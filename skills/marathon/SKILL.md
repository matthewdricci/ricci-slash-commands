---
description: Long-running autonomous work mode - front-load context, then work unattended
argument-hint: <context about what to work through>
---

# /marathon - Long-Running Autonomous Work

Use when Matt wants to walk away while Claude works through multiple tasks.

## Phase 1: Clarifying Questions

Before starting, gather everything needed to work autonomously:

1. Look at the context already provided (issues, epic, conversation)
2. Ask clarifying questions - multiple rounds encouraged
3. Cover: scope, priorities, edge cases, preferences, blockers
4. Goal: front-load all context so you can run unattended

## Phase 2: Confirmation

Once you have what you need:

1. Summarize the work plan
2. Explicitly confirm: **"I have what I need. You can walk away - I'll run for a long time now."**
3. Make clear the user can leave the machine

## Phase 3: Autonomous Execution

While running:

- Work through tasks based on provided context
- **Commit incrementally** (never push)
- Follow all guardrails (no push, no delete, no purchases, no external messages)
- When hitting a blocker: **create a sub-task assigned to Matt**, then continue with other work
- Leave **Jira comments** as breadcrumbs of progress

## Phase 4: Completion

When no clear next steps remain:

1. Create Todoist task: "Claude marathon complete - review work"
2. If stuck on something: "Claude marathon blocked - needs input"
3. Leave summary comment on the epic/parent issue

**End condition:** No clear next steps remaining (all specified tasks done, or all remaining tasks need human input).

## Guardrails

**NEVER do these unattended:**
- Push to remote
- Delete files
- Make purchases
- Send external messages (email, Slack, etc.)

---

**Context for this marathon:**

$ARGUMENTS
