---
upstream_url: https://github.com/anthropics/claude-code/issues/12810
upstream_number: 12810
upstream_state: CLOSED
status: filed-closed-duplicate
created: 2025-12-01
closed: 2025-12-05
labels: [duplicate]
---

# [FEATURE]  Native support for multiple accounts

**Upstream:** [#12810](https://github.com/anthropics/claude-code/issues/12810) — `CLOSED` (closed-duplicate)
**Created:** 2025-12-01 • **Closed:** 2025-12-05
**Labels:** duplicate

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

I use Claude Code both for personal projects and for a client. 

I maintain two paid accounts:

- My own (Claude Max 200) 
- The client's 

Sometimes I work for several hours on the client's site and manually change between subscriptions. To avoid cutting into my own weekly allowance, I manually change accounts before and after the process. 

But currently the process for doing this is cumbersome:

I need to log out, log in, reauthorize with the new browser credential and then repeat the process when switching back. 

### Proposed Solution

Before talking about better "quality of life" solutions I think the core realisation has to be that there _are_ legitimate reasons why users might hold multiple subs. At one time, I had three (personal, consultancy, client A).

Users who do pay concurrent subs should not have to jump through hoops or add on third-party tooling just to achieve a basic account switching functionality. 

It would be much more pragmatic for the CLI to be able to hold a couple of authentications in memory such that every account change did not require a new authentication flow (and the issuance of a new API key).

To support the needs of multi-account users, it would be also very helpful to have account labeling. I could label my auth tokens Personal and ACME, for example. 

Generally, I'm working in one specific repository for the client. So being able to define an account param that's repo-bound would also be a very elegant fix.

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
