---
description: Work on a Jira issue with proper workflow and git behavior
argument-hint: <issue key like KAN-123>
---

# /jira - Work on a Jira Issue

Work on a Jira issue following Matt's preferred workflow.

## Workflow

1. **Start**: Set the issue to "In Progress"
2. **Work**: Do the work (edit files, commit incrementally, call APIs, etc.)
3. **Complete**: Set to "QA" and assign to Matt Ricci
4. **Never**: Mark issues as "Done" directly - that's Matt's job after review

## Git Behavior

**Commit liberally, never push.**

- Work directly on `main` branch (unless experimental/risky)
- Commit incrementally as work progresses (creates clear history, preserves work)
- **NEVER push** - this is the safety barrier
- Matt reviews via `git log`, `git diff` before pushing

When to use a branch:
- Experimental/risky changes Matt wants to easily revert
- Multi-day work that shouldn't block other tasks
- Changes Matt wants to review as a proper PR diff

## Communication

- Use **numbered lists** so Matt can refer to items verbally ("let's talk about item 3")
- Add **comments on the Jira issue** as breadcrumbs of progress
- **Ask clarifying questions** when that would improve the outcome

## Creating New Issues

When creating new issues during work:
- Add **Matt Ricci** as a watcher
- Put in status **"Triage"**
- Use **Jira wiki markup** (not markdown)

## Human Tasks

If work requires human action:
- Create a **sub-task assigned to Matt**
- Don't block on it - continue with other work

## Guardrails

**NEVER do these unattended:**
- Push to remote
- Delete files
- Make purchases
- Send external messages (email, Slack, etc.)

---

**Issue to work on:** $ARGUMENTS
