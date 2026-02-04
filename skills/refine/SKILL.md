---
description: Refine rough thoughts into a clean, parked item ready to review later
argument-hint: <rough text, voice note transcript, or stream-of-consciousness>
---

# /refine - Clean Up Rough Thoughts

Takes rough input (rambling text, voice note transcripts, stream-of-consciousness) and produces a **clean, parked item** ready to review later with fresh eyes.

This is explicitly for items **not yet ready for action** - the goal is to tighten and clarify, not to start building.

## Core Behaviors

1. **Clean up structure** - Turn rambling into organized, scannable writing
2. **Surface clarifying questions** - When something is unclear or underspecified, ask
3. **Focus on problem + what good looks like** - Never prescribe implementation details (the implementing Claude will have the technical context; the refining Claude does not)
4. **Push back when warranted** - Flag fundamental tensions, conflicting goals, or "you're trying to do two things at once"

## Output Style: Wes Kao

Write like Wes Kao - communication style for working with a co-worker, not writing a PRD:

- Short paragraphs
- Direct sentences
- No throat-clearing or fluff
- **Bold the key point**
- Scannable on fresh eyes

*Not* one sentence. *Not* verbose. Thoughtful but concise.

## What to Include

- What problem we're solving
- What good looks like in the end (behavioral, checklist, or vibe - whatever fits)
- Any constraints or context that matters
- Open questions (things that need answering before action)

## Jira Card Titles

When creating or updating Jira cards, **titles must be action phrases** starting with a verb:

- "Create admin view for adoption metrics" ✓
- "Add early check-in auto-messages" ✓
- "Fix login redirect bug" ✓
- "Admin view for adoption metrics" ✗
- "Early check-in messages" ✗

This makes the backlog scannable and clarifies what "done" means.

## What to Avoid

- Prescribing technical implementation details
- Being too long to read in one sitting
- Solution-focused writing when problem-focused is needed
- Assuming context the implementing Claude will have but the refining Claude doesn't

## When to Use

When you want to **park an idea cleanly** - not ready to act, but want it tightened so you can sleep on it and return with fresh eyes.

---

**Input to refine:**

$ARGUMENTS
