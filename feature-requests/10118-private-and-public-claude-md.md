---
upstream_url: https://github.com/anthropics/claude-code/issues/10118
upstream_number: 10118
upstream_state: CLOSED
status: filed-closed-stale
created: 2025-10-22
closed: 2026-01-08
labels: [enhancement, area:core, area:security, autoclose]
---

# [FEATURE] Private and public CLAUDE.md

**Upstream:** [#10118](https://github.com/anthropics/claude-code/issues/10118) — `CLOSED` (closed-stale)
**Created:** 2025-10-22 • **Closed:** 2026-01-08
**Labels:** enhancement, area:core, area:security, autoclose

---

### Preflight Checklist

- [x] I have searched [existing requests](https://github.com/anthropics/claude-code/issues?q=is%3Aissue%20label%3Aenhancement) and this feature hasn't been requested yet
- [x] This is a single feature request (not multiple features)

### Problem Statement

Claude Code uses `CLAUDE.md` files to provide project-specific context and instructions. However, there is currently no native support for separating public instructions (suitable for version control and sharing) from private instructions (containing sensitive information, personal preferences, or PII filters).

## The Challenge

Users face a dilemma when working with Claude Code in public repositories:

1. **Security Risk**: Including sensitive information (API keys, personal data, PII filters, private system details) in `CLAUDE.md` risks accidentally committing this data to public repositories
2. **Manual Management**: Users must manually maintain separate instruction files and remember which information belongs in public vs. private contexts
3. **No Built-in Mechanism**: There is no standardized approach for managing private Claude instructions across multiple repositories
4. **Workflow Friction**: Users need to constantly be vigilant about what they include in `CLAUDE.md`, creating cognitive overhead and potential security vulnerabilities

## Current Workaround

The current workaround requires:
- Creating a custom global gitignore pattern for `CLAUDE_PRIVATE.md`
- Manual setup scripts to configure this pattern
- User education about the distinction between public and private files
- No guidance from Claude Code itself about this pattern

## Impact

Without native support for private instruction files:
- Users may accidentally commit sensitive information
- There's no consistent pattern across the Claude Code community
- Setup is manual and error-prone
- New users have no way to discover this capability
- The security model relies entirely on user vigilance rather than built-in safeguards

### Proposed Solution

Claude Code should natively support a dual-file configuration system with built-in security safeguards.

## Implementation Idea

### 1. Automatic Recognition

Claude Code should automatically recognize and load both files:
- `CLAUDE.md` - Public project instructions (tracked by git)
- `CLAUDE_PRIVATE.md` - Private instructions (automatically excluded from git)

### 2. Built-in Gitignore Management

When Claude Code is initialized or first detects a repository:
- Automatically check if `CLAUDE_PRIVATE.md` is in the user's global gitignore
- If not, prompt the user: "Would you like to configure git to automatically ignore CLAUDE_PRIVATE.md files globally?"
- If confirmed, automatically add to global gitignore and configure git

### 3. File Creation Assistance

When users create `CLAUDE.md` files, Claude Code could:
- Suggest creating a companion `CLAUDE_PRIVATE.md` file
- Provide a template explaining the distinction
- Offer to set up the global gitignore pattern if not already configured

### 4. Visual Indicators

In any Claude Code interface or output:
- Clearly indicate when instructions are being read from `CLAUDE_PRIVATE.md`
- Show visual distinction between public and private context sources
- Warn users if they're about to commit content that references private instructions

### 5. Documentation and Best Practices

Official Claude Code documentation should include:
- Clear explanation of the dual-file pattern
- Security best practices for managing private instructions
- Examples of what belongs in each file
- Migration guide for existing users

## Benefits

### For Users
- **Security by Default**: Private information is automatically protected
- **Zero Configuration**: Works out of the box after one-time setup
- **Consistent Pattern**: Standardized approach across all repositories
- **Peace of Mind**: No more worrying about accidentally committing sensitive data

### For the Community
- **Established Pattern**: Creates a community-wide standard
- **Better Examples**: Public repositories can safely share `CLAUDE.md` files
- **Reduced Risk**: Fewer incidents of leaked credentials or PII
- **Improved Adoption**: Easier onboarding for new users

## Alternative Approaches

### Option A: Single File with Sections
Use comments or markers in `CLAUDE.md` to denote private sections.
- **Pros**: Single file to manage
- **Cons**: More complex parsing, higher risk of accidental commits, no file-level gitignore protection

### Option B: Environment Variables
Store private instructions in environment variables.
- **Pros**: Well-established pattern in software development
- **Cons**: Not suitable for large instruction sets, harder to maintain, less readable

### Option C: Encrypted Sections
Allow encrypted sections within `CLAUDE.md`.
- **Pros**: Single file, cryptographically secure
- **Cons**: Complex implementation, key management overhead, breaks readability

## Recommended Approach

**The dual-file system (CLAUDE.md + CLAUDE_PRIVATE.md)** is recommended because it:
- Leverages existing git infrastructure
- Provides clear separation of concerns
- Requires minimal implementation complexity
- Maintains readability and editability
- Follows the principle of least surprise
- Can be implemented incrementally without breaking existing workflows

## Migration Path

For existing users:
1. Detect presence of `CLAUDE.md` without `CLAUDE_PRIVATE.md`
2. Analyze content for potentially sensitive patterns (API keys, personal info, etc.)
3. Suggest splitting the file with preview of recommended split
4. Automate the migration with user confirmation

## Implementation Priority

1. **Phase 1**: Automatic loading of `CLAUDE_PRIVATE.md` if present
2. **Phase 2**: Global gitignore setup assistant
3. **Phase 3**: File creation wizard and suggestions
4. **Phase 4**: Visual indicators and warnings
5. **Phase 5**: Migration assistant for existing users


### Alternative Solutions

_No response_

### Priority

Low - Nice to have

### Feature Category

CLI commands and flags

### Use Case Example

_No response_

### Additional Context

_No response_
