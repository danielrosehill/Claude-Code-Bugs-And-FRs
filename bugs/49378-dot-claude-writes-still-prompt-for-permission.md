---
status: filed-open
kind: bug
created: 2026-04-16
filed: 2026-04-16
upstream_url: https://github.com/anthropics/claude-code/issues/49378
upstream_number: 49378
upstream_state: open
labels: [bug]
evidence: bugs/assets/claude-dir-permission-prompt.png
---

# [BUG] `.claude/**` writes still prompt for permission despite explicit `Write(.claude/**)` and bare `Write` allowlist entries

**Upstream:** [#49378](https://github.com/anthropics/claude-code/issues/49378) — `OPEN`
**Filed:** 2026-04-16
**Evidence:** [`bugs/assets/claude-dir-permission-prompt.png`](assets/claude-dir-permission-prompt.png)

---

## Summary

Writes to files inside a project-local `.claude/` directory trigger a manual permission prompt even when the user-level `permissions.allow` list contains all of `Write`, `Write(.claude/**)`, and `Write(**/.claude/**)`.

## Reproduction

1. Ensure `~/.claude/settings.json` allows `Write`, `Write(.claude/**)`, `Write(**/.claude/**)`.
2. In any project, ask Claude to create `.claude/commands/test.md`.
3. Permission prompt appears anyway.

Reproduced live in this very repo while staging this filing — see screenshot.

## Hypothesis

`.claude/` paths appear to be special-cased in the permission matcher (likely a security guardrail against prompt-injection-driven self-modification of agents/commands/hooks). If so, that special-case isn't documented and the bare `Write` rule misleadingly suggests it would cover it.
