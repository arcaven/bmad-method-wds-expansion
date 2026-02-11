# Tutorial 16: Build with Agent Dialogs

**Hands-on guide to agentic development with Idunn**

---

## Overview

This tutorial walks you through the agentic development loop — building from specifications while documenting decisions.

**Time:** 45-60 minutes
**Prerequisites:** Design delivery package completed (Module 15)
**Agent:** Idunn
**What you'll create:** Working implementation with agent dialog documentation

---

## Before You Start

**You'll need:**

- Your delivery package from Module 15
- Development environment set up
- Access to your AI coding assistant

**Idunn will help you:**

- Compare implementation to specs
- Catch divergences
- Document decisions
- Maintain spec-code alignment

---

## Step 1: Create Dialog Folder (2 min)

### Set up documentation:

```
docs/F-Agent-Dialogs/
└── 2026-02-10-signup-form/
    └── dialog.md
```

### Initialize the dialog file:

```markdown
# Agent Dialog: Signup Form Implementation

## Meta
- Date: 2026-02-10
- Specification: P02-signup-form.md
- Status: In Progress

## Summary
[To be filled as we work]

## Decisions Made
[To be filled as we work]

## Changes from Spec
| Element | Spec Said | Built As | Reason |
|---------|-----------|----------|--------|
[To be filled as needed]

## Learnings
[To be filled at end]
```

---

## Step 2: Pick First Element (3 min)

### Start with the happy path:

**You say to Idunn:**
> "Let's implement the signup form from P02-signup-form.md. Starting with the basic form layout."

**Idunn acknowledges:**
> "I have the specification. Let's build the form structure first:
>
> **Elements to implement:**
> 1. Form container
> 2. Headline and subheadline
> 3. Email field
> 4. Password field
> 5. Submit button
> 6. Footer links
>
> Starting with the container and headlines."

---

## Step 3: Build and Verify (15 min)

### Build one element:

**Idunn generates:**
```jsx
<div className="signup-form">
  <h1>Start in 2 minutes</h1>
  <p className="subheadline">No credit card required. Cancel anytime.</p>
  {/* Form fields will go here */}
</div>
```

### Verify against spec:

**Idunn checks:**
> "Comparing to spec:
> - ✓ Headline matches: 'Start in 2 minutes'
> - ✓ Subheadline matches: 'No credit card required. Cancel anytime.'
> - ✓ Container structure correct
>
> Proceeding to email field."

### Continue building:

**Email field:**
```jsx
<div className="form-field">
  <label htmlFor="email">Email</label>
  <input
    type="email"
    id="email"
    placeholder="you@example.com"
    required
  />
</div>
```

**Verify:**
> "Email field:
> - ✓ Label: 'Email'
> - ✓ Placeholder: 'you@example.com'
> - ✓ Type: email
> - ✓ Required: yes
>
> Matches spec."

---

## Step 4: Handle Divergence (5 min)

### Discover an issue:

**Idunn notes:**
> "Building the password field with strength indicator. The spec shows the indicator below the field. In the generated HTML, it renders to the right of the field.
>
> Should we:
> 1. Adjust CSS to match spec (below)
> 2. Update spec to reflect implementation (right)
> 3. Discuss which is better UX"

**You respond:**
> "Let's keep it below as per spec. That gives more room for the strength text on mobile."

**Idunn:**
> "Adjusting layout. Documenting this as a considered decision."

### Document the decision:

**Add to dialog:**
```markdown
### Strength Indicator Position
- **Decision:** Keep indicator below field, not beside
- **Reason:** More room for text on mobile, matches original spec
- **Spec Impact:** None (spec followed)
```

---

## Step 5: Complete Core Implementation (10 min)

### Finish all elements:

**Idunn tracks:**
> "Implementation status:
> - ✓ Form container
> - ✓ Headlines
> - ✓ Email field
> - ✓ Password field with strength indicator
> - ✓ Submit button
> - ✓ Terms link
> - ✓ Login link
>
> Core happy path complete. Moving to validation states."

### Add validation:

