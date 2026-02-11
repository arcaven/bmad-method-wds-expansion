# Module 14: Visual Design

## Lesson 2: Visual Design Techniques

**Practical methods for generating and refining visuals**

---

## Working with AI Generation

AI tools can generate visuals from specifications. Here's how to get good results.

### Prompt Structure

```
Generate [element type] based on this specification:

[Paste your specification]

Visual requirements:
- Font: [font family]
- Primary color: [hex code]
- Background: [color/style]
- Size: [dimensions or responsive]

Focus on: [what's most important]
```

### Example Prompt

```
Generate a signup form based on this specification:

## Signup Form
- Email field (required, validates email format)
- Password field (required, 8+ chars, show/hide toggle)
- Submit button: "Create Free Account"
- Terms link below
- Login link for existing users

Visual requirements:
- Font: Inter
- Primary color: #0066FF
- Background: White with subtle gray (#F9FAFB)
- Size: Mobile-first (max-width 400px)

Focus on: Clean, minimal, low friction
```

### What You Get

Working HTML/CSS that you can:
- View in browser
- Click through
- Import to Figma
- Refine and iterate

---

## Refining Generated Output

AI output is a starting point, not a final product.

### Common Refinements

**Spacing:**
- AI often under- or over-spaces
- Adjust for visual rhythm
- Ensure breathing room around elements

**Typography:**
- Check font weights
- Verify line heights
- Adjust size hierarchy

**Colors:**
- Verify contrast ratios
- Check hover states
- Ensure consistency

**Touch Targets:**
- Buttons 44px minimum
- Adequate spacing between tap targets
- Test on actual devices

---

## Using Figma for Polish

### Import from HTML

1. Generate HTML with AI
2. Use html.to.design plugin
3. Import to Figma canvas
4. Elements become Figma objects

### Polish in Figma

- Adjust auto-layout spacing
- Apply component styles
- Create variants for states
- Add design tokens

### Export Back

- Export assets (icons, images)
- Generate CSS from Figma
- Use Figma Dev Mode for specs

---

## Designing States

Each state needs its own visual:

### Default State

The initial appearance. What users see on load.

### Hover State

Feedback on mouseover. Usually:
- Slight color change (10% darker)
- Subtle shadow or elevation
- Cursor change

### Active/Pressed State

Feedback on click. Usually:
- Darker than hover
- Slight scale down (98%)
- Pressed appearance

### Focus State

For keyboard navigation. Must be visible:
- Outline (2px solid)
- Offset from element
- Sufficient contrast

### Disabled State

When interaction is blocked:
- Reduced opacity (50-60%)
- No hover effects
- Cursor: not-allowed

### Loading State

During async operations:
- Spinner or skeleton
- Reduced interactivity
- Progress indication

### Error State

When something fails:
- Error color (usually red)
- Clear message
- Recovery path visible

---

## Accessibility in Visual Design

### Color Contrast

- Text on background: 4.5:1 minimum (WCAG AA)
- Large text (18px+): 3:1 minimum
- UI components: 3:1 minimum

**Tools:** Contrast checkers in Figma, browser extensions

### Focus Visibility

- Focus rings must be visible
- 3:1 contrast against background
- Don't hide on mouse use

### Touch Targets

- Minimum 44x44px for touch
- 24x24px for precise mouse input
- Adequate spacing between targets

---

## Consistency Patterns

### Token Application

Apply tokens consistently:

```css
/* All primary buttons use same color */
.btn-primary {
  background: var(--color-primary);
  color: var(--color-text-on-primary);
}

/* All headings use same scale */
h1 { font: var(--type-heading-1); }
h2 { font: var(--type-heading-2); }

/* All spacing uses same scale */
.card { padding: var(--space-lg); }
.stack > * + * { margin-top: var(--space-md); }
```

### Component Reuse

Same component, same styling:
- Buttons look identical across pages
- Inputs behave the same everywhere
- Cards have consistent structure

---

## The Freya Method

Freya connects visuals to strategy:

> "This visual is beautiful, but does it match Felix's need for simplicity?"

> "The color contrast here might cause accessibility issues."

> "Your spec says primary CTA — but visually the secondary button draws more attention."

She keeps visuals aligned with intent.

---

## Visual Design Checklist

For each page:

- [ ] Layout matches specification
- [ ] Visual hierarchy correct (primary element dominates)
- [ ] Typography applied from tokens
- [ ] Colors from palette/brand
- [ ] Spacing consistent (uses token scale)
- [ ] All states designed (default, hover, loading, error, etc.)
- [ ] Contrast ratios pass WCAG
- [ ] Touch targets adequate
- [ ] Responsive behavior defined

---

## What's Next

In the tutorial, you'll generate and refine visuals for your own specifications, working through the design loop until you have polished, validated prototypes.

---

**[Continue to Tutorial: Create Your Visuals →](tutorial-13.md)**

---

[← Back to Lesson 1](lesson-01-making-it-visible.md) | [Back to Module Overview](module-14-visual-design-overview.md)
