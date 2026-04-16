---
upstream_url: https://github.com/anthropics/claude-code/issues/14973
upstream_number: 14973
upstream_state: CLOSED
status: filed-closed-duplicate
created: 2025-12-21
closed: 2025-12-25
labels: [duplicate]
---

# [BUG] VS Code Extension Defaulting To Sonnet, Ignoring Model Setting

**Upstream:** [#14973](https://github.com/anthropics/claude-code/issues/14973) — `CLOSED` (closed-duplicate)
**Created:** 2025-12-21 • **Closed:** 2025-12-25
**Labels:** duplicate

---

### Preflight Checklist

- [x] I have searched [existing issues](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20state%3Aopen%20label%3Abug) and this hasn't been reported yet
- [x] This is a single bug report (please file separate reports for different bugs)
- [x] I am using the latest version of Claude Code

### What's Wrong?

In VS Code Claude Code extension:

Select model:

<img width="560" height="576" alt="Image" src="https://github.com/user-attachments/assets/5290efd4-32c7-4ac9-b742-6f39eb5f243b" />

Can choose default or specifically Opus:

<img width="560" height="576" alt="Image" src="https://github.com/user-attachments/assets/1d02635c-0d55-4e61-9fe2-760c2555b152" />

Let's try force Opus. 

Test:

<img width="546" height="339" alt="Image" src="https://github.com/user-attachments/assets/7b98afcd-914c-44fb-bd4a-1423d4e13252" />

But if I start a new session, lo and behold, the selection has mysteriously reset itself to Sonnet!

<img width="563" height="614" alt="Image" src="https://github.com/user-attachments/assets/b1614fb6-dcb6-4922-8a34-599575834d28" />

This is particularly strange given that my default model via the "regular" CLI has held:

<img width="565" height="300" alt="Image" src="https://github.com/user-attachments/assets/66e14673-aa6d-42f7-8eb2-6e73093c5841" />


### What Should Happen?

Claude Code VS Code Extension should both:

1) Honor model preference of the CLI 

2) Honor any user-overrides in the IDE

### Error Messages/Logs

```shell

```

### Steps to Reproduce

Pretty sure yes

### Claude Model

None

### Is this a regression?

Yes, this worked in a previous version

### Last Working Version

_No response_

### Claude Code Version

v2.0.75

### Platform

Other

### Operating System

Ubuntu/Debian Linux

### Terminal/Shell

Terminal.app (macOS)

### Additional Information

_No response_
