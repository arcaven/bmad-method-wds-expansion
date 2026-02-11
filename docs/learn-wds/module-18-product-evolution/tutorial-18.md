# Tutorial 18: Evolve Your Product

**Hands-on guide to implementing changes with creative discipline**

---

## Overview

This tutorial walks you through the evolution workflow — taking a change request from feedback through implementation.

**Time:** 20-30 minutes
**Prerequisites:** Completed implementation (Modules 16-17)
**Agent:** Idunn
**What you'll practice:** The complete evolution cycle

---

## Before You Start

**You'll need:**

- Your Trigger Map
- Your existing specifications
- A change request (real or example)

**Scenario for this tutorial:**

> "Users report the password requirements aren't clear. They don't know what makes a strong password until they try and fail."

---

## Step 1: Connect to Trigger Map (3 min)

### Trace the request to strategy:

**You say to Idunn:**
> "We have feedback: password requirements unclear. Let's connect this to our Trigger Map."

**Idunn analyzes:**
> "Looking at your Trigger Map...
>
> **Persona connection:** Felix the Full-Stack
> **Driving force:** 'Want to try before committing'
> **Fear:** Complicated onboarding that wastes time
>
> Unclear requirements cause friction during signup — directly opposing Felix's driving force."

### Confirm the connection:

This change serves an existing persona and addresses a known driving force. It should proceed.

---

## Step 2: Define the Change (5 min)

### Clarify what needs to change:

**Idunn:**
> "Current state:
> - Password field shows 'At least 8 characters' as helper text
> - Strength indicator appears only after typing
> - No explanation of what makes password strong
>
> Proposed change:
> - Show clear requirements upfront
> - Update helper text to list requirements
> - Keep strength indicator for feedback"

### Write the change spec:

```markdown
## Change Request: Password Requirements Clarity

### Problem
Users don't understand password requirements until they fail validation.

### Connection
- Persona: Felix
- Driving Force: Quick, frictionless onboarding
- Pain: Repeated failed attempts create frustration

### Proposed Solution
1. Update helper text to list requirements explicitly
2. Show requirements before user starts typing
3. Keep strength indicator as secondary feedback

### Affected Specs
- P02-signup-form.md (password field section)
```

---

## Step 3: Update Specification (5 min)

### Modify the existing spec:

**Before:**
```markdown
#### Password Field
- Type: Password input
- Label: "Password"
- Helper text: "At least 8 characters"
- Strength indicator: Appears on typing
```

**After:**
```markdown
#### Password Field
- Type: Password input
- Label: "Password"
- Helper text: "8+ characters, including a number and letter"
- Requirements shown: Always (not just on error)
- Strength indicator: Appears on typing, reinforces requirements
```

### Add to changelog:

```markdown
## Changelog

### v1.2 (2026-02-15)
- Changed: Password helper text now shows full requirements
- Changed: Requirements visible before user starts typing
- Reason: User feedback — unclear requirements causing friction
```

---

## Step 4: Implement the Change (5 min)

### Make the code change:

**Idunn:**
> "Updating the password field implementation..."

```jsx
<div className="form-field">
  <label htmlFor="password">Password</label>
  <input type="password" id="password" />
  <span className="helper-text">
    8+ characters, including a number and letter
  </span>
  <PasswordStrengthIndicator value={password} />
</div>
```

### Document in agent dialog:

```markdown
# Agent Dialog: Password Requirements Update

## Meta
- Date: 2026-02-15
- Change: Password requirements clarity
- Status: Complete

## Summary
Updated password field to show clear requirements upfront.

## Changes Made
- Helper text updated from "At least 8 characters" to
  "8+ characters, including a number and letter"
- Requirements now visible immediately (not just on error)

## Spec Updated
Yes — P02-signup-form.md v1.2
```

---

## Step 5: Test the Change (5 min)

### Verify against updated spec:

**Idunn:**
> "Testing the updated password field..."

### Checklist:

- [x] Helper text shows full requirements
- [x] Text visible before typing
- [x] Strength indicator still works
- [x] Validation errors still appear correctly
- [x] Error messages align with shown requirements

**Idunn:**
> "All checks pass. The change matches the updated specification."

---

## Step 6: Document and Close (3 min)

### Complete the change log:

```markdown
# Change: Password Requirements Clarity

## Request
Users reported password requirements unclear.

## Connection
Felix — frictionless onboarding driving force

## Solution
Updated helper text to show full requirements upfront.

## Implementation
- Spec updated: P02-signup-form.md v1.2
- Code updated: PasswordField component
- Dialog: 2026-02-15-password-requirements/dialog.md

## Testing
- Verified: Requirements visible
- Verified: Strength indicator works
- Verified: Validation still correct

## Status: Complete
```

### Update design system if needed:

If the change created a new pattern, add it:

```markdown
## Input Component Update

### Helper Text Patterns
- Validation requirements should be shown upfront
- Not just on error
- Use clear, actionable language
```

---

## The Complete Evolution Workflow

You've practiced:

1. **Connect** — Trace to Trigger Map
2. **Define** — Clarify the change
3. **Specify** — Update documentation
4. **Implement** — Make the change
5. **Test** — Verify against spec
6. **Document** — Record for history

This same workflow applies to every change, big or small.

---

## Avoiding Spec Drift

Over time, specs and reality can diverge.

### Prevention

- Update specs with every change
- Test regularly against specs
- Review specs quarterly

### Recovery (if specs get out of date)

1. Audit current implementation
2. Update specs to match reality
3. Document differences as intentional
4. Resume normal process

---

## You've Completed the WDS Course!

**Congratulations!** You've learned:

1. **The Paradigm Shift** — Design is the specification
2. **Strategy Phase** — Project Brief, Trigger Map, Platform Requirements
3. **Design Phase** — Scenarios, Sketches, Storyboards, Specifications, Components, Visuals, Delivery
4. **Implementation Phase** — Agentic Development, Testing, Evolution

---

## What You've Become

You're not just a designer anymore.

You're the keeper of creative discipline:
- Strategy traced through design
- Design expressed in specifications
- Specifications realized in code
- Code verified against specifications
- Evolution maintaining the chain

**You are the linchpin.**

---

## What's Next?

### Apply to a Real Project

The only way to truly learn is to do. Take a real project through the WDS workflow.

### Join the Community

- **Discord:** [discord.gg/whiteport](https://discord.gg/whiteport)
- **GitHub:** Report issues, suggest improvements
- **YouTube:** Watch tutorials and examples

### Contribute

WDS is open source. Your improvements help everyone.

### Teach Others

Spread creative discipline. Help other designers become linchpins.

---

## The Transformation

Remember where we started:

> "The design becomes the specification."
> "The specification becomes the product."
> "The code is just the printout."

You now have the methodology to make this real.

Go build something amazing.

---

**[← Back to Course Overview](../00-course-overview/00-course-overview.md)**

---

*Created by Mårten Angner and the Whiteport team*
*Part of the BMad Method ecosystem*
