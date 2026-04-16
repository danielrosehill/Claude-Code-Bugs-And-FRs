---
upstream_url: https://github.com/anthropics/claude-code/issues/38203
upstream_number: 38203
upstream_state: CLOSED
status: filed-closed-duplicate
created: 2026-03-24
closed: 2026-03-28
labels: [duplicate]
---

# [BUG] Images are always injected as binaries on Linux - can't provide a path

**Upstream:** [#38203](https://github.com/anthropics/claude-code/issues/38203) — `CLOSED` (closed-duplicate)
**Created:** 2026-03-24 • **Closed:** 2026-03-28
**Labels:** duplicate

---

### Preflight Checklist

- [x] I have searched [existing issues](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20state%3Aopen%20label%3Abug) and this hasn't been reported yet
- [x] This is a single bug report (please file separate reports for different bugs)
- [x] I am using the latest version of Claude Code

### What's Wrong?

Currently, I have no way to provide Claude with the path to an image.

I:

- Copy location (path of image resource).
- Paste into terminal (I'm using Konsole)

But:

- Claude Code automatically ingests it as an image binary which it then can't process because it doesn't have the raw path and I have no way of providing it

<img width="1908" height="522" alt="Image" src="https://github.com/user-attachments/assets/d67dfe7e-0ee2-4356-8bd5-f62b65b91719" />

### What Should Happen?

Paste a path (raw text): Claude Code CLI gets raw path 

Paste an image (image encoded data on clipboad): Claude Code gets the image data

### Error Messages/Logs

```shell

```

### Steps to Reproduce

Run Claude Code on Ubuntu with KDE Plasma and Konsole and try pasting an image path

### Claude Model

None

### Is this a regression?

I don't know

### Last Working Version

_No response_

### Claude Code Version

2.1.81

### Platform

Anthropic API

### Operating System

Ubuntu/Debian Linux

### Terminal/Shell

Other

### Additional Information

_No response_
