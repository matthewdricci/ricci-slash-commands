---
description: Capture learnings from this session into the knowledge base
argument-hint: <what was learned>
---

# /learn - Capture Learnings

A command for capturing learnings from actions taken during a session.

## When Invoked

1. **Acknowledge** what was learned
2. **Look at** the current repository AND global Claude Code settings
3. **Determine** the best place to capture the learning so it's repeatable next time
4. **Ask clarifying questions** to document it correctly
5. **Prefer global-level** capture over repo-level unless truly project-specific

## Where to Capture

| Type of Learning | Location |
|------------------|----------|
| API behavior/quirks (Basecamp, Linear, etc.) | Global Claude Code settings |
| Auth flow patterns | Global |
| General tool behaviors | Global |
| Project-specific IDs, mappings | Repo-level |
| Workflow specific to one project | Repo-level |

## Format

- **Markdown**, matching the repository conventions
- Claude proposes the specific format based on context
- Keep it scannable and actionable

## Follow-ups

- **Do NOT create Linear issues** (migrating to Atlassian)
- Create **Jira issues** for follow-ups if needed

## Examples of Learnings Worth Capturing

- "Jira uses wiki markup, not markdown"
- "PUT requests to Basecamp replace all fields"
- "This project uses snake_case for API fields"
- "The webhook expects deadline_date, not due_date"

---

**What was learned:** $ARGUMENTS
