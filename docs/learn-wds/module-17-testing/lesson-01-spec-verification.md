# Module 17: Testing

## Lesson 1: Spec Verification

**Ensuring implementation matches design**

---

## The Purpose of Testing in WDS

Your specifications are the source of truth.

If the implementation differs from the spec, one of them is wrong:
- The spec needs updating, OR
- The implementation needs fixing

Testing finds the differences. You decide which to fix.

---

## Browser-Based Testing

Open the implementation. Open your spec. Compare.

This is the simplest, most direct form of testing.

### What to Check

| Check | How |
|-------|-----|
| **Content** | Does text match spec exactly? |
| **States** | Do all states work as specified? |
| **Interactions** | Do clicks/hovers behave correctly? |
| **Layout** | Is visual hierarchy correct? |
| **Responsiveness** | Does it work on all sizes? |

---

## The Testing Flow

```
┌─────────────┐
│  Open spec  │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│  Open impl  │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│  Compare    │
│  element by │
│  element    │
└──────┬──────┘
       │
       ▼
   Matches? ─── No ──► Document difference
       │
      Yes
       │
       ▼
┌─────────────┐
│    Next     │
│   element   │
└─────────────┘
```

Go through every element. Check every state. Document every difference.

---

## Testing Categories

### 1. Content Testing

Does the text match the specification exactly?

- Headlines
- Button labels
- Error messages
- Placeholder text
- Helper text
- Link text

**Common issues:**
- Typos
- Slightly different wording
- Missing content
- Extra content not in spec

### 2. State Testing

Do all behavioral states work?

- Default state
- Hover states
- Active/pressed states
- Focus states
- Disabled states
- Loading states
- Error states
- Empty states

**Common issues:**
- Missing states
- Wrong styling on states
- Incorrect transitions
- Timing differences

### 3. Interaction Testing

Do interactions behave correctly?

- Clicks trigger correct actions
- Forms validate correctly
- Navigation works
- Keyboard navigation works
- Touch interactions work

**Common issues:**
- Wrong action on click
- Missing keyboard support
- Validation timing differs
- Focus management incorrect

### 4. Visual Testing

Does the layout match the specification?

- Element positioning
- Spacing correct
- Colors correct
- Typography correct
- Responsive behavior

**Common issues:**
- Spacing off
- Colors slightly different
- Font weights incorrect
- Breakpoints not matching

---

## When Implementation Differs

You found a difference. Now what?

### Three possibilities:

**1. Spec Was Unclear**

The implementation team interpreted the spec differently than intended.

**Fix:** Update spec to be clearer. Implementation might actually be correct.

**2. Implementation Is Wrong**

The implementation doesn't match the clear spec.

**Fix:** Update implementation to match spec.

**3. Better Idea During Implementation**

The implementation discovered a better approach.

**Fix:** Update spec to reflect the improvement. Document why it's better.

---

## The Idunn Method

Idunn guides testing systematically:

> "Let's check the signup form against spec P02."

> "The button says 'Sign Up' but spec says 'Create Free Account'. Which is correct?"

> "Error state: spec says inline message, implementation shows toast. Mismatch."

She catches what eyes miss.

---

## Testing Checklist Template

For each page:

```markdown
## Page: [Name]

### Content
- [ ] Headlines match spec
- [ ] Body text matches spec
- [ ] Button labels match spec
- [ ] Error messages match spec
- [ ] Placeholder text matches spec

### States
- [ ] Default state correct
- [ ] Hover states work
- [ ] Active states work
- [ ] Focus states visible
- [ ] Disabled states work
- [ ] Error states display correctly
- [ ] Loading states show correctly
- [ ] Empty states handled

### Interactions
- [ ] Clicks trigger correct actions
- [ ] Forms validate correctly
- [ ] Navigation works
- [ ] Keyboard navigation works
- [ ] Touch works (if applicable)

### Visual
- [ ] Layout matches spec
- [ ] Spacing is correct
- [ ] Colors are correct
- [ ] Typography is correct
- [ ] Responsive breakpoints work
```

---

## What's Next

In the next lesson, you'll learn how to document test results and run acceptance testing against your criteria.

---

**[Continue to Lesson 2: Test Results and Acceptance →](lesson-02-test-results.md)**

---

[← Back to Module Overview](module-17-testing-overview.md)