**Idunn:**
> "Implementing validation. Spec says:
> - Empty email: 'Email is required'
> - Invalid email: 'Please enter a valid email'
> - Empty password: 'Password is required'
> - Short password: 'Password must be at least 8 characters'
>
> When should validation trigger? Spec says real-time, but that could mean on input or on blur."

**You respond:**
> "On blur is less jarring. Let's do that."

**Document:**
```markdown
### Validation Timing
- **Decision:** Trigger validation on blur, not on input
- **Reason:** Input validation shows errors while user is still typing, which is jarring
- **Spec Impact:** Update storyboard to clarify blur trigger
```

---

## Step 6: Test Against Spec (10 min)

### Run through checklist:

**Idunn:**
> "Let's verify the implementation against spec:
>
> **Content:**
> - ✓ Headlines match
> - ✓ Labels match
> - ✓ Button text matches
> - ✓ Error messages match
> - ✓ Helper text matches
>
> **States:**
> - ✓ Default renders correctly
> - ✓ Hover states work
> - ⚠️ Loading state: spinner is smaller than spec shows
> - ✓ Disabled state correct
> - ✓ Error states display correctly
>
> **Issue found:** Spinner size differs from spec."

### Resolve issue:

**You respond:**
> "What size is the spinner currently vs. spec?"

**Idunn:**
> "Current: 16px. Spec: 20px. Should I increase it?"

**You respond:**
> "Yes, match the spec."

**Idunn fixes and verifies.**

---

## Step 7: Document Learnings (5 min)

### Capture insights:

**Idunn:**
> "Implementation complete. Let's document what we learned."

**Add to dialog:**
```markdown
## Learnings

- Blur validation is better UX than input validation for forms
- Always check loading spinner sizing against spec
- Mobile touch targets need explicit sizing — don't rely on defaults
- Password strength indicators need careful color contrast checking

## Open Questions

- None — implementation matches spec
```

### Update summary:

```markdown
## Summary

Implemented the signup form with all validation states.
Made one intentional deviation (blur validation instead of
ambiguous "real-time"). Updated storyboard to clarify.
Fixed one implementation bug (spinner size).
```

---

## Step 8: Finalize Dialog (5 min)

### Complete the documentation:

**Final dialog file:**
```markdown
# Agent Dialog: Signup Form Implementation

## Meta
- Date: 2026-02-10
- Specification: P02-signup-form.md
- Status: Complete

## Summary
Implemented the signup form with all validation states.
Made one intentional deviation (blur validation instead of
ambiguous "real-time"). Updated storyboard to clarify.
Fixed one implementation bug (spinner size).

## Decisions Made

### Validation Timing
- **Decision:** Trigger validation on blur, not on input
- **Reason:** Input validation shows errors while user is still typing
- **Spec Impact:** Updated storyboard to clarify blur trigger

### Strength Indicator Position
- **Decision:** Keep indicator below field, not beside
- **Reason:** More room for text on mobile
- **Spec Impact:** None (spec followed)

## Changes from Spec

| Element | Spec Said | Built As | Reason |
|---------|-----------|----------|--------|
| Validation trigger | "Real-time" | On blur | Clarified ambiguous spec |

## Learnings

- Blur validation is better UX than input validation
- Always check loading spinner sizing against spec
- Mobile touch targets need explicit sizing
- Color contrast requires verification, not assumption
```

---

## What You've Created

### Implementation:

- Working signup form
- All states functional
- Matches specification

### Documentation:

- Complete agent dialog
- Decisions recorded with reasoning
- Spec updates noted
- Learnings captured

---

## Tips for Success

**DO:**

- Document as you go, not at the end
- Verify each element against spec
- Record every intentional divergence
- Capture learnings for future reference

**DON'T:**

- Build everything then check
- Leave divergences undocumented
- Assume spec is always right
- Skip the verification step

---

## You've Completed Module 16!

**Your first agentic development loop is complete.** You've:
- Built from specification
- Documented decisions
- Maintained spec-code alignment
- Created reusable context

---

## Next Module

**[Module 17: Testing →](../module-17-testing/module-17-testing-overview.md)**

Verify that implementation matches design systematically.

---

[← Back to Lesson 2](lesson-02-documenting-decisions.md) | [Back to Module Overview](module-16-agentic-development-overview.md)
