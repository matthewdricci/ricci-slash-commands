---
description: Work on a Jira issue with proper workflow and git behavior
argument-hint: <issue key like KAN-123>
---

# /jira - Work on a Jira Issue

Work on a Jira issue following Matt's preferred workflow.

## Workflow

1. **Pre-flight**: Check for uncommitted changes in current directory. If dirty, stop and ask Matt to commit/stash first.
2. **Worktree**: Set up isolated worktree (see Git Behavior below)
3. **Start**: Set the issue to "In Progress"
4. **Work**: Do the work (edit files, commit incrementally, call APIs, etc.)
5. **Complete**: Set to "QA" and assign to Matt Ricci
6. **Never**: Mark issues as "Done" directly - that's Matt's job after review

## Git Behavior

**Use worktrees for isolation. Commit liberally, never push.**

### Worktree Setup (for concurrent sessions)

Before starting work, set up an isolated worktree:

1. **Check the main repo location** - find the root of the git repo
2. **Create worktree** at `~/.claude-worktrees/<repo-name>/<issue-key>/`
   ```bash
   git worktree add ~/.claude-worktrees/<repo-name>/<issue-key> -b <issue-key>
   ```
3. **Work in that directory** for all file edits and commits
4. If worktree already exists, just `cd` into it

This keeps concurrent Claude Code sessions isolated - each issue gets its own branch and working directory.

### Committing

- Commit incrementally as work progresses (creates clear history, preserves work)
- **NEVER push** - this is the safety barrier
- Matt reviews via `git log`, `git diff` before pushing
- When done, Matt merges the branch to main manually

## Communication

- Use **numbered lists** so Matt can refer to items verbally ("let's talk about item 3")
- Add **comments on the Jira issue** as breadcrumbs of progress
- **Ask clarifying questions** when that would improve the outcome

## Creating New Issues

When creating new issues during work:
- Add **Matt Ricci** as a watcher
- Put in status **"Triage"**
- Use **Jira wiki markup** (not markdown)
- **Link to epic when relevant** — If the work or user mention implies an epic/repo (e.g. bth-messaging, Home Assistant, ricci-slash-commands, Strategy), call **jira_link_to_epic**(issue_key, epic_key) after create. See create skill for epic reference. Bug tracking: KAN-265.

## Human Tasks

If work requires human action:
- Create a **sub-task assigned to Matt**
- Don't block on it - continue with other work

## Definition of Done

Before marking work complete (moving to QA):
- Consider if the application's **public changelog** and/or the **private code repo changelog** needs an update. Err on yes.

## Guardrails

**NEVER do these unattended:**
- Push to remote
- Delete files
- Make purchases
- Send external messages (email, Slack, etc.)

---

**Issue to work on:** $ARGUMENTS
