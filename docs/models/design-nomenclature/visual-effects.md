# Visual Effects

The vocabulary for describing motion, depth, and decorative treatments applied to interface elements.

---

## Shadow Effects

### Drop Shadow

**Definition:** Shadow cast behind an element, simulating depth.

**Characteristics:**
- Creates elevation illusion
- Separates element from background
- Adjustable: offset, blur, spread, color

**CSS:**
```css
box-shadow: 4px 4px 8px rgba(0, 0, 0, 0.1);
/* offset-x | offset-y | blur | color */
```

**Variations:**
| Type | CSS | Effect |
|------|-----|--------|
| Subtle | `0 1px 3px rgba(0,0,0,0.1)` | Gentle lift |
| Medium | `0 4px 6px rgba(0,0,0,0.1)` | Clear separation |
| Heavy | `0 10px 20px rgba(0,0,0,0.15)` | Strong elevation |
| Colored | `0 4px 12px rgba(99,102,241,0.4)` | Brand accent |

---

### Long Shadow

**Definition:** Extended shadow at 45° angle, popular in flat design era.

**Characteristics:**
- Retro/flat design aesthetic
- No blur (solid shadow)
- Creates depth in minimalist designs
- Often same color as element, darker

**CSS (approximation):**
```css
text-shadow:
  1px 1px 0 #d35400,
  2px 2px 0 #d35400,
  3px 3px 0 #d35400,
  /* ... continue */;
```

**Era:** 2013-2016 flat design trend

---

### Inner Shadow (Inset)

**Definition:** Shadow inside element boundary, creating recessed effect.

**CSS:**
```css
box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.1);
```

**Use Cases:**
- Input fields (pressed state)
- Neumorphic inset elements
- Creating depth in buttons

---

### Soft Shadow

**Definition:** Very high blur, low opacity shadow for floating effect.

**Characteristics:**
- Subtle, modern feel
- Large blur radius
- Low opacity
- Popular 2020s trend

**CSS:**
```css
box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
```

