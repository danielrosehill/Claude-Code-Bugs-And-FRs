---
upstream_url: https://github.com/anthropics/claude-code/issues/12363
upstream_number: 12363
upstream_state: CLOSED
status: filed-closed
created: 2025-11-25
closed: 2025-11-25
labels: [enhancement, area:tui, area:ide]
---

# [FEATURE] Unobtrusive editing mode in VS Code

**Upstream:** [#12363](https://github.com/anthropics/claude-code/issues/12363) — `CLOSED` (closed)
**Created:** 2025-11-25 • **Closed:** 2025-11-25
**Labels:** enhancement, area:tui, area:ide

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

When working with Claude on projects, sometimes I will delegate a task while working on another task in the IDE separately. 

In such workflows, my desire is that Claude will work autonomously and I may wish to review the proposed changes at a convenient time. 

The problem is that the diffs are opened immediately and on the fly in the IDE. This means that I can't really use the IDE at the same time as the agent without (AFAIK) using things like split windows. 

### Proposed Solution

It would be nice to have a UI mode that supported something that might be labeled unobtrusive editing (I'm sure a better name can be conceived).

This workflow would have the agent applying its suggested diffs in such a way that they don't automatically trigger new window opens within the IDE allowing the human to work simultaneously with the agent. 

Maybe something like a open diffs button could allow the human to view the proposed changes when ready to do so. 

### Alternative Solutions

_No response_

### Priority

Critical - Blocking my work

### Feature Category

CLI commands and flags

### Use Case Example

_No response_

### Additional Context

_No response_
