---
upstream_url: https://github.com/anthropics/claude-code/issues/12732
upstream_number: 12732
upstream_state: CLOSED
status: filed-closed-stale
created: 2025-11-30
closed: 2026-01-30
labels: [bug, has repro, platform:linux, area:core, autoclose]
---

# [BUG]  Agent does not follow the correct format when creating sub-agents.

**Upstream:** [#12732](https://github.com/anthropics/claude-code/issues/12732) — `CLOSED` (closed-stale)
**Created:** 2025-11-30 • **Closed:** 2026-01-30
**Labels:** bug, has repro, platform:linux, area:core, autoclose

---

### Preflight Checklist

- [x] I have searched [existing issues](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20state%3Aopen%20label%3Abug) and this hasn't been reported yet
- [x] This is a single bug report (please file separate reports for different bugs)
- [x] I am using the latest version of Claude Code

### What's Wrong?

You can ask Claude to create a sub-agent to support the operation of this repository. 

However, unless you do this using the specific agent slash command (`/agents`) Claude will invariably create agents that lack the minimal front matter and which are not recognized by the orchestrator. 

### What Should Happen?

Claude should have inherent understanding of its own documentation in general (this was addressed in a previous bug report). But in the specific case of sub-agents, it should certainly know the essential front-matter 

Allowing for the creation of agents in standard chats would create a more fluid user experience. 

### Error Messages/Logs

```shell

```

### Steps to Reproduce

During a chat with Claude, ask it to create an agent. 

In the majority of cases:

- Claude will correctly create the agent configuration within the target directory (`.claude/agents`) 
- The created config will lack frontmatter 

### Claude Model

Not sure / Multiple models

### Is this a regression?

Yes, this worked in a previous version

### Last Working Version

_No response_

### Claude Code Version

2.0.55

### Platform

Anthropic API

### Operating System

Ubuntu/Debian Linux

### Terminal/Shell

Terminal.app (macOS)

### Additional Information

_No response_
