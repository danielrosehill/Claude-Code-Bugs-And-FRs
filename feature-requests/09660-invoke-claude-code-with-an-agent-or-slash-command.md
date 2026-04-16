---
upstream_url: https://github.com/anthropics/claude-code/issues/9660
upstream_number: 9660
upstream_state: CLOSED
status: filed-closed-duplicate
created: 2025-10-16
closed: 2025-10-20
labels: [duplicate]
---

# [FEATURE] Invoke Claude Code with an agent or slash command

**Upstream:** [#9660](https://github.com/anthropics/claude-code/issues/9660) — `CLOSED` (closed-duplicate)
**Created:** 2025-10-16 • **Closed:** 2025-10-20
**Labels:** duplicate

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

Apologies if this has already been covered in a prior feature request. I did search and wasn't able to find it, but given the large volume of discussions here, I may have missed some keywords. 

Frequently I find that I would like to be able to initiate Claude in a specific context with an existing agent or slash command. 

For the purpose of creating tools and utilities which wrap over Claude Code, it would be especially useful to have execution parameters for agents and commands that can be invoked before the CLI runtime.


### Proposed Solution

Parameters like: ``--agent`` or ``--slash`` or `--command`` which could be chained with ``claude``.

Example: it would be super helpful to createa  bash alias like ``debug python`` which might be an alias for ``claude --python-debugger`` - where ``python-debugger`` is the agent ID.

### Alternative Solutions

From what I understand from the man page and reference lit:

You *can* use slash commands this way but not agents/subagents

(Sorry if I got that wrong)

### Priority

Medium - Would be very helpful

### Feature Category

CLI commands and flags

### Use Case Example

_No response_

### Additional Context

_No response_
