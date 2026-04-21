---
status: filed-open
kind: feature
created: 2026-04-20
filed: 2026-04-20
upstream_url: https://github.com/anthropics/claude-code/issues/51348
upstream_number: 51348
upstream_state: open
labels: [documentation, enhancement, area:docs, area:plugins]
---

# [DOCS] Describe process for creating private plugins

**Upstream:** [#51348](https://github.com/anthropics/claude-code/issues/51348) — `OPEN`
**Filed:** 2026-04-20
**Labels:** documentation, enhancement, area:docs, area:plugins

---

### Documentation Type

Missing documentation (feature not documented)

### Documentation Location

https://code.claude.com/docs/en/discover-plugins

### Section/Topic

Plugins

### Current Documentation

Discover and install prebuilt plugins through marketplaces

Find and install plugins from marketplaces to extend Claude Code with new skills, agents, and capabilities.

Plugins extend Claude Code with skills, agents, hooks, and MCP servers. Plugin marketplaces are catalogs that help you discover and install these extensions without building them yourself.
Looking to create and distribute your own marketplace? See [Create and distribute a plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces).

### What's Wrong or Missing?

Plugins are fantastic ways of bundling together Claude primitives.

In certain instances, however, plugins are not suitable for sharing. Consider plugins that might be specific for a team's internal workflow and contain proprietary information about process, etc.

The CLI UX and documentation are a little confusing because the statement that to install a plugin you should a) create a marketplace and b) install your plugin implies that:

1. There's no way to create and use a plugin that doesn't involve creating a marketplace (I think true!)
2. A "marketplace" strongly suggests that the marketplace is intended to be public

The docs does not mention "private" at all. I discovered that private plugins *could* be created by finding guides [like this one](https://alexmcfarland.substack.com/p/you-need-a-private-claude-plugin) on Google.

### Suggested Improvement

A simply FAQ: how do I create a private plugin? What do I do if I don't want my plugin to be public?

Answer (weird workaround for the moment): create a *private* marketplace. Then add your *private* plugin. Then install.

This procedure is itself kind of counterintuitive and there's a definite risk that users would inadvertently add a private plugin to a public marketplace.

### Impact

Medium - Makes feature difficult to understand
