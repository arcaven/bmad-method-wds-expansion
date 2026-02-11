# Module 16: Agentic Development

## Lesson 2: Documenting Decisions

**Creating agent dialogs that preserve context**

---

## What Are Agent Dialogs?

Agent dialogs are documentation of the conversations you have with AI during implementation.

They capture:
- The questions asked
- The decisions made
- The reasoning behind choices
- Changes from original specs

---

## Why This Matters

### Context Preservation

AI conversations are ephemeral. When the session ends, the context is gone.

Agent dialogs make that context permanent.

### Decision Rationale

Six months from now: "Why does the password toggle work this way?"

The answer is in the dialog, not someone's memory.

### Team Communication

Multiple people working on the project? Everyone can read the dialogs and understand what happened.

### Session Continuity

Starting a new AI session? Load the previous dialogs. Context carries forward.

---

## Dialog Structure

```markdown
# Agent Dialog: [Feature Name]

## Meta
- Date: [Date]
- Specification: [Spec reference]
- Status: In Progress / Complete
- Developer: [Name]

## Summary
Brief description of what was accomplished.

## Decisions Made

### [Decision Title]
- **Decision:** What was decided
- **Reason:** Why it was decided
- **Spec Impact:** Did this change the spec?

## Changes from Spec

| Element | Spec Said | Built As | Reason |
|---------|-----------|----------|--------|
| [Element] | [Original] | [New] | [Why] |

## Learnings
- Key insights from this implementation session
- Things to remember for future work

## Open Questions
- Unresolved issues for next session
```

---

## Example Dialog

```markdown
# Agent Dialog: Signup Form Implementation

## Meta
- Date: 2026-02-10
- Specification: P02-signup-form.md
- Status: Complete
- Developer: Mårten

## Summary
Implemented the signup form including all validation states.
Made two intentional deviations from spec based on accessibility
findings during development.

## Decisions Made

### Password Validation Timing
- **Decision:** Validate on blur, not on keypress
- **Reason:** Keypress validation was jarring and showed errors
  before user finished typing. Blur gives them a chance to complete.
- **Spec Impact:** Updated storyboard to reflect blur trigger

### Error Message Styling
- **Decision:** Changed from red text to red box with text
- **Reason:** Plain red text didn't meet contrast requirements
  against the light gray input background. Box provides contrast.
- **Spec Impact:** Updated visual spec, added to component docs

### Touch Target Size
- **Decision:** Increased submit button padding from 16px to 20px
- **Reason:** 16px padding resulted in 42px touch target, below
  the 44px minimum. 20px brings it to 48px.
- **Spec Impact:** Updated button component default

## Changes from Spec

| Element | Spec Said | Built As | Reason |
|---------|-----------|----------|--------|
| Error message | Red text #DC2626 | Red box with text | Accessibility contrast |
| Button padding | 16px | 20px | Touch target minimum |
| Validation trigger | On input | On blur | Better UX |

## Learnings
- Real-time validation needs careful timing consideration
- Always check contrast ratios before finalizing colors
- Touch targets are easy to undersize — measure, don't assume

## Open Questions
- None — this implementation is complete
```

---

## When to Document

### During Development

As you make decisions, write them down. Don't wait until the end — you'll forget the reasoning.

### At Session End

Before closing an AI session, summarize what was accomplished. Capture any open questions.

### When Changing Specs

Any time implementation causes a spec update, document why.

---

## Dialog File Organization

```
docs/F-Agent-Dialogs/
├── 2026-02-10-signup-form/
│   ├── dialog.md
│   ├── decisions.md
│   └── changes.md
├── 2026-02-11-welcome-screen/
│   └── dialog.md
└── 2026-02-12-password-reset/
    ├── dialog-part1.md
    └── dialog-part2.md
```

Date-prefixed folders keep dialogs organized chronologically.

Split long implementations into multiple files if needed.

---

## Loading Context in New Sessions

Starting a new AI session for continued work?

```
"I'm continuing implementation of the signup form. Here's the
previous dialog with decisions and current status:

[Paste relevant dialog content]

We left off at: [State where you stopped]

Next: [What you're doing now]"
```

This gives the AI full context without starting from scratch.

---

## The Idunn Method

Idunn helps you document effectively:

> "That's an interesting implementation choice. Let's document why we went with blur instead of keypress validation."

> "This differs from the spec. Is this intentional? Let me add it to the changes log."

> "Good session. Let me summarize what we accomplished and note the open questions for next time."

She makes documentation a natural part of the workflow, not an afterthought.

---

## What's Next

In the tutorial, you'll practice the agentic development loop — picking a spec, building it, reviewing against the spec, and documenting your decisions.

---

**[Continue to Tutorial: Build with Agent Dialogs →](tutorial-16.md)**

---

[← Back to Lesson 1](lesson-01-iterative-building.md) | [Back to Module Overview](module-16-agentic-development-overview.md)