**Examples:**
- [Tailwind shadow-2xl](https://tailwindcss.com/docs/box-shadow)
- Modern card designs

---

### Hard Shadow (Neobrutalism)

**Definition:** Solid color shadow with no blur, offset from element.

**Characteristics:**
- Bold, graphic effect
- No blur (0px)
- Often black or accent color
- Creates layered paper effect

**CSS:**
```css
box-shadow: 4px 4px 0 #000000;
```

**Examples:**
- [Gumroad](https://gumroad.com/)
- Neobrutalist interfaces

---

## Blur Effects

### Gaussian Blur

**Definition:** Standard blur effect, softens image/element uniformly.

**CSS:**
```css
filter: blur(10px);
```

**Use Cases:**
- Depth of field simulation
- Background for overlays
- Privacy/redaction
- Inactive states

---

### Backdrop Blur

**Definition:** Blur applied to content BEHIND an element (glassmorphism).

**CSS:**
```css
backdrop-filter: blur(10px);
background: rgba(255, 255, 255, 0.2);
```

**Use Cases:**
- Modal overlays
- Glass-effect cards
- Floating headers
- macOS/iOS-style interfaces

**Browser Support:** Check [caniuse.com](https://caniuse.com/css-backdrop-filter)

---

### Motion Blur

**Definition:** Directional blur suggesting movement.

**Implementation:** Usually created in image editing, not CSS

**Use Cases:**
- Speed indication
- Background dynamism
- Transition effects

---

## Overlay Effects

### Color Overlay

**Definition:** Semi-transparent color layer over image/content.

**CSS:**
```css
.overlay::after {
  content: '';
  position: absolute;
  background: rgba(0, 0, 0, 0.5);
  /* or gradient */
}
```

**Use Cases:**
- Improve text readability over images
- Brand color treatment
- Mood/atmosphere

---

### Gradient Overlay

**Definition:** Gradient layer fading from transparent to solid.

**CSS:**
```css
background: linear-gradient(
  to bottom,
  transparent 0%,
  rgba(0, 0, 0, 0.8) 100%
);
```

**Use Cases:**
- Text over hero images
- Fade to background color
- Creating visual hierarchy

---

### Blend Modes

**Definition:** How layers combine visually (Photoshop-style blending).

**Common Modes:**
| Mode | Effect | Use Case |
|------|--------|----------|
| `multiply` | Darkens, removes white | Texture overlays |
| `screen` | Lightens, removes black | Light effects |
| `overlay` | Contrast enhancement | Color grading |
| `color` | Applies hue | Duotone effect |
| `difference` | Inverts based on brightness | Artistic effects |

**CSS:**
```css
mix-blend-mode: multiply;
background-blend-mode: overlay;
```

---

## Gradient Types

### Linear Gradient

**Definition:** Color transition in straight line.

**CSS:**
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

**Direction Options:** `to right`, `to bottom`, `45deg`, `135deg`, etc.

---

### Radial Gradient

**Definition:** Color transition radiating from center point.

**CSS:**
```css
background: radial-gradient(circle, #667eea 0%, #764ba2 100%);
```

**Shapes:** `circle`, `ellipse`

---

### Conic Gradient

**Definition:** Color transition rotating around center point.

**CSS:**
```css
background: conic-gradient(from 0deg, red, yellow, green, blue, red);
```

**Use Cases:**
- Pie charts
- Color wheels
- Decorative elements

---

### Mesh Gradient

**Definition:** Multi-point color blending for organic, flowing gradients.

**Characteristics:**
- Multiple color "sources"
- Organic transitions
- Very popular 2024-2026
- Hero section backgrounds

**Tools:**
- [Mesh Gradient Generator](https://meshgradient.in/)
- [Figma Mesh Gradient Plugin](https://www.figma.com/community/plugin/958202093377483021)

**Examples:**
- [Linear](https://linear.app/)
- [Stripe](https://stripe.com/)
- [Vercel](https://vercel.com/)

---

## Motion Effects

### Parallax Scrolling

**Definition:** Background and foreground move at different speeds while scrolling.

**Characteristics:**
- Creates depth illusion
- Engaging scroll experience
- Can cause motion sickness if overused
- Performance considerations on mobile

**Implementation:**
```css
.parallax {
  background-attachment: fixed;
  /* or JavaScript-based for more control */
}
```

**Examples:**
- [Webflow Parallax Templates](https://webflow.com/templates)
- [Firewatch Game Site](https://www.firewatchgame.com/)

**Tools:**
- [Locomotive Scroll](https://locomotivemtl.github.io/locomotive-scroll/)
- [GSAP ScrollTrigger](https://greensock.com/scrolltrigger/)

---

### Scroll Animations

**Definition:** Elements animate as they enter viewport on scroll.

**Types:**
| Effect | Description |
|--------|-------------|
| **Fade in** | Opacity 0 → 1 |
| **Slide up** | Enter from below |
| **Scale** | Grow from small |
| **Reveal** | Mask/clip animation |
| **Stagger** | Sequential delays |

**Libraries:**
- [Framer Motion](https://www.framer.com/motion/)
- [GSAP](https://greensock.com/gsap/)
- [AOS (Animate On Scroll)](https://michalsnik.github.io/aos/)

---

### Hover Effects

**Definition:** Visual changes when cursor hovers over element.

**Common Effects:**
- Scale (grow/shrink)
- Color change
- Shadow increase
- Underline animation
- Image zoom
- Overlay reveal

**CSS:**
```css
.element {
  transition: transform 0.3s ease;
}
.element:hover {
  transform: scale(1.05);
}
```

---

### Micro-interactions

**Definition:** Small, contained animations responding to user actions.

**Examples:**
- Button press feedback
- Toggle switches
- Like/heart animations
- Loading spinners
- Form validation feedback
- Notification badges

**Principles:**
- Immediate feedback
- Subtle (not distracting)
- Meaningful (convey information)
- Consistent throughout interface

---

## Texture Effects

### Noise/Grain

**Definition:** Fine speckled texture added to flat areas.

**Characteristics:**
- Adds warmth and depth
- Prevents banding in gradients
- Subtle, organic feel
- Retro/film quality

**CSS (SVG filter):**
```css
filter: url(#noiseFilter);
/* Requires SVG noise filter in HTML */
```

**Generators:**
- [Grainy Gradients](https://grainy-gradients.vercel.app/)
- CSS noise via repeating SVG

**Examples:**
- [Stripe](https://stripe.com/) backgrounds
- Grained hero sections

---

### Vignette

**Definition:** Darkening at edges of image/viewport, brighter center.

**Effect:**
- Draws focus to center
- Cinematic quality
- Subtle depth

**CSS:**
```css
box-shadow: inset 0 0 100px rgba(0, 0, 0, 0.3);
/* or radial gradient overlay */
```

---

### Halftone

**Definition:** Pattern of dots simulating continuous tone (print technique).

**Characteristics:**
- Retro/pop art effect
- Comic book aesthetic
- Print nostalgia

**Implementation:** SVG filters or CSS patterns

---

### Glitch Effect

**Definition:** Digital distortion mimicking data corruption.

**Characteristics:**
- RGB color splitting
- Horizontal displacement
- Scan lines
- Cyberpunk/tech aesthetic

**Use Cases:**
- Gaming sites
- Tech/hacker themes
- Error states (stylized)

**Libraries:**
- [Glitch.js](https://github.com/sjhewitt/glitch.js)
- CSS animations

---

## 3D Effects

### Isometric

**Definition:** 3D representation at fixed 30° angles, no perspective.

**Characteristics:**
- Equal measurement on all axes
- No vanishing point
- Popular in illustrations
- Technical/architectural feel

**Examples:**
- [Illustrations](https://dribbble.com/tags/isometric)
- [Blush Illustrations](https://blush.design/)

---

### Perspective

**Definition:** 3D effect with vanishing point (realistic depth).

**CSS:**
```css
.container {
  perspective: 1000px;
}
.card {
  transform: rotateY(15deg);
}
```

**Use Cases:**
- Card flips
- 3D carousels
- Depth effects

---

### Floating Elements

**Definition:** Elements that appear to hover above the page with shadow.

**CSS:**
```css
.floating {
  animation: float 3s ease-in-out infinite;
  box-shadow: 0 20px 40px rgba(0,0,0,0.2);
}
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}
```

---

## Resources

- [CodePen](https://codepen.io/) — Effect examples and experiments
- [CSS Tricks](https://css-tricks.com/) — Effect tutorials
- [Codrops](https://tympanus.net/codrops/) — Advanced UI effects
- [Cubic Bezier](https://cubic-bezier.com/) — Easing function generator

---

*Part of the [Design Nomenclature Reference](index.md)*
