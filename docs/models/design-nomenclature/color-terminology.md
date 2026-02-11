# Color Terminology

The language of color in design — from color theory fundamentals to practical application in interfaces.

---

## Color Scheme Types

### Monochromatic

**Definition:** Single hue with variations in lightness (tints) and darkness (shades).

**Characteristics:**
- Harmonious and cohesive
- Elegant, sophisticated feel
- Easy to manage
- Risk of monotony without texture/typography variation

**When to use:**
- Minimalist designs
- Luxury/premium brands
- When content should be the focus
- Photography-heavy layouts

**Examples:**
- [Squarespace Templates](https://www.squarespace.com/templates)
- [Apple Product Pages](https://www.apple.com/iphone/)

**CSS Example:**
```css
--primary-100: #E3F2FD;
--primary-300: #64B5F6;
--primary-500: #2196F3;
--primary-700: #1976D2;
--primary-900: #0D47A1;
```

---

### Analogous

**Definition:** Three adjacent colors on the color wheel (e.g., blue, blue-green, green).

**Characteristics:**
- Natural harmony (found in nature: sunset, forest)
- Calm, comfortable feeling
- Low contrast
- One dominant, two supporting colors

**When to use:**
- Nature/wellness brands
- Backgrounds and gradients
- When you want cohesion without monotony

**Examples:**
- [Headspace](https://www.headspace.com/)
- [Calm](https://www.calm.com/)

**Color Wheel Position:** Adjacent colors (30-60° apart)

---

### Complementary

**Definition:** Two colors directly opposite on the color wheel (e.g., blue and orange).

**Characteristics:**
- High contrast, vibrant
- Colors enhance each other
- Attention-grabbing
- Can be harsh if overused

**When to use:**
- Call-to-action buttons
- Emphasis and highlighting
- Sports/energy brands
- Warning/success states

**Examples:**
- [Firefox](https://www.mozilla.org/firefox/)
- [FedEx](https://www.fedex.com/) (purple + orange)

**Balance Tip:** Use 80/20 rule — dominant color 80%, complement 20%

---

### Split-Complementary

**Definition:** Base color + two colors adjacent to its complement.

**Characteristics:**
- High contrast but less tension than complementary
- More nuanced than straight complementary
- Three-color harmony
- Easier to balance

**When to use:**
- When you want vibrancy with more flexibility
- Branding with primary/secondary/accent
- Web interfaces with varied content

**Example Combination:** Blue + Yellow-Orange + Red-Orange

---

### Triadic

**Definition:** Three colors equally spaced on the color wheel (120° apart).

**Characteristics:**
- Vibrant and playful
- Balanced tension
- Works best with one dominant color
- Can feel childish if not carefully balanced

**When to use:**
- Children's products
- Playful/creative brands
- When you need variety with harmony

**Examples:**
- [Google](https://www.google.com/) (blue, red, yellow + green)
- [Slack](https://slack.com/)

**Classic Triads:** Red-Yellow-Blue, Orange-Green-Purple

---

### Tetradic (Square/Rectangle)

**Definition:** Four colors forming a rectangle or square on the color wheel.

**Characteristics:**
- Rich, varied palette
- Complex to balance
- Best with clear hierarchy
- One dominant color recommended

**When to use:**
- Complex interfaces with many states
- Illustration-heavy designs
- When variety is essential

---

## Color Properties

### Saturation

**Definition:** The intensity or purity of a color.

| Term | Meaning | Effect |
|------|---------|--------|
| **Saturated** | Pure, vivid color | Energetic, attention-grabbing |
| **Desaturated** | Muted, grayed | Calm, sophisticated, accessible |
| **Pastel** | Light, low saturation | Soft, friendly, gentle |
| **Neon** | Maximum saturation + brightness | Bold, modern, energetic |

**Accessibility Note:** Highly saturated colors can cause eye strain. Desaturate for large areas.

---

### Value/Lightness

| Term | Meaning |
|------|---------|
| **Tint** | Color + white (lighter) |
| **Shade** | Color + black (darker) |
| **Tone** | Color + gray (muted) |

---

### Temperature

| Term | Colors | Feeling |
|------|--------|---------|
| **Warm** | Red, orange, yellow | Energy, passion, urgency |
| **Cool** | Blue, green, purple | Calm, trust, professionalism |
| **Neutral** | Gray, beige, white, black | Balance, sophistication |

---

## Specialized Color Techniques

### Duotone

**Definition:** Image or graphic using only two colors.

**Characteristics:**
- Striking, graphic effect
- Unifies diverse imagery
- Strong brand association
- Popular in hero images

**Examples:**
- [Spotify](https://www.spotify.com/) marketing
- [Twitch](https://www.twitch.tv/) branding

**CSS/Tool:** Photoshop gradient maps, CSS blend modes

---

### Gradient Types

| Type | Description | Use Case |
|------|-------------|----------|
| **Linear** | Straight color transition | Backgrounds, buttons |
| **Radial** | Circular color transition | Spotlights, orbs |
| **Conic** | Angular color transition | Pie charts, color wheels |
| **Mesh** | Multi-point color blending | Complex backgrounds |

**Trend:** Mesh gradients are popular in 2024-2026 for hero sections.

**Tools:**
- [Mesh Gradient Generator](https://meshgradient.in/)
- [Coolors Gradient Maker](https://coolors.co/gradient-maker)

---

### Color Modes

| Mode | Use Case |
|------|----------|
| **RGB** | Screens, digital (Red-Green-Blue) |
| **CMYK** | Print (Cyan-Magenta-Yellow-Black) |
| **HSL** | Design tools (Hue-Saturation-Lightness) |
| **HEX** | Web development (#FF5733) |
| **OKLCH** | Modern CSS color space (perceptual uniformity) |

---

## Palette Generation Tools

- [Coolors](https://coolors.co/) — Quick palette generation
- [Adobe Color](https://color.adobe.com/) — Color wheel + harmony rules
- [Realtime Colors](https://www.realtimecolors.com/) — See colors on a real UI
- [Paletton](https://paletton.com/) — Advanced color scheme designer
- [Colour Lovers](https://www.colourlovers.com/) — Community palettes

---

## Color in Accessibility

| Contrast Ratio | Use Case | WCAG Level |
|----------------|----------|------------|
| 4.5:1 | Normal text | AA |
| 3:1 | Large text (18pt+) | AA |
| 7:1 | Normal text | AAA |

**Tools:**
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Stark Plugin](https://www.getstark.co/)

**Rule:** Never use color alone to convey meaning.

---

*Part of the [Design Nomenclature Reference](index.md)*
