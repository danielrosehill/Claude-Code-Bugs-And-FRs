---
upstream_url: https://github.com/anthropics/claude-code/issues/8324
upstream_number: 8324
upstream_state: OPEN
status: filed-open
created: 2025-09-28
closed: n/a
labels: [bug, has repro, platform:linux, area:tui]
---

# [BUG] Can't paste image from clipboard on Linux (Ubuntu)

**Upstream:** [#8324](https://github.com/anthropics/claude-code/issues/8324) — `OPEN` (open)
**Created:** 2025-09-28
**Labels:** bug, has repro, platform:linux, area:tui

---

### Preflight Checklist

- [x] I have searched [existing issues](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20state%3Aopen%20label%3Abug) and this hasn't been reported yet
- [x] This is a single bug report (please file separate reports for different bugs)
- [x] I am using the latest version of Claude Code

### What's Wrong?

Using Ubuntu Linux, I'm unable to paste an image from my clipboard into the CLI.

System: Ubuntu 25.04 + KDE (Wayland).

Verified that the image is on the clipboard by pasting into GIMP and with:

`wl-paste --list-types`

``` 
application/x-qt-image        
     image/png
     image/avif
```

However, after pasting, Claude Code flashes:

<img width="776" height="179" alt="Image" src="https://github.com/user-attachments/assets/3b803f1c-ff37-488f-80e1-b62aaf667382" />

### What Should Happen?

Image should paste into the CLI (FYI, using Konsole)

### Error Messages/Logs

```shell
N/A
```

### Steps to Reproduce

Use environment as above.

Install claude with npm, upgrade to lastest version 

Copy an image onto the clipboard 

Paste into the CLI

### Claude Model

None

### Is this a regression?

Yes, this worked in a previous version

### Last Working Version

_No response_

### Claude Code Version

1.0.128 (Claude Code)

### Platform

Anthropic API

### Operating System

Ubuntu/Debian Linux

### Terminal/Shell

Other

### Additional Information

Shell = konsole
