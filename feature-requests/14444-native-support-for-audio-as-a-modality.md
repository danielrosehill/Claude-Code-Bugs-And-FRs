---
upstream_url: https://github.com/anthropics/claude-code/issues/14444
upstream_number: 14444
upstream_state: CLOSED
status: filed-closed-stale
created: 2025-12-18
closed: 2026-03-08
labels: [enhancement, area:model, area:core, stale]
---

# [FEATURE] Native support for audio as a modality

**Upstream:** [#14444](https://github.com/anthropics/claude-code/issues/14444) — `CLOSED` (closed-stale)
**Created:** 2025-12-18 • **Closed:** 2026-03-08
**Labels:** enhancement, area:model, area:core, stale

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

Claude has the ability to process images directly as a modality but not audio binary data (or video AFAIK)

### Proposed Solution

Voice is an immensely effective modality for capturing information and facilitates spec-based development. In CLI-only interfaces, audio can be captured and saved as MP3 recordings.

If Claude had native support for the audio mentality such that it could accept user requests for creating transcriptions or summarized transcriptions, it would relieve the need to integrate MCP tooling for transcriptions.

### Alternative Solutions

The user could record and provide an MP3 in a repository containing a spec for development. This could be contextual data or any other audio data captured for any other reason, like an interview transcript or a voice note from a development sprint.

If this modality were available, the user could add hooks and slash commands in order to round out those requests to ensure robust operation. For example, adding an inferred instruction that whenever formats like this were requested, the time stamp be added for documentation.

### Priority

Medium - Would be very helpful

### Feature Category

CLI commands and flags

### Use Case Example

As you can point to an image and Claude will engage its vision modality to parse the image, the user could ask Claude a simple request like, "This file contains a recording from our development sprint. The last five minutes contain our decisions. Could you process the audio file and document those decisions in the repository in an organized fashion to capture the information?"

### Additional Context

_No response_
