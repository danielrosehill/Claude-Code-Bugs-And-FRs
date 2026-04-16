---
upstream_url: https://github.com/anthropics/claude-code/issues/37426
upstream_number: 37426
upstream_state: OPEN
status: filed-open
created: 2026-03-22
closed: n/a
labels: [documentation, area:mcp, stale]
---

# [DOCS] Claude.ai Connectors And Claude Code Connection

**Upstream:** [#37426](https://github.com/anthropics/claude-code/issues/37426) — `OPEN` (open)
**Created:** 2026-03-22
**Labels:** documentation, area:mcp, stale

---

### Documentation Type

Missing documentation (feature not documented)

### Documentation Location

_No response_

### Section/Topic

MCP

### Current Documentation

Anthropic docs are somewhat divided between docs for the Claude.ai product and for Claude Code, although in practice everyone with a Claude Code sub has access to Claude (the conversational agent). 

Both sets of docs are good. But I couldn'rt find one covering a very important nuance: how Claude.ai "connectors" become available in Claude Code (CLI) sessions.



### What's Wrong or Missing?

It might seem obvious, but I didn't assume that connectors (added in Claude.ai) would be inherited by the CLI. I assumed that if it had its own MCP management ,that that was done for a reason.

`claude mcp list` also doesn't really provide this info. 

### Suggested Improvement

As far as I know all of this is correct:

- If you add connectors in Claude.ai, they're going to be available in Claude Code 
- They are lazy-loaded 
- Claude CLI can access them 

It would be useful to document this because, without doing so, there's a risk that confused useres, like me, might end up creating duplicates (ie, a connector for Claude the chatbot and an MCP for Claude Code) not realising that this may not be necessary. 

The shared MCP connection model is efficient and makes sense. But, in my opinion, users, used to configuring MCPs manually, are not going to necessarily grasp that the two features are integrated.

Some best practice/recommendation guidance would also be valuable:

- If you want an email tool, do you recommend using, say, a Google Workspace MCP or just using the connector? When might either be preferable (etc).


### Impact

Medium - Makes feature difficult to understand

### Additional Context

_No response_
