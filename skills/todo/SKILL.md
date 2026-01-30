---
description: Create a Todoist task via Zapier webhook
argument-hint: <task title>
---

# /todo - Create Todoist Task

Shorthand for creating Todoist tasks via Zapier webhook.

## Quick Reference

**Endpoint:** `{{YOUR_ZAPIER_WEBHOOK_URL}}`

**Schema:**
```json
{
  "task": "Task title (required)",
  "description": "Task description with context",
  "deadline_date": "YYYY-MM-DD",
  "priority": "p1|p2|p3|p4",
  "labels": ["source-label", "context-labels"]
}
```

## Rules

1. Always include source in labels: `["ClaudeCode"]`
2. Use `deadline_date` (not `due_date`) - Zapier is configured for this field
3. End descriptions with source attribution: `\n\n---\nSource: ClaudeCode`
4. Labels must be an array, even for single labels: `["ClaudeCode"]`
5. Project is hardcoded to Inbox in Zapier

## Example: Simple Task

```bash
curl -X POST "{{YOUR_ZAPIER_WEBHOOK_URL}}" \
  -H "Content-Type: application/json" \
  -d '{
    "task": "Call the plumber",
    "labels": ["ClaudeCode"]
  }'
```

## Example: With Deadline and Priority

```bash
curl -X POST "{{YOUR_ZAPIER_WEBHOOK_URL}}" \
  -H "Content-Type: application/json" \
  -d '{
    "task": "Review quarterly report",
    "deadline_date": "2026-02-15",
    "priority": "p2",
    "labels": ["ClaudeCode"]
  }'
```

## Setup: Zapier Webhook

To use this command, create a Zapier webhook that posts to Todoist:

1. Create a new Zap with **Webhooks by Zapier** as trigger (Catch Hook)
2. Add **Todoist** action: Create Task
3. Map fields: `task` → Task Content, `deadline_date` → Due Date, etc.
4. Replace `{{YOUR_ZAPIER_WEBHOOK_URL}}` with your webhook URL

**Design rationale:**
- Simple so it works every time
- One-way so no possibility of havoc (worst case: someone fills your inbox, which you keep tidy anyway)

## When to Use

**Use when:**
- User explicitly asks to create a Todoist task
- A clear action item emerges that should be tracked
- Marathon mode completes or gets stuck (signal to Matt)

**Don't use when:**
- User is just discussing possibilities
- Action is immediate and will be done now
- Content is better suited as notes/documentation

---

**Task to create:** $ARGUMENTS
