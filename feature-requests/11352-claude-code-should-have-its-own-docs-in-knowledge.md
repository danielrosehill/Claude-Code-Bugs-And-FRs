---
upstream_url: https://github.com/anthropics/claude-code/issues/11352
upstream_number: 11352
upstream_state: CLOSED
status: filed-closed-duplicate
created: 2025-11-10
closed: 2025-11-14
labels: [duplicate]
---

# [FEATURE] Claude Code should have its own docs in knowledge!

**Upstream:** [#11352](https://github.com/anthropics/claude-code/issues/11352) — `CLOSED` (closed-duplicate)
**Created:** 2025-11-10 • **Closed:** 2025-11-14
**Labels:** duplicate

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

Claude Code does not seem to have an innate understanding of its own documentation!

I've experienced this on multiple times:

Ask Claude Code: "hey, could you take this JSON object and give me the `claude mcp add`"

Claude returns with invalid syntax that does not pass. 

### Proposed Solution

It would be ideal if Claude had its own (dynamically updated) documentation available via RAG so that not only did it return correct syntax but it didn't even need to use fetch ... as having Claude Code search the internet to know how the user is supposed to operate it seems a bit nonsensical.

### Alternative Solutions

_No response_

### Priority

Medium - Would be very helpful

### Feature Category

CLI commands and flags

### Use Case Example

_No response_

### Additional Context

_No response_
