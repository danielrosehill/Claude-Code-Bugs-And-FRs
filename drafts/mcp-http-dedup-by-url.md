---
status: draft
kind: bug
created: 2026-04-16
upstream_url: null
upstream_number: null
needs: clean reproduction with two dummy HTTP MCP servers at the same URL
---

# [BUG] Two HTTP MCP servers with the same URL but different headers — only one registers

**Status:** draft (needs reproduction before filing)

---

## What's wrong

When `.mcp.json` declares two HTTP-type MCP server entries that point to the same `url` but use different `headers` (e.g. distinct `Authorization` bearer tokens for different tenants/projects of the same SaaS), only the first entry registers. The second silently disappears from the available servers list — no error, no warning.

## Repro (suspected — not yet verified)

`.mcp.json` like:

```json
{
  "mcpServers": {
    "saas-personal": {
      "type": "http",
      "url": "https://mcp.example.com/mcp",
      "headers": { "Authorization": "Bearer ${PERSONAL_KEY}" }
    },
    "saas-work": {
      "type": "http",
      "url": "https://mcp.example.com/mcp",
      "headers": { "Authorization": "Bearer ${WORK_KEY}" }
    }
  }
}
```

Expected: both `saas-personal` and `saas-work` register as separate MCP servers with their own toolsets and auth contexts.

Actual: only one (typically the first) shows up in the available MCP server list. The other is silently dropped.

## Originally hit while

Configuring the `claude-user-memory` plugin which ships two Mem0 MCP instances (`mem0-personal` and `mem0-work`) — both pointing at `https://mcp.mem0.ai/mcp` with different bearer tokens. Only `mem0-personal` showed up; `mem0-work` was missing entirely. No error log surfaced.

## Why it matters

Multi-tenant SaaS APIs commonly expose a single MCP endpoint and discriminate by bearer token (Mem0 personal vs work projects, Pinecone projects, multiple GitHub orgs, etc). Plugin authors who want to ship multiple isolated contexts against one provider have no way to do so today.

## Workaround

Single MCP entry + pass tenant/project scope as a parameter on each tool call (the `claude-user-memory` plugin's `CONTEXT.md` actually documents passing `project_id` per call). Works, but defeats the point of having separate logical servers, and breaks the cleaner per-server tool isolation.

## Notes before filing

- Need to reproduce with two dummy HTTP servers (e.g. echo servers on different paths of the same host, or with distinct `User-Agent` echoing) to confirm dedup-by-URL is the actual cause vs. some other failure mode (silent auth failure, race in connection setup, etc.).
- Worth checking `claude mcp list` and any debug logs to confirm only one entry is loaded vs. both loading then one failing.
- Check whether stdio-type servers have the same issue (probably not since they have distinct command lines).
