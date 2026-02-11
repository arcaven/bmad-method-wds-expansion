# Tutorial 17: Test Your Implementation

**Hands-on guide to verifying implementation against specifications**

---

## Overview

This tutorial walks you through testing an implemented page against its specification.

**Time:** 30-40 minutes
**Prerequisites:** Implementation completed (Module 16)
**Agent:** Idunn
**What you'll create:** Test results document with verified acceptance criteria

---

## Before You Start

**You'll need:**

- Your page specification
- Your acceptance criteria
- Access to the running implementation
- Browser developer tools

**Idunn will help you:**

- Compare systematically
- Catch details
- Document findings
- Prioritize issues

---

## Step 1: Set Up Test Session (3 min)

### Create test results file:

```markdown
# Test Results: S01-User-Registration

## Tested: [Today's date]
## Tester: [Your name]
## Status: In Progress

## P02: Signup Form

### Content
[To be filled]

### States
[To be filled]

### Interactions
[To be filled]

### Visual
[To be filled]

## Actions Required
[To be filled]
```

### Open both views:

- Specification in one window
- Implementation in another
- Side by side if possible

---

## Step 2: Content Testing (5 min)

### Check every piece of text:

**You say to Idunn:**
> "Let's test the signup form. Starting with content verification."

**Idunn guides:**
> "Checking content against spec P02-signup-form.md..."

### Go through each element:

| Element | Spec Says | Implementation | Match? |
|---------|-----------|----------------|--------|
| Headline | "Start in 2 minutes" | "Start in 2 minutes" | ✓ |
| Subheadline | "No credit card required. Cancel anytime." | "No credit card required. Cancel anytime." | ✓ |
| Email label | "Email" | "Email" | ✓ |
| Email placeholder | "you@example.com" | "you@example.com" | ✓ |
| Password label | "Password" | "Password" | ✓ |
| Submit button | "Create Free Account" | "Create Free Account" | ✓ |
| Terms text | "By continuing, you agree to our Terms and Privacy Policy" | "By continuing, you agree to our Terms and Privacy Policy" | ✓ |
| Login link | "Already have an account? Log in" | "Already have an account? Log in" | ✓ |

**Idunn:**
> "Content check complete. All text matches specification. ✓"

---

## Step 3: State Testing (10 min)

### Test each state:

**Idunn:**
> "Now testing all states. I'll guide you through each one."

### Default State

> "Load the page fresh. Does the default state match?"

Check:
- Form is empty
- Button is disabled
- No validation messages
- Focus not yet in any field

### Focus States

> "Tab to the email field. Is focus visible?"

Check:
- Outline appears (2px blue per spec)
- Outline has offset
- Visible on all interactive elements

### Validation States

> "Enter an invalid email, then blur the field. Does error appear?"

Check:
- Error message appears
- Correct text: "Please enter a valid email"
- Correct styling (red, below field)
- Field border turns red

### Loading State

> "Submit a valid form. Does loading state appear?"

Check:
- Spinner appears in button
- Button becomes disabled
- Form fields disabled
- No new input allowed

### Success State

> "Let submission complete. Does success state appear before redirect?"

Check:
- Brief success indication
- Redirect happens after ~1.5s
- No jarring transitions

---

## Step 4: Interaction Testing (5 min)

### Test user flows:

**Idunn:**
> "Testing interactions now."

### Form Validation

Try:
- Submit with empty form → Button disabled, can't submit
- Enter email only → Button still disabled
- Enter valid email + short password → Password error shows
- Enter valid email + valid password → Button enables

### Keyboard Navigation

> "Navigate entire form using only keyboard."

Check:
- Tab moves through all fields in order
- Enter submits the form
- Escape has appropriate behavior (if modal)
- All states accessible via keyboard

### Click Behaviors

> "Click the terms link. Does it work?"

Check:
- Terms link opens terms page/modal
- Privacy link opens privacy page/modal
- Login link navigates to login

---

## Step 5: Visual Testing (5 min)

