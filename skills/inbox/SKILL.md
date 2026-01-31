---
description: Process inbox/outbox folders in current directory
argument-hint: [optional: specific item to process]
---

# /inbox - Directory Inbox/Outbox Processing

Process items in the inbox folder of the current directory, then propose cleanup for stale outbox items.

## Phase 1: Inbox Processing

### Step 1: Find the Inbox

Look for inbox folder (case-insensitive):
- `inbox/` or `Inbox/`
- `0 - Inbox/` (Obsidian vault convention)

If no inbox found, report this and stop.

### Step 2: Find Processing Instructions

Search for instructions in this order:
1. README in the inbox folder itself
2. SKILL file in the inbox folder (e.g., `SKILL - Inbox Processing.md`)
3. README in parent directory's `_Inbox Tools/` subfolder
4. Parent directory's README

If instructions found, follow them exactly.

### Step 3: No Instructions (Smart Default)

If no README or SKILL found anywhere:
1. List inbox contents
2. Propose routing based on file types:
   - `.md` files: Review content and suggest destination
   - `.csv`/`.xlsx` files: Ask what to do with them
   - Images: Ask if they belong to a project
   - Audio: Check if transcription is possible
   - Other: Ask for guidance

### Step 4: Process Items

Follow the instructions to process each item. Common patterns:
- **Route**: Move file to appropriate destination
- **Mark processed**: Rename with `LLM-PROCESSED - ` prefix
- **Archive**: Move to `_archive/` or `9 - Archive/`
- **Delete**: Move to `.trash/` (never hard delete)

## Phase 2: Outbox Cleanup

Only proceed to Phase 2 if inbox is empty (or only contains `.DS_Store`).

### Step 1: Find the Outbox

Look for outbox folder (case-insensitive):
- `outbox/` or `Outbox/`

If no outbox found, report "Inbox clear, no outbox found" and stop.

### Step 2: Check for Stale Items

Outbox items are files Claude produced for Matt to review.

For each item, propose one of:
- **Archive**: Item was reviewed, move to `_archive/`
- **Delete**: Item is no longer needed
- **Migrate**: Content should become a Jira issue
- **Keep**: Still pending review (explain why)

### Step 3: Confirm Before Acting

Present the cleanup plan as a numbered list. Wait for Matt's approval before taking action.

## Known Inbox Locations

These directories have inbox/outbox patterns:

| Location | Inbox Path | Notes |
|----------|------------|-------|
| Vault | `0 - Inbox/` | Has `_Inbox Tools/SKILL - Inbox Processing.md` with routing table |
| ATH Agent | `Inbox/` | Incoming docs for property management |
| ClaudeCodeAgentSpace | `Inbox/` | Working files for Claude Code sessions |

## Critical Rules

- **Never hard delete**: Always move to `.trash/` or archive
- **Follow existing instructions**: If a SKILL or README exists, use it
- **Ask when uncertain**: Don't guess at routing for ambiguous items
- **Report clearly**: Use numbered lists so Matt can reference items verbally

$ARGUMENTS
