---
upstream_url: https://github.com/anthropics/claude-code/issues/49413
upstream_number: 49413
upstream_state: OPEN
status: filed-open
created: 2026-04-16
closed: n/a
labels: [enhancement, area:skills]
---

# [FEATURE] Ship a first-party feedback skill for filing issues from inside Claude Code

**Upstream:** [#49413](https://github.com/anthropics/claude-code/issues/49413) — `OPEN` (open)
**Created:** 2026-04-16
**Labels:** enhancement, area:skills

---

### Preflight Checklist

- [x] I have searched existing requests and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

Filing well-formed issues against `anthropics/claude-code` from inside an active Claude Code session is higher-friction than it should be. The in-repo issue forms (`bug_report.yml`, `feature_request.yml`, `model_behavior.yml`, `docs.yml`) have many required fields, strict dropdown options, and change over time. Ad-hoc issue creation from a session tends to produce malformed reports that bounce or need re-filing, and the built-in `/bug` flow only covers a subset of the feedback surface (no feature requests, docs issues, or model-behavior reports).

Community plugins can paper over this, but they go stale the moment upstream templates change, aren't discoverable to most users, and have no sanctioned status.

### Proposed Solution

Ship a first-party feedback skill (or skill bundle) maintained by Anthropic, bundled with Claude Code or available via the official plugin marketplace.

Here's a functional skill I built that covers this surface: https://github.com/danielrosehill/Claude-Code-Feedback-Plugin — I'm offering it as a starting point / reference implementation, but the point of this request is that something like this should be an **Anthropic-maintained agent skill** rather than a community plugin. Happy to transfer, relicense, or have it reimplemented; attribution isn't the ask.

Minimum viable shape:

- One skill per issue-form type under `.github/ISSUE_TEMPLATE/` (bug, feature request, model behavior, docs — plus anything Anthropic adds later).
- Self-healing: fetch the live YAML from `main` on each run rather than baking field lists into the skill. Cache for offline fallback and drift detection.
- Interview-style gathering that respects `required`/`validations`, renders dropdowns verbatim, and previews the final body before `gh issue create`.
- Invoked naturally ("report a bug", "file a feature request", "the model refused to…") so users don't need to remember a slash command.

Because Anthropic controls both the issue forms and the skill, self-healing becomes near-trivial to guarantee — template changes can ship alongside skill updates.

### Alternative Solutions

- **Status quo:** users open the GitHub web UI and fill the form manually — context-switch cost suppresses feedback volume.
- **The existing built-in `/bug` command:** bugs only, and has had its own issues (e.g. #35845 where user skills intercepted it). Doesn't cover feature requests, model behavior, or docs.
- **Third-party plugins:** work for users who find and install them, but fragmentation means most users never encounter one, and maintenance falls on individuals.

### Priority

Low - Nice to have

### Feature Category

Developer tools/SDK

### Use Case Example

1. Mid-session, Claude Code does something surprising — a skill stalls, or the model returns an obviously wrong refactor.
2. User types "file a bug about this" (or "feature request: I wish /resume could…").
3. The first-party feedback skill activates, fetches the current `bug_report.yml` from `main`, and walks the user through each field with context from the current session pre-filled where appropriate (CLI version, OS, recent tool calls — with secrets redacted).
4. Skill previews the rendered issue, user confirms, `gh issue create` submits.
5. User stays in flow; Anthropic receives a correctly-formatted report that slots straight into triage.

### Additional Context

Reference implementation: https://github.com/danielrosehill/Claude-Code-Feedback-Plugin — MIT-licensed, four skills (bug / feature-request / model-behavior / docs) plus a `refresh-templates` skill that detects drift and scaffolds new skills when Anthropic adds new issue-form types.

Related existing requests: #30727 (Official Verified Marketplace for Skills, MCP Servers, and Custom Agents) — this is a narrower first-party-skill ask, not a marketplace proposal.
