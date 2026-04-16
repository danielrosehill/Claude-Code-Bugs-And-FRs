---
upstream_url: https://github.com/anthropics/claude-code/issues/11740
upstream_number: 11740
upstream_state: CLOSED
status: filed-closed-stale
created: 2025-11-16
closed: 2026-01-18
labels: [enhancement, area:tools, area:mcp, autoclose]
---

# [FEATURE] List subcommand for plugins

**Upstream:** [#11740](https://github.com/anthropics/claude-code/issues/11740) — `CLOSED` (closed-stale)
**Created:** 2025-11-16 • **Closed:** 2026-01-18
**Labels:** enhancement, area:tools, area:mcp, autoclose

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

If you want to see which plugins you have installed.

I can get to that via the enable or disable flags:

<img width="1253" height="295" alt="Image" src="https://github.com/user-attachments/assets/193cfc57-cfa1-4343-9f6c-fdf900691571" />

But there's no equivalent of 

`claude mcp list`

Which I would have expected to exist to just show the plugins i have installed maybe in a format that shows the markplace from which they were installed too



### Proposed Solution

My usual workflow would be:

- See which plugins I have 
- See what to keep/remove

Subcommand:

`claude plugins list`

To provide that showing plugin list and marketplace associations




### Alternative Solutions

_No response_

### Priority

High - Significant impact on productivity

### Feature Category

CLI commands and flags

### Use Case Example

_No response_

### Additional Context

_No response_
