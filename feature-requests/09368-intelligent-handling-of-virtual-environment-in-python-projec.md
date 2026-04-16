---
upstream_url: https://github.com/anthropics/claude-code/issues/9368
upstream_number: 9368
upstream_state: CLOSED
status: filed-closed-duplicate
created: 2025-10-11
closed: 2025-10-15
labels: [duplicate]
---

# [FEATURE] Intelligent handling of virtual environment in Python projects.

**Upstream:** [#9368](https://github.com/anthropics/claude-code/issues/9368) — `CLOSED` (closed-duplicate)
**Created:** 2025-10-11 • **Closed:** 2025-10-15
**Labels:** duplicate

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

When working with Python code generation tools (e.g., Claude, GPT, etc.), a recurring frustration is their tendency to default to system Python rather than using a virtual environment (venv). 

Even when workspace instructions explicitly request the use of a virtual environment (for example, by including a rule in Claude.md to always create and use a venv via UV), the agent often ignores these directions and installs packages into the system Python. 

Additionally, when a virtual environment is used, the agent frequently reactivates it before every shell command, rather than maintaining a persistent session. This is inefficient and unrepresentative of real developer workflows.


### Proposed Solution

Implement intelligent virtual environment management that mimics human developer behavior.

1. **Automatic Detection and Activation**
   - Detect an existing virtual environment by checking for standard folders like `.venv/`, `venv/`, or `.env/`.
   - Automatically activate the detected environment instead of creating a new one unnecessarily.

2. **Intelligent Creation**
   - If no environment exists, create one using the specified package manager (e.g., `uv venv` or `python -m venv`) before installing dependencies.

3. **Session-Persistent Activation**
   - Activate the venv once and persist the environment for the session.
   - All subsequent commands should execute within that activated environment, without repeated activation calls.

4. **Configurable Defaults**
   - Support configuration through workspace files (e.g., `.claude.md` or YAML-based workspace configs):
     ```yaml
     python:
       use_virtual_env: true
       manager: uv
       detect_existing_env: true
       persistent_activation: true
     ```


### Alternative Solutions

_No response_

### Priority

Medium - Would be very helpful

### Feature Category

CLI commands and flags

### Use Case Example

_No response_

### Additional Context

_No response_
