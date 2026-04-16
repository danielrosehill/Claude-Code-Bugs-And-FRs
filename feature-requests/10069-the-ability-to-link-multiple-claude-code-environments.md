---
upstream_url: https://github.com/anthropics/claude-code/issues/10069
upstream_number: 10069
upstream_state: CLOSED
status: filed-closed-stale
created: 2025-10-21
closed: 2026-01-08
labels: [enhancement, area:core, autoclose]
---

# [FEATURE] The ability to link multiple claude code environments

**Upstream:** [#10069](https://github.com/anthropics/claude-code/issues/10069) — `CLOSED` (closed-stale)
**Created:** 2025-10-21 • **Closed:** 2026-01-08
**Labels:** enhancement, area:core, autoclose

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

Consider this common usage scenario:

The user (me!) uses claude code to ssh into a remote (maybe on the lan, maybe not).

That environment (enviroment 2) also has claude cli installed (this config has resulted from experimenting with running claude on the server versus using mcp or direct ssh to connect from a local claude code).

It would be nice if (in the same way that you can configure bash aliases), claude could "remember" that it has a networked claude code environment at X (IP and/or authentication method).

Potential advantages: 

- This could allow even more flexibility than configuring aliases for remotes
- The connecting agent knows to expect another claude enabled environment on the remote so might do things like inspect its slash commands

To my mind, this could provide the basis for greater certainty around how claude behaves when it finds another claude in an environment its working in!

### Proposed Solution

- User connects to an environment 
- Claude detects the prescence of another Claude installation through finding artefacts like .claude, CLAUDE.md
- Claude asks user if it woudl like it to remember this environment and to give it a name 
- Claude adds a memory that this environment exists and has X parameters 
- This remote can be recalled for connection regardless of whether it is defined in the user's ssh config / aliases

### Alternative Solutions

_No response_

### Priority

Low - Nice to have

### Feature Category

Configuration and settings

### Use Case Example

_No response_

### Additional Context

_No response_
