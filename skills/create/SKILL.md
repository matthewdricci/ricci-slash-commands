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

## Output

When creating, confirm:
1. Summary/title
2. Description (in wiki markup)
3. Any suggested links or parent epic
4. Status will be set to Triage

$ARGUMENTS