### Compare layout:

**Idunn:**
> "Comparing visual layout to specification."

### Check Layout

- Element positioning matches
- Spacing is consistent
- Alignment is correct

### Check Responsive

> "Resize browser to mobile size."

Check:
- Layout adapts correctly
- Elements stack appropriately
- Touch targets remain adequate

### Check Colors

Use browser dev tools:

- Primary button: Should be #0066FF
- Error text: Should be #DC2626
- Muted text: Should be #6B7280

---

## Step 6: Document Findings (5 min)

### Record all issues:

**Idunn:**
> "Testing complete. Let's document findings."

**Example findings:**

```markdown
### Content ✓
All text matches spec.

### States
- [x] Default
- [x] Focus
- [x] Validation errors
- [ ] **ISSUE:** Loading spinner too small
  - Spec: 20px
  - Impl: 16px
- [x] Success

### Interactions ✓
All working correctly.

### Visual
- [x] Layout
- [x] Spacing
- [ ] **ISSUE:** Error text color slightly off
  - Spec: #DC2626
  - Impl: #EF4444
- [x] Responsive
```

---

## Step 7: Run Acceptance Criteria (5 min)

### Verify each criterion:

**Idunn:**
> "Now running through acceptance criteria from delivery package."

```markdown
## Acceptance Criteria: S01-User-Registration

### Happy Path
- [x] User can enter email and password
- [x] Real-time validation shows errors
- [x] Submit button disabled when form invalid
- [x] Successful submission redirects to welcome
- [x] Welcome screen shows user's email

### Error Handling
- [x] Invalid email shows "Please enter a valid email"
- [x] Short password shows "Password must be at least 8 characters"
- [x] Duplicate email shows "This email is already registered"
- [x] Server error shows "Something went wrong"
- [x] Network error shows "Connection lost"

### Accessibility
- [x] All inputs have labels
- [x] Errors announced to screen readers
- [x] Focus moves to first error on submit
- [x] Touch targets minimum 44px
- [x] Keyboard navigation works throughout
```

---

## Step 8: Prioritize and Assign (3 min)

### Categorize issues:

**Idunn:**
> "Two issues found. Let's prioritize."

```markdown
## Actions Required

### Major
None

### Minor
1. **Loading spinner size**
   - Current: 16px
   - Spec: 20px
   - Action: Update implementation
   - Assigned: Developer

2. **Error text color**
   - Current: #EF4444
   - Spec: #DC2626
   - Action: Update implementation
   - Assigned: Developer
```

---

## Step 9: Finalize Test Results (2 min)

### Complete the document:

```markdown
# Test Results: S01-User-Registration

## Tested: 2026-02-10
## Tester: Idunn
## Status: 2 minor issues found

## Summary
Signup form implementation matches specification with two minor
visual discrepancies. All functionality works correctly.
Acceptance criteria: 15/15 passed.

[Details as documented above]

## Next Steps
1. Developer fixes spinner size and error color
2. Re-test those specific items
3. Sign off on page
```

---

## What You've Created

### Test documentation:

- Complete test results
- All issues documented
- Priorities assigned
- Clear next steps

### Verified:

- Content matches spec
- All states work
- Interactions correct
- Acceptance criteria passed

---

## Tips for Success

**DO:**

- Test every state, not just happy path
- Use spec as your source of truth
- Document even small differences
- Re-test after fixes

**DON'T:**

- Assume things work because they look right
- Skip accessibility testing
- Leave issues undocumented
- Fix without updating spec if needed

---

## You've Completed Module 17!

**Your implementation is verified.** You've:
- Tested against specification
- Documented all findings
- Verified acceptance criteria
- Created clear action items

---

## Next Module

**[Module 18: Product Evolution →](../module-18-product-evolution/module-18-product-evolution-overview.md)**

Products don't end at launch. Learn how to evolve them.

---

[← Back to Lesson 2](lesson-02-test-results.md) | [Back to Module Overview](module-17-testing-overview.md)
