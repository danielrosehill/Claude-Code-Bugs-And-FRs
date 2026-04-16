---
upstream_url: https://github.com/anthropics/claude-code/issues/15271
upstream_number: 15271
upstream_state: CLOSED
status: filed-closed
created: 2025-12-24
closed: 2025-12-26
labels: [enhancement, area:mcp]
---

# [FEATURE] Time awareness as a built in MCP

**Upstream:** [#15271](https://github.com/anthropics/claude-code/issues/15271) — `CLOSED` (closed)
**Created:** 2025-12-24 • **Closed:** 2025-12-26
**Labels:** enhancement, area:mcp

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

Setting up MCP servers can be tedious and challenging. Anything to reduce the tedium and pitfalls would generally be welcomed, I believe.

The MCP standard provides a time-awareness MCP (`@modelcontextprotocol/server-time'), but it is not enabled out of the box.

Currently, without external tooling or assistance, Claude remains frozen in the knowledge cutoff of the model, which, without careful supervision, can lead to embarrassing mistakes. 

This can lead to development challenges as well. I frequently find myself having to tell Claude that Gemini 3 is a real thing; it was just released after its training data.

Without this instruction and without re-adding the time server, it was changing the environment variables back to 2.5 because it believed that I was mistaken.

With the current models, they believe the year to be 2024.

### Proposed Solution

I would suggest that the time awareness server comes bundled with Claude Code to obviate the need to install it. 

Perhaps there could be a default enabled MCP section. 

The time server only provides a single tool and therefore is a minimal contributor to MCP bloat.

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
