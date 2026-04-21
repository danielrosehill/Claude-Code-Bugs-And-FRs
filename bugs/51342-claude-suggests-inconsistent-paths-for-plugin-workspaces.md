---
status: filed-open
kind: bug
created: 2026-04-20
filed: 2026-04-20
upstream_url: https://github.com/anthropics/claude-code/issues/51342
upstream_number: 51342
upstream_state: open
labels: [bug, area:model, area:plugins]
---

# [MODEL] Claude suggests inconsistent paths under user level Claude store (.claude) for plugin workspaces

**Upstream:** [#51342](https://github.com/anthropics/claude-code/issues/51342) — `OPEN`
**Filed:** 2026-04-20
**Labels:** bug, area:model, area:plugins

---

### Type of Behavior Issue

Claude made incorrect assumptions about my project

### What You Asked Claude to Do

While developing Claude Code plugins intended for public marketplace release, I ask Claude Code to help decide where the plugin should persist per-user state (onboarding answers, preferences, etc.) — data that must survive plugin updates and ideally be portable across machines.

### What Claude Actually Did

Claude consistently suggests paths nested under `~/.claude/`, for example:

- `~/.claude/plugin-data/<plugin-name>/`
- `~/.claude/<plugin-name>-data/`
- `~/.claude/data/<plugin-name>/`

The specific subpath varies between sessions and even within a single session, but the bias toward `~/.claude/` as the root is consistent. Claude does not proactively suggest XDG Base Directory paths.

There are two problems with this (note: I'm using the plugin development skill)

- **Non deterministic**: if you follow this blindly, you will end up propagating a discorderly and inconsistent data structure for users within their `.claude`.
- **Chance of data loss**: Assuming that these paths are not safe from Claude Code updates, this creates a non-insignificant chance of data loss/erasure for users.

## Docs

[Docs ref](https://code.claude.com/docs/en/plugins-reference).

> A plugin is a self-contained directory of components that extends Claude Code with custom functionality. Plugin components include skills, agents, hooks, MCP servers, LSP servers, and monitors.

Admittedly, this doesn't address the issue of user memory persistency so perhaps the desired behavior is that users should use memory for this purpose (but general user-memory is not a great way to maintain templates and other artifacts that might be bundled by the plugin author!)

Under "optional fields" for the `plugin.json` the reference doc provides:

```
"workspaceFolder	Workspace folder path for the server"
```

This suggested to me at least that the idea that plugins could declare a persistent data/storage folder **is** intended but that the path is not specified yet.

### Expected Behavior

For per-user plugin state, Claude should default to the XDG Base Directory spec on Linux and its cross-platform equivalents:

- **Linux**: `$XDG_DATA_HOME/<plugin>/` (default `~/.local/share/<plugin>/`) for data; `$XDG_CONFIG_HOME/<plugin>/` (default `~/.config/<plugin>/`) for config
- **macOS**: `~/Library/Application Support/<plugin>/`
- **Windows**: `%APPDATA%\<plugin>\`

`~/.claude/` is Claude Code's own config/install directory. Third-party plugins should not write user data there by default, and they must never write inside `~/.claude/plugins/<plugin>/` — that directory is owned by the marketplace installer and is overwritten on plugin update.

### Steps to Reproduce

1. Start a Claude Code session and ask it to help design a Claude Code plugin that includes an onboarding flow which persists user answers across sessions.
2. Ask: "Where should the plugin store its per-user data?"
3. Claude tends to propose a path nested under `~/.claude/` rather than an XDG-compliant path.

### Claude Model

Opus 4.7

### Claude Code Version

2.1.116

### Additional Context

Likely cause: overgeneralization from the fact that Claude Code's own dotfiles and plugin installs live under `~/.claude/`. The model appears to treat that directory as a general-purpose home for anything plugin-related rather than recognising it as Anthropic-owned configuration space.

Suggested correction: when advising on plugin user-data storage, default to XDG paths and explicitly exclude `~/.claude/` unless the data is part of Claude Code's own configuration surface.
