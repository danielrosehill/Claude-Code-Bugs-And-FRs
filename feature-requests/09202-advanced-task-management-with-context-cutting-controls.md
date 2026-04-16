---
upstream_url: https://github.com/anthropics/claude-code/issues/9202
upstream_number: 9202
upstream_state: CLOSED
status: filed-closed-stale
created: 2025-10-09
closed: 2026-01-07
labels: [enhancement, area:tui, area:core, memory, autoclose]
---

# [FEATURE] Advanced task management with context cutting controls

**Upstream:** [#9202](https://github.com/anthropics/claude-code/issues/9202) — `CLOSED` (closed-stale)
**Created:** 2025-10-09 • **Closed:** 2026-01-07
**Labels:** enhancement, area:tui, area:core, memory, autoclose

---

### Preflight Checklist

- [x] I have checked [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and confirmed that this feature has not already been proposed.  
- [x] This submission represents a single feature request (not multiple requests combined).

---

### Problem Statement

Achieving consistent and predictable outcomes with AI agents is often complicated by the heavy context load that accumulates during interactions with large codebases.  

A variety of strategies have been developed to mitigate this, including some already implemented in Claude Code—for example, context truncation, which summarizes previous conversation history to free up space for future tasks.  

However, experienced users of AI coding tools often develop their own informal “muscle memory” methods for managing context.  

In my case, my instinct is to start a new conversation whenever I sense that inference quality is deteriorating due to accumulated context—even when the theoretical context window is far from being reached. I’ve observed that this “tipping point” is usually reached well before the full context limit (which, while not visible in Claude Code, is exposed in other tools such as Gemini CLI).  

While this manual reset habit works as a practical workaround, it feels unnecessary. Ideally, users could trust that the agent is managing context intelligently—so that manual intervention to “reset” inference quality becomes obsolete.  

---

### Proposed Solution

Currently, when new tasks are added in Claude Code, they appear to be appended to a task list that the model processes within the same conversation. This list is visible in the UI, suggesting a sequential execution model within a single conversational thread.  

If, behind the scenes, Claude Code is actually spawning new conversations to handle certain tasks, this distinction would be valuable to surface to the user. Greater transparency about this behavior would allow users to make more informed decisions about how to structure their work and maintain inference quality.

Here’s a proposed modular approach that would give users explicit control over how tasks interact with context:

1. Task Hierarchy Options  
   Allow users to specify whether a new task should be created as:  
   - A new, standalone task  
   - A sub-task of the current task  
   - An add-on to an existing task  

   Suggested logic:  
   - Subtasks are executed within the current conversation as long as the context limit is not exceeded.  
   - When the limit is approached, context truncation is applied.  
   - If truncation would still compromise inference quality, a new conversation is automatically opened.

2. Automatic Context Reset for New Tasks  
   To simplify context management, new tasks could always be initiated in new conversations by default.  
   - These tasks would represent discrete, self-contained units of work that do not depend on the conversational history, but only on:  
     - The general project context (e.g., the codebase), and  
     - The persistent memory retained by Claude Code.  
   - This ensures that trailing context does not degrade performance and that each task begins with a clean, focused context.

The outcome would be that users have a clear understanding of how Claude Code handles task management and context allocation—leading to more predictable results, higher inference quality, and fewer of the issues caused by degraded context.

---

### Alternative Solutions

Manual management of conversations and task resets to approximate the above behavior.

---

### Priority

High — This feature would have a significant impact on productivity and reliability.

---

### Feature Category

Other

---

### Use Case Example

_No response._

---

### Additional Context

_No response._

