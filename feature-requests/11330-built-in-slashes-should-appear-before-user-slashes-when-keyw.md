---
upstream_url: https://github.com/anthropics/claude-code/issues/11330
upstream_number: 11330
upstream_state: CLOSED
status: filed-closed-stale
created: 2025-11-09
closed: 2026-01-11
labels: [enhancement, area:tui, area:mcp, autoclose]
---

# [FEATURE] Built in slashes should appear before user slashes when keywords match

**Upstream:** [#11330](https://github.com/anthropics/claude-code/issues/11330) — `CLOSED` (closed-stale)
**Created:** 2025-11-09 • **Closed:** 2026-01-11
**Labels:** enhancement, area:tui, area:mcp, autoclose

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

Users might credibly create slash commands that involve phrases that are part of the important ones built into the system.

E.g.:

`/new-mcp-server`

If you have a few of these they will tend to obscure the system slash of `/mcp` and it takes a bit of ... thinking to figure out that you need to scroll all the way past the auto-suggestions.

### Proposed Solution

One idea (UI):

Different background shading for built in slashes to make them visually obvious as opposed to use added ones

Prefential ordering: as the system slashes (esp MCP) are very important they should always be shown before user slashes regardless of filtering logic

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
