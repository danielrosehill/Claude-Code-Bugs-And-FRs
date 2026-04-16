---
upstream_url: https://github.com/anthropics/claude-code/issues/9145
upstream_number: 9145
upstream_state: CLOSED
status: filed-closed-duplicate
created: 2025-10-08
closed: 2025-10-12
labels: [duplicate]
---

# [BUG] Shift + tab not persisting

**Upstream:** [#9145](https://github.com/anthropics/claude-code/issues/9145) — `CLOSED` (closed-duplicate)
**Created:** 2025-10-08 • **Closed:** 2025-10-12
**Labels:** duplicate

---

### Preflight Checklist

- [x] I have searched [existing issues](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20state%3Aopen%20label%3Abug) and this hasn't been reported yet
- [x] This is a single bug report (please file separate reports for different bugs)
- [x] I am using the latest version of Claude Code

### What's Wrong?

Pressing shift and tab is supposed to allow all edits during the session. 

<img width="875" height="366" alt="Image" src="https://github.com/user-attachments/assets/a977b120-4fe4-469a-9fc6-534e2c2c5550" />

However, with the latest version of CC, if I do that it doesn't seem to persist 

Right after I clicked shift and tab (by selecting 2 + enter) in the above dialog, I got this screen:

<img width="875" height="366" alt="Image" src="https://github.com/user-attachments/assets/26ad4d63-3ebf-4cea-b0b6-0d11a9794068" />


### What Should Happen?

Shift and tab should do what it says it will "allow all edits during this session."

### Error Messages/Logs

```shell
The only explanation I can think of is that I have `.claude` added to my global git ignore. 

I have no idea *where* CC saves the session state and user selections but maybe it can't see them if the folder is hidden due to sandboxing`
```

### Steps to Reproduce

Environment: Ubuntu 25.04

Subscription: I'm using CC with my Max sub

Context: using it inside VS code to work on a project 

### Claude Model

None

### Is this a regression?

Yes, this worked in a previous version

### Last Working Version

_No response_

### Claude Code Version

2.0.10 (Claude Code)

### Platform

Anthropic API

### Operating System

Ubuntu/Debian Linux

### Terminal/Shell

VS Code integrated terminal

### Additional Information

_No response_
