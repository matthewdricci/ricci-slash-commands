---
description: Create a Jira issue with proper defaults and validation
argument-hint: <description of what to create>
---

# /create - Jira Issue Creation

Create a new Jira issue with Matt's preferred defaults and workflow.

## Before Creating

1. **Ask clarifying questions** - Don't assume. Understand what's being asked.
2. **Search for related items** - Look for existing epics or issues that this might link to or combine with.
3. **Propose connections** - Suggest parent epics or related items if relevant.

## Required Behaviors

- Always use project **KAN**
- Put new items in status **"Triage"**
- Use **Jira wiki markup** (NOT markdown) for descriptions
- Validate required fields are populated
- Double-check before linking or merging content
- **Titles must be action phrases** starting with a verb

## Title Formatting

Jira card titles must start with an action verb. This makes the backlog scannable and clarifies what "done" means.

**Good titles:**
- "Create admin view for adoption metrics"
- "Add early check-in auto-messages"
- "Fix login redirect bug"
- "Build Turno webhook handler"

**Bad titles:**
- "Admin view for adoption metrics"
- "Early check-in messages"
- "Login redirect bug"
- "Turno webhook handler"

## Jira Wiki Markup Reference

**Future Claude: Jira uses wiki markup, NOT markdown.**

| Element | Jira Syntax |
|---------|-------------|
| Heading 1 | `h1. Heading` |
| Heading 2 | `h2. Heading` |
| Heading 3 | `h3. Heading` |
| Bold | `*bold*` |
| Italic | `_italic_` |
| Inline code | `{{code}}` |
| Numbered list | `#` at line start |
| Bullet list | `*` at line start |
| Link | `[text\|url]` |
| Quote | `{quote}text{quote}` |
| Code block | `{code}code{code}` |
| Table header | `\|\|header\|\|` |
| Table cell | `\|cell\|` |

**Known issue with Atlassian MCP:**
- The `#` character for numbered lists gets converted to `h1.` headings by the MCP tool
- **Workaround:** Use bullet points (`*`) instead of numbered lists (`#`) until this is fixed
- See KAN-72 for tracking

**Common mistakes to avoid:**
- Do NOT use `h1.` for numbered list items (it creates a heading)
- Avoid `#` for numbered lists due to MCP bug - use `*` bullet points instead
- Tables use `||` for headers and `|` for cells

## After Creating: Link to Epic When Relevant

If the user's request mentioned an **epic**, **project**, or **repo** (e.g. bth-messaging, Home Assistant, ricci-slash-commands, ATH_Agent, Strategy), **link the new issue to the appropriate epic**:

1. Call **jira_link_to_epic**(issue_key, epic_key) with the newly created issue key and the correct epic key.
2. If unsure which epic, list options or ask (e.g. "Link to epic? Options: KAN-238 Home Assistant, KAN-264 Strategy, KAN-18 Personal Productivity").
3. Err on linking when the context is clear (e.g. "create a card for the good morning weather" → KAN-238).

**Epic reference (KAN):** Home Assistant Voice = KAN-238, Strategy/Research/Positioning = KAN-264, Matt's Personal Productivity = KAN-18, BTH Ops = KAN-224, BTH App Phase 2 = KAN-154, Turno = KAN-246, BTH Status Board = KAN-155. Use jira_search or jira_get_project_issues if you need to find an epic by name.

Tracking: Bug KAN-265 — Create/Jira flow was not linking to epics; this section is the fix.

## Definition of Done (Reminder for Future Work)

When this issue is eventually completed, consider:
- Does the application's **public changelog** and/or the **private code repo changelog** need an update? Err on yes.

## Output

When creating, confirm:
1. Summary/title
2. Description (in wiki markup)
3. Epic link (if applicable — and actually call jira_link_to_epic)
4. Status will be set to Triage

$ARGUMENTS
