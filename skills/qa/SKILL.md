---
description: Lightweight QA pass - run happy path, catch obvious issues, log in Jira
argument-hint: <what to QA, or blank for current work>
---

# /qa - Lightweight QA Safety Net

A lightweight QA pass that saves Matt from his tendency to ship without checking. Runs the happy path, catches obvious issues, logs findings in Jira.

**This is not a gatekeeper. It's a safety net.**

## Core Behaviors

1. **Run the happy path** - Actually use the thing. Click through the main flow. Verify it works as intended.
2. **Catch obvious issues** - Broken links, wrong data showing, runtime errors, things that would embarrass you.
3. **Log bugs as Jira subtasks** - Don't just report in conversation. Create subtasks so they're tracked.
4. **Ask clarifying questions** - If something seems off but you're not sure, ask.
5. **Don't block on permissions** - If browser automation needs permission and Matt isn't there, create a subtask and move on.

## What Good QA Looks Like

- Lightweight - doesn't hold up shipping
- Finds real issues, not trivial cosmetic flaws
- Gets the item out the door
- Leaves a trail in Jira so nothing falls through cracks

## What to Skip

- Formal test case generation (too heavy)
- Accessibility audits (not a priority)
- Performance testing (not needed)
- Paranoid edge case hunting (these aren't production systems)
- Cosmetic nitpicks that don't matter

## Browser Automation

Use Claude in Chrome when it would help verify the feature:

- If permission needed and Matt isn't there: create subtask ("Browser test blocked - needs permission: [what to test]") and move on
- Don't let browser automation block the whole QA pass

## Output

1. **Findings go in Jira** - Create subtasks for bugs found
2. **Summary in conversation** - Quick recap of what was checked and found
3. **Don't get stuck** - If blocked, log a subtask and continue

## Philosophy

**Start somewhere and iterate.** This doesn't need to be perfect. Matt will refine the /qa command based on reality as he uses it.

---

**What to QA:** $ARGUMENTS
