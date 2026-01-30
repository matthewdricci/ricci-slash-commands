# Ricci Slash Commands

My personal Claude Code slash commands. Built for how I actually work - as a PM who uses Claude Code as a capable co-worker, not a chatbot.

## Philosophy

These commands encode **my workflow preferences** so I don't have to repeat myself. They're opinionated. That's the point.

**The goal:** When I type `/jira KAN-123`, Claude knows to set the issue to "In Progress", do the work, leave breadcrumbs, and hand it back for my review. No explaining the workflow every time.

**The style:** Wes Kao, not PRD. These are notes to a co-worker, not formal documentation. Short paragraphs. Direct sentences. Bold the key point.

## The Commands

| Command | What it does |
|---------|-------------|
| `/jira` | Work on a Jira issue with my preferred workflow (status transitions, git behavior, guardrails) |
| `/create` | Create a Jira issue with my defaults |
| `/refine` | Turn rough thoughts into clean, parked items ready to review later |
| `/marathon` | Long-running autonomous work - front-load context, then work unattended |
| `/qa` | Lightweight QA pass - run happy path, catch obvious issues |
| `/todo` | Create a Todoist task via Zapier webhook |
| `/learn` | Capture learnings into the knowledge base |
| `/park` | End of session checklist - capture loose ends |
| `/basecamp` | Load context for Basecamp API work |

## Installation

Copy the `skills` folder to your Claude Code config:

```bash
cp -r skills/* ~/.claude/skills/
```

Or cherry-pick individual commands:

```bash
cp -r skills/refine ~/.claude/skills/
```

## Customization

These are templates, not gospel. Fork and make them yours:

- **Project keys** - I use `KAN` for my Jira project. Change it.
- **Webhook URLs** - `/todo` needs your Zapier webhook. See the file for setup instructions.
- **Names** - I reference "Matt Ricci" in some commands. Swap in your name.
- **Guardrails** - I have strong opinions about never pushing unattended. Adjust to your risk tolerance.

## What Makes These Different

Most Claude Code prompts are generic. These are **workflow-specific**:

1. **Status transitions baked in** - `/jira` knows my Jira workflow (Triage → In Progress → QA → Done)
2. **Git guardrails** - Commit liberally, never push. That's my safety barrier.
3. **Human-in-the-loop defaults** - Create subtasks for human work rather than blocking
4. **Breadcrumbs** - Leave Jira comments as progress markers so I can review later

## File Structure

```
skills/
├── basecamp/SKILL.md   # Basecamp API context
├── create/SKILL.md     # Jira issue creation
├── jira/SKILL.md       # Jira issue workflow
├── learn/SKILL.md      # Learning capture
├── marathon/SKILL.md   # Autonomous work mode
├── park/SKILL.md       # Session wrap-up
├── qa/SKILL.md         # QA workflow
├── refine/SKILL.md     # Rough → clean thoughts
└── todo/SKILL.md       # Todoist via webhook
```

## Contributing

PRs welcome. These are personal tools, so I'll merge what fits my workflow - but fork freely and make your own.
