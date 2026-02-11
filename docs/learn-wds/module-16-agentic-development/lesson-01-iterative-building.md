# Module 16: Agentic Development

## Lesson 1: Iterative Building

**From delivery package to working software**

---

## The Handoff

Freya's work is complete. Your delivery package is validated and ready.

Now Idunn takes over.

She'll coordinate between your design specifications and actual development, ensuring what gets built matches what you designed.

---

## The Old Way vs. The WDS Way

### Old Way

```
Design everything → Hand off → Wait → Review → Disappointment
```

The designer creates all the designs. Hands them off. Waits weeks or months. Gets back something that doesn't match. Frustrated rework begins.

### WDS Way

```
Design one thing → Build it → Review → Iterate → Next thing
```

Smaller loops. Faster feedback. Better outcomes.

Each element is designed, built, verified, then you move to the next. Issues are caught immediately, not weeks later.

---

## Meet Idunn

Idunn is your implementation partner. She:

- **Coordinates** between design and development
- **Tracks** what's built vs. what's specified
- **Documents** decisions along the way
- **Keeps** the feedback loop tight

She's the bridge between your design documents and working code.

---

## The Agentic Development Loop

```
┌─────────────┐
│  Pick spec  │  ← Choose one element to build
└──────┬──────┘
       │
       ▼
┌─────────────┐
│  Build it   │  ← Implement with AI assistance
└──────┬──────┘
       │
       ▼
┌─────────────┐
│  Review vs  │  ← Compare to specification
│    spec     │
└──────┬──────┘
       │
   Match? ─── No ──► Fix (implementation or spec)
       │
      Yes
       │
       ▼
┌─────────────┐
│ Document &  │  ← Record decisions, move on
│    next     │
└─────────────┘
```

This loop repeats for every element until the entire delivery is implemented.

---

## Build Order

Not everything should be built at once.

### 1. Core Happy Path First

Build the main functionality — what users do 90% of the time.

For a signup form:
- Form renders correctly
- User can enter email and password
- Submit works and redirects

### 2. Error States Second

Add what happens when things go wrong.

- Validation errors appear correctly
- Server errors are handled
- Network failures are managed

### 3. Edge Cases Third

Handle unusual but possible situations.

- Duplicate email detection
- Rate limiting
- Session timeout

### 4. Polish Last

Add the finishing touches.

- Animations and transitions
- Micro-interactions
- Performance optimizations

---

## One Thing at a Time

Don't build the whole page at once.

**Instead:**

1. Build the form layout
2. Verify layout matches spec
3. Build the email field
4. Verify email field behavior
5. Build the password field
6. Verify password field behavior
7. Build the submit button
8. Verify submit behavior
9. Connect everything
10. Verify full flow

Each step is small. Each step is verified. Problems are caught early.

---

## Spec Divergence

Sometimes implementation reveals issues with specs:

| Situation | Action |
|-----------|--------|
| **Spec unclear** | Clarify with Freya, update spec |
| **Spec impossible** | Update spec to reflect reality |
| **Better idea found** | Document, consider spec update |
| **Pure implementation detail** | Document, don't update spec |

**Never leave mismatches undocumented.**

If the implementation differs from spec, you must either:
- Fix the implementation to match
- Update the spec to reflect the change

Both are valid. Silence is not.

---

## Agent Dialogs

Document your AI conversations.

This is unique to agentic development — you're having extensive conversations with AI as you build. These conversations contain valuable context.

```
docs/F-Agent-Dialogs/
└── 2026-02-10-signup-form/
    ├── dialog.md           ← The conversation
    ├── decisions.md        ← What was decided
    └── changes.md          ← What changed from spec
```

---

## Why Document Dialogs?

### You'll Forget

"Why did we make the password field 20 characters max?"

The answer is in the dialog.

### Others Need Context

New team member joins. They can read the history and understand why things are the way they are.

### AI Context Carries Forward

Start a new session? Load the dialog. Context preserved. Less re-explaining.

---

## The Idunn Method

Idunn keeps you aligned:

> "The spec says 8 character minimum. You've implemented 6. Which is correct?"

> "This interaction isn't in the spec. Should we update the spec or remove the feature?"

> "Good implementation. Let's document why we chose shake animation."

She ensures specs and code stay synchronized throughout development.

---

## What's Next

In the next lesson, you'll learn how to structure agent dialogs and document decisions effectively.

---

**[Continue to Lesson 2: Documenting Decisions →](lesson-02-documenting-decisions.md)**

---

[← Back to Module Overview](module-16-agentic-development-overview.md)
