# Layout Terminology

The vocabulary for describing how elements are arranged in space — from page structure to component organization.

---

## Page Sections

### Hero Section

**Definition:** The large, prominent section at the top of a page, often fullscreen.

**Variations:**

| Type | Description | Best For |
|------|-------------|----------|
| **Full-bleed Image** | Background image covers viewport | Visual impact, photography |
| **Split Hero** | Image one side, text other | Product launches, features |
| **Video Hero** | Background video | Energy, movement, emotion |
| **Text-focused** | Minimal image, strong headline | Content sites, SaaS |
| **Carousel Hero** | Rotating content | Multiple offerings (use sparingly) |

**Examples:**
- [Stripe](https://stripe.com/) — Animated gradient hero
- [Apple](https://www.apple.com/iphone/) — Product-focused hero
- [Airbnb](https://www.airbnb.com/) — Search-integrated hero

**Key Elements:**
- Headline (compelling value proposition)
- Subheadline (supporting details)
- CTA button(s)
- Visual (image, video, or illustration)

---

### Above the Fold

**Definition:** Content visible without scrolling on initial page load.

**Critical for:**
- Value proposition clarity
- Primary call-to-action visibility
- Navigation access
- Trust signals

**Note:** "Fold" varies by device. Design for common viewport heights (768px, 900px, 1080px).

---

### Content Sections

| Term | Description |
|------|-------------|
| **Feature Grid** | Multiple features displayed in grid |
| **Testimonials** | Customer quotes/reviews |
| **Social Proof** | Logos, numbers, trust indicators |
| **FAQ Accordion** | Expandable question/answer sections |
| **CTA Band** | Full-width call-to-action section |
| **Footer** | Navigation, legal, contact at bottom |

---

## Grid Systems

### Column Grid

**Definition:** Vertical columns that structure content placement.

**Common Configurations:**
- 12-column (most flexible)
- 8-column (balanced)
- 6-column (simpler)
- 4-column (minimal)

**CSS:** `display: grid; grid-template-columns: repeat(12, 1fr);`

**Examples:**
- [Bootstrap Grid](https://getbootstrap.com/docs/5.3/layout/grid/)
- [Foundation Grid](https://get.foundation/sites/docs/grid.html)

---

### Modular Grid

**Definition:** Both vertical columns AND horizontal rows, creating equal modules.

**Characteristics:**
- Checkerboard-like structure
- Equal-sized content blocks
- Excellent for galleries, dashboards
- Highly organized feel

**Examples:**
- Pinterest layout
- Dashboard interfaces
- Image galleries

---

### Hierarchical Grid

**Definition:** Organic grid based on content importance rather than strict columns.

**Characteristics:**
- Breaks conventional grid for emphasis
- Content-driven structure
- Magazine-style layouts
- Varied element sizes

**Examples:**
- News websites (NY Times, The Guardian)
- Editorial layouts

---

### Baseline Grid

**Definition:** Horizontal lines aligned to text baseline for vertical rhythm.

**Purpose:**
- Consistent vertical spacing
- Harmonious text alignment
- Professional, polished appearance

**Implementation:** Align line-height to base unit (often 8px or 4px)

---

## Layout Patterns

### Card-Based Layout

**Definition:** Self-contained content blocks that can be arranged flexibly.

**Characteristics:**
- Distinct visual boundary (shadow, border, background)
- Contains related information
- Responsive-friendly
- Scannable content

**Variations:**
- Standard card (image + text + action)
- Horizontal card (image left, text right)
- Overlay card (text over image)
- Stats card (numbers + labels)

**Examples:**
- [Trello](https://trello.com/)
- [Netflix](https://www.netflix.com/)
- [Medium articles](https://medium.com/)

**CSS:** `box-shadow`, `border-radius`, `padding`, defined `max-width`

---

### Bento Box Layout

**Definition:** Japanese meal-inspired grid with varied-sized compartments.

**Characteristics:**
- Different sized modules in grid
- Spanning cells (some items take 2x1, 1x2, 2x2)
- Visual hierarchy through size
- Trending 2023-2026

**Examples:**
- [Apple Features pages](https://www.apple.com/iphone-15-pro/)
- [Vercel](https://vercel.com/)
- [Linear](https://linear.app/)

**CSS:** `grid-column: span 2; grid-row: span 2;`

---

### Masonry Layout

**Definition:** Pinterest-style layout where items stack based on available vertical space.

**Characteristics:**
- Variable height items
- No fixed row heights
- Organic, flowing appearance
- Efficient space usage

**Examples:**
- [Pinterest](https://www.pinterest.com/)
- [Unsplash](https://unsplash.com/)

**Implementation:** CSS Grid with `grid-auto-rows: masonry` (limited support) or JavaScript libraries (Masonry.js, Isotope)

---

### Single Column

**Definition:** Content flows in one vertical column.

**Characteristics:**
- Maximum readability
- Mobile-first approach
- Content-focused
- Blog/article standard

**Examples:**
- [Medium articles](https://medium.com/)
- [Substack](https://substack.com/)

**Optimal width:** 600-800px for text content

---

### Split Screen

**Definition:** Page divided into two equal (or near-equal) vertical sections.

**Characteristics:**
- Clear visual distinction
- Often image vs. content
- Good for comparisons
- Strong visual impact

**Examples:**
- [Slack landing](https://slack.com/)
- Before/after comparisons

---

### F-Pattern

**Definition:** Layout optimized for Western reading pattern (left-to-right, top-to-bottom).

**Eye Movement:**
1. Horizontal across top
2. Down left side
3. Horizontal scan across middle
4. Down left side

**Optimize for:**
- Logo/navigation top-left
- Headlines at scan lines
- CTAs in hot zones

---

### Z-Pattern

**Definition:** Layout following diagonal scanning for landing pages.

**Eye Movement:**
1. Top left → Top right
2. Diagonal to bottom left
3. Bottom left → Bottom right

**Use for:**
- Simple landing pages
- Low-content pages
- Clear conversion paths

---

## Composition Principles

### Balance

| Type | Description |
|------|-------------|
| **Symmetrical** | Mirror image across axis |
| **Asymmetrical** | Visual weight balanced without mirroring |
| **Radial** | Elements radiate from center |

---

### Alignment

| Type | Description | Use Case |
|------|-------------|----------|
| **Left** | Text/elements align left | Body text, Western reading |
| **Center** | Centered alignment | Headlines, hero content |
| **Right** | Right-aligned | Navigation, prices |
| **Justified** | Stretched to fill width | Print, formal documents |

---

### White Space (Negative Space)

**Definition:** Empty areas between and around elements.

**Types:**
- **Macro** — Large spaces between sections
- **Micro** — Small spaces (padding, margins, line-height)

**Effects:**
- Improves readability
- Creates visual hierarchy
- Adds elegance
- Reduces cognitive load

**Rule:** When in doubt, add more white space.

---

### Visual Hierarchy

**Definition:** Order in which elements are perceived and processed.

**Techniques:**
- Size (larger = more important)
- Color (contrast draws attention)
- Position (top/left = first)
- Weight (bold = emphasis)
- Whitespace (isolation = importance)

---

### Proximity

**Definition:** Related items should be grouped together.

**Application:**
- Form labels near inputs
- Navigation items grouped
- Card content related
- Section spacing larger than element spacing

---

### Golden Ratio

**Definition:** Mathematical proportion (1:1.618) considered aesthetically pleasing.

**Applications:**
- Layout proportions
- Typography scaling
- Image cropping
- Spacing systems

**Practical:** Often rounded to 1:1.6 or 5:8

---

## Responsive Layout Terms

| Term | Definition |
|------|------------|
| **Breakpoint** | Screen width where layout changes |
| **Fluid** | Elements scale proportionally |
| **Fixed** | Elements maintain set pixel width |
| **Container** | Maximum width wrapper for content |
| **Gutter** | Space between grid columns |
| **Margin** | Space outside content container |

**Common Breakpoints:**
- Mobile: 320px - 767px
- Tablet: 768px - 1023px
- Desktop: 1024px - 1439px
- Large: 1440px+

---

## Resources

- [Refactoring UI](https://www.refactoringui.com/) — Layout best practices
- [Every Layout](https://every-layout.dev/) — CSS layout patterns
- [Layout Land (YouTube)](https://www.youtube.com/c/LayoutLand) — Modern CSS layouts
- [CSS Grid Garden](https://cssgridgarden.com/) — Interactive grid learning

---

*Part of the [Design Nomenclature Reference](index.md)*
