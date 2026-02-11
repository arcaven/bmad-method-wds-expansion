# Module 17: Testing

## Lesson 2: Test Results and Acceptance

**Documenting findings and verifying acceptance criteria**

---

## Test Results Document

Every test session should produce documentation.

```markdown
# Test Results: [Scenario Name]

## Tested: [Date]
## Tester: [Name]
## Status: [# issues found]

## [Page Name]

### Content
- [x] Headlines match
- [x] Button labels match
- [ ] Error message differs — [describe]

### States
- [x] Default
- [x] Hover
- [ ] Loading — [describe issue]

### Interactions
- [x] Form validation works
- [x] Navigation correct

### Visual
- [x] Layout matches
- [ ] Spacing issue — [describe]

## Actions Required
1. [Issue 1 — who will fix]
2. [Issue 2 — who will fix]

## Notes
[Any observations or recommendations]
```

---

## Documenting Issues

For each issue found:

### Be Specific

**Bad:** "Button looks wrong"

**Good:** "Submit button has 24px padding (spec says 16px)"

### Include Context

- What you expected (from spec)
- What you found (in implementation)
- Where to find it (page, element, state)

### Suggest Resolution

- Fix implementation to match spec, OR
- Update spec to reflect better approach

---

## Acceptance Testing

Acceptance criteria (from Module 15) become test cases.

```markdown
## Acceptance Criteria: S01-User-Registration

### Happy Path
- [x] User can enter email and password
- [x] Real-time validation shows errors
- [x] Submit button disabled when form invalid
- [x] Successful submission redirects to welcome
- [x] Welcome screen shows user's email

### Error Handling
- [x] Invalid email shows correct message
- [ ] Short password message differs — NEEDS FIX
- [x] Server error handled
- [x] Network error handled

### Accessibility
- [x] All inputs have labels
- [x] Errors announced to screen readers
- [ ] Focus doesn't move to first error — NEEDS FIX
- [x] Touch targets adequate
```

---

## Prioritizing Issues

Not all issues are equal.

### Critical

Must fix before release.

- Broken functionality
- Security vulnerabilities
- Data loss scenarios
- Accessibility failures

### Major

Should fix before release.

- Wrong content
- Incorrect behavior
- Significant visual differences

### Minor

Can fix after release.

- Small spacing issues
- Slight color variations
- Polish items

---

## Resolution Workflow

```
Issue Found
    │
    ▼
Is spec correct?
    │
   Yes ──► Fix implementation
    │
   No  ──► Update spec first ──► Then update implementation if needed
    │
    ▼
Verify fix
    │
    ▼
Document resolution
```

**Always close the loop.** Every issue should end with:
- Implementation fixed, OR
- Spec updated, OR
- Decision to defer with reason

---

## Example Test Results

```markdown
# Test Results: S01-User-Registration

## Tested: 2026-02-10
## Tester: Idunn
## Status: 2 issues found (1 major, 1 minor)

## P02: Signup Form

### Content ✅
All text matches spec.

### States
- [x] Default
- [x] Hover
- [x] Active
- [ ] **MAJOR:** Error message color differs
  - Spec: #DC2626
  - Impl: #EF4444
  - Action: Fix implementation
- [x] Loading
- [x] Disabled

### Interactions ✅
All working correctly.

### Visual
- [ ] **MINOR:** Submit button padding larger than spec
  - Spec: 16px
  - Impl: 24px
  - Note: Larger padding improves touch target
  - Action: Update spec to reflect intentional change

## Actions Required

1. **Error color** — Fix implementation to use #DC2626
   - Assigned: Developer
   - Priority: Major

2. **Button padding** — Update spec to 24px
   - Assigned: Designer
   - Priority: Minor (actually an improvement)

## Notes
- Decided to keep larger padding (48px touch target vs 42px)
- Updated spec to reflect this intentional deviation
- Error color was a simple oversight — hex code was close but not exact
```

---

## Closing the Testing Loop

After issues are resolved:

1. **Re-test** the specific items
2. **Update** test results document
3. **Mark** issues as resolved
4. **Sign off** on the page/scenario

```markdown
## Resolution Log

### Issue 1: Error color
- Fixed: 2026-02-11
- Verified: Color now matches spec
- Status: Closed

### Issue 2: Button padding
- Fixed: 2026-02-11
- Action: Updated spec to 24px
- Status: Closed

## Final Status: PASSED
All issues resolved. Ready for release.
```

---

## The Idunn Method

Idunn keeps testing organized:

> "Running through acceptance criteria for S01..."

> "Found 3 issues. 1 critical, 2 minor. Let me prioritize them."

> "Issue #1 is resolved. Retesting... confirmed fixed. 2 remaining."

She ensures nothing slips through.

---

## What's Next

In the tutorial, you'll run through the complete testing process for one of your implemented pages.

---

**[Continue to Tutorial: Test Your Implementation →](tutorial-17.md)**

---

[← Back to Lesson 1](lesson-01-spec-verification.md) | [Back to Module Overview](module-17-testing-overview.md)
