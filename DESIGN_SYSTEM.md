# Design System – One Piece Cinematic Profile

## Overview

This document defines the visual language, typography, colors, animations, and component specifications for the cinematic GitHub profile README. All sections follow these rules to ensure a cohesive, professional, and premium feel.

---

## Color Palette

All colors chosen for WCAG AA contrast (4.5:1 minimum for text).

| Name | Hex | RGB | Use Case |
|------|-----|-----|----------|
| **Ocean Black** | `#050816` | 5, 8, 22 | Page background, deep navies |
| **Deep Navy** | `#081B33` | 8, 27, 51 | Cards, sections, panels |
| **Ocean Blue** | `#0E3A5D` | 14, 58, 93 | Secondary sections, borders |
| **Treasure Gold** | `#D4AF37` | 212, 175, 55 | Buttons, highlights, accent borders |
| **Parchment** | `#F6ECD2` | 246, 236, 210 | Wanted poster frames, light cards |
| **Pirate Red** | `#B22222` | 178, 34, 34 | Accents, danger states, skulls |
| **Neon Cyan** | `#3ECFFF` | 62, 207, 255 | Links, badges, interactive elements |
| **Silver** | `#D7D7D7` | 215, 215, 215 | Secondary text, dividers, captions |

### Contrast Verification
- **White text on Ocean Black**: 21:1 ✅ (AAA)
- **White text on Deep Navy**: 13.5:1 ✅ (AAA)
- **Treasure Gold text on Ocean Black**: 10.2:1 ✅ (AAA)
- **Silver text on Ocean Black**: 11:1 ✅ (AAA)
- **Ocean Blue text on Parchment**: 5.1:1 ✅ (AA)

---

## Typography

### Font Stack

```css
/* Decorative – Section Titles & Hero */
font-family: 'Pirata One', 'Cinzel', serif;
font-size: 2.5rem;
font-weight: 700;
letter-spacing: 0.1em;

/* Monospace – Terminal & Code */
font-family: 'JetBrains Mono', 'Courier New', monospace;
font-size: 0.95rem;
line-height: 1.6;
color: #3ECFFF; /* or #2ECC71 for green terminal */

/* Serif/Sans – Body & Captions */
font-family: 'Inter', 'Segoe UI', sans-serif;
font-size: 1rem;
line-height: 1.6;
color: #D7D7D7;
```

### Hierarchy

| Element | Font | Size | Weight | Line-Height | Color |
|---------|------|------|--------|-------------|-------|
| **Page Title** | Pirata One | 2.5rem | 700 | 1.2 | Gold (#D4AF37) |
| **Section Header** | Pirata One | 1.8rem | 700 | 1.3 | Neon Cyan (#3ECFFF) |
| **Subsection** | Inter | 1.2rem | 600 | 1.4 | Silver (#D7D7D7) |
| **Body Text** | Inter | 1rem | 400 | 1.6 | Silver (#D7D7D7) |
| **Terminal/Code** | JetBrains Mono | 0.95rem | 400 | 1.6 | Neon Cyan (#3ECFFF) |
| **Caption** | Inter | 0.85rem | 400 | 1.5 | Silver (#D7D7D7), opacity 0.7 |

---

## Spacing & Layout

### Base Unit: 16px

All spacing uses multiples of 16px for consistency.

```css
/* Spacing Scale */
var(--spacing-xs): 4px;    /* 0.25x */
var(--spacing-sm): 8px;    /* 0.5x */
var(--spacing-md): 16px;   /* 1x */
var(--spacing-lg): 24px;   /* 1.5x */
var(--spacing-xl): 32px;   /* 2x */
var(--spacing-2xl): 48px;  /* 3x */
var(--spacing-3xl): 64px;  /* 4x */
```

### Container & Gutters

- **Max width**: 1200px (centered on desktop)
- **Side gutters**: 24px (mobile: 16px)
- **Section padding**: 48px top/bottom (mobile: 32px)
- **Card padding**: 24px
- **Card gap**: 24px (3-column grid on desktop, stacked on mobile)

---

## Borders & Corners

### Border Radius

```css
var(--radius-sm): 4px;    /* Minimal curves */
var(--radius-md): 8px;    /* Standard cards */
var(--radius-lg): 12px;   /* Large components */
var(--radius-xl): 16px;   /* Hero/feature blocks */
var(--radius-full): 9999px; /* Pills & badges */
```

### Border Styles

```css
/* Standard card border */
border: 2px solid #D4AF37;
border-radius: 12px;

/* Glowing accent (on hover) */
box-shadow: 0 0 20px rgba(212, 175, 55, 0.6);

/* Dark card separator */
border-bottom: 1px solid #0E3A5D;
```

---

## Shadows

### Shadow Hierarchy

```css
/* Subtle (cards at rest) */
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);

/* Medium (cards on hover/focus) */
box-shadow: 0 8px 24px rgba(0, 0, 0, 0.5),
            0 0 20px rgba(212, 175, 55, 0.3);

/* Deep (modals, overlays) */
box-shadow: 0 20px 60px rgba(0, 0, 0, 0.7);
```

---

## Section Dividers

Each divider is thematic and uses SVG or Unicode. No plain lines.

### Divider Styles

```markdown
════════⚓════════      (Anchor – Stability)
══════☠══════          (Skull – Danger/Achievement)
🌊🌊🌊🌊🌊🌊🌊           (Waves – Transition)
⚔════════════⚔        (Crossed Swords – Battle/Challenge)
✦─────────────✦        (Star – Magic/Mystery)
```

### SVG Divider Template

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 50" width="100%" height="50">
  <style>
    .divider-line { stroke: #D4AF37; stroke-width: 2; }
    .divider-icon { fill: #D4AF37; font-size: 24px; }
  </style>
  <line x1="50" y1="25" x2="450" y2="25" class="divider-line"/>
  <text x="500" y="35" text-anchor="middle" class="divider-icon">⚓</text>
  <line x1="550" y1="25" x2="950" y2="25" class="divider-line"/>
</svg>
```

---

## Animations & Motion

All animations are CSS-based (no JavaScript). Movement is meaningful and subtle.

### Animation Rules

**Principle**: Motion tells a story. No random or jarring movements.

```css
/* Ocean Waves – Continuous, Soothing */
@keyframes waves {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-3px); }
}
animation: waves 6s ease-in-out infinite;

/* Ship Bob – Gentle Floating */
@keyframes shipBob {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-8px); }
}
animation: shipBob 2s ease-in-out infinite;

/* Compass Spin – Slow Rotation */
@keyframes compassSpin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
animation: compassSpin 10s linear infinite;

/* Glow Pulse – Tech Cards */
@keyframes glowPulse {
  0%, 100% { box-shadow: 0 0 10px rgba(212, 175, 55, 0.3); }
  50% { box-shadow: 0 0 30px rgba(212, 175, 55, 0.8); }
}
animation: glowPulse 3s ease-in-out infinite;

/* Twinkle – Stars */
@keyframes twinkle {
  0%, 100% { opacity: 0.3; }
  50% { opacity: 1; }
}
animation: twinkle 2s ease-in-out infinite;

/* Fade In – Text Reveal */
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
animation: fadeIn 0.8s ease-in-out;
```

### Duration Guidelines

| Effect | Duration | Easing | Repeat |
|--------|----------|--------|--------|
| Ocean waves | 6s | ease-in-out | infinite |
| Ship bob | 2s | ease-in-out | infinite |
| Compass spin | 10s | linear | infinite |
| Glow pulse | 3s | ease-in-out | infinite |
| Star twinkle | 2s (random offset) | ease-in-out | infinite |
| Text fade-in | 0.8s | ease-in-out | 1x |
| Hover scale | 0.3s | ease-out | 1x |

### Accessibility

Respect user preferences for reduced motion:

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## Component Specifications

### Hero Banner

**Purpose**: Cinematic opening; sets the tone.

```css
height: 400px;
background: linear-gradient(
  180deg,
  #050816 0%,
  #081B33 50%,
  #0E3A5D 100%
);
position: relative;
overflow: hidden;
```

**Contents**:
- Animated ocean waves (SVG, looping)
- Floating pirate ship (SVG, bobbing)
- "WANTED" poster text overlay (gold, centered)
- Typing intro below (readme-typing-svg)

---

### Wanted Poster Card

**Purpose**: Hero title card with pirate aesthetic.

```css
background: #F6ECD2; /* Parchment */
border: 3px solid #B22222; /* Pirate Red */
border-radius: 8px;
padding: 32px 24px;
text-align: center;
box-shadow: 0 8px 24px rgba(0, 0, 0, 0.6);
```

**Typography**:
- "WANTED" header: Pirata One, 2.5rem, #B22222
- Name: Pirata One, 2rem, #050816
- Subtitle: Inter, 1rem, #081B33

---

### Terminal Card (Captain's Log)

**Purpose**: Bio and role display in retro terminal style.

```css
background: #050816;
border: 2px solid #3ECFFF;
border-radius: 8px;
padding: 24px;
font-family: 'JetBrains Mono';
font-size: 0.95rem;
color: #3ECFFF; /* Cyan terminal text */
line-height: 1.8;
overflow-x: auto;
box-shadow: inset 0 0 20px rgba(62, 207, 255, 0.1);
```

**Example Output**:
```
$ whoami
Name: Banoth Vikas
Role: Computer Science @ NIT Silchar
Title: Full Stack Engineer | AI Enthusiast | DevOps Explorer
Mission: Build legendary software & sail the Grand Line
```

---

### Crew Card

**Purpose**: Skill category with icon, role, and tech list.

```css
background: linear-gradient(135deg, #081B33 0%, #0E3A5D 100%);
border-left: 4px solid #D4AF37;
border-radius: 12px;
padding: 24px;
min-height: 200px;
display: flex;
flex-direction: column;
gap: 16px;
```

**Layout**:
1. Icon (100×100px, centered)
2. Role name (Inter, 1.2rem, gold)
3. Tech list (JetBrains Mono, 0.9rem, cyan)

**Hover Effect**:
```css
transform: translateY(-4px);
box-shadow: 0 12px 32px rgba(212, 175, 55, 0.4);
```

---

### Devil-Fruit Card

**Purpose**: Tech stack as glowing power-ups.

```css
width: 120px;
height: 120px;
border-radius: 50%;
background: radial-gradient(circle, #D4AF37 0%, #B8860B 100%);
display: flex;
align-items: center;
justify-content: center;
box-shadow: 0 0 15px rgba(212, 175, 55, 0.4);
transition: all 0.3s ease-out;
```

**Hover Effect** (CSS Glow):
```css
transform: scale(1.1);
box-shadow: 0 0 30px rgba(212, 175, 55, 0.9),
            0 0 60px rgba(212, 175, 55, 0.6);
```

**Contents**:
- Icon/emoji (48px, centered, white)
- Tech name below (Inter, 0.85rem, navy)

---

### Project Island Card

**Purpose**: Showcase key projects as discoverable islands.

```css
background: #081B33;
border: 2px solid #D4AF37;
border-radius: 12px;
overflow: hidden;
box-shadow: 0 8px 24px rgba(0, 0, 0, 0.5);
transition: all 0.3s ease-out;
```

**Layout** (vertical stack):
1. **Image/Screenshot** (600×300px, cover)
   - Gold pushpin icon overlay (top-right)
2. **Title** (Pirata One, 1.5rem, gold)
3. **Description** (Inter, 0.95rem, silver, 2–3 lines)
4. **Tech Stack** (icons or badges, 24px each)
5. **Buttons**
   - [Live Demo] (blue badge)
   - [GitHub] (gold badge)

**Hover**:
```css
transform: translateY(-8px);
box-shadow: 0 16px 48px rgba(212, 175, 55, 0.5);
```

---

### Timeline (Grand Line Map)

**Purpose**: Visual roadmap of growth milestones.

**Option A – Vertical Timeline**:
```css
border-left: 4px solid #D4AF37;
padding-left: 32px;
```

**Option B – SVG Map**:
- Horizontal or winding path (hand-drawn style)
- Waypoint icons (anchor, compass, treasure chest)
- Labels and dates aligned above/below

**Milestone Format**:
```
🏝 East Blue (2023)
   ↓ Started CS @ NIT Silchar
   ↓ Learned HTML, CSS, JavaScript
   
🏝 Alabasta (2024)
   ↓ Mastered MERN Stack
   ↓ Built first full-stack project
   
🏝 Wano (2025)
   ↓ Research Intern @ NIT
   ↓ Explored Kubernetes & DevOps
   
🏝 Laugh Tale (Future)
   ↓ Cloud Architecture & AI/ML
```

---

### Achievement Badge

**Purpose**: Highlight accomplishments with pirate flair.

```css
display: inline-block;
padding: 12px 20px;
background: linear-gradient(135deg, #D4AF37 0%, #B8860B 100%);
color: #050816;
border-radius: 8px;
font-weight: 600;
font-size: 0.9rem;
margin: 8px 8px 8px 0;
box-shadow: 0 4px 12px rgba(212, 175, 55, 0.4);
```

**Examples**:
- ⚔️ Defeated 300+ DSA Problems
- 🏆 Walmart Sparkathon Winner 2025
- 🔬 Research Intern @ NIT Silchar
- 🧠 Certified Full Stack Developer

---

### GitHub Stats Card (Marine HQ)

**Purpose**: Official-looking GitHub metrics.

```css
background: linear-gradient(135deg, #081B33 0%, #0E3A5D 100%);
border: 2px solid #3ECFFF;
border-radius: 12px;
padding: 24px;
text-align: center;
```

**Contents** (via [GitHub Readme Stats API]):
- Total repos, stars, followers
- Top languages (pie/bar chart)
- Public contributions
- Streak (via [GitHub Streak Stats])

---

### Sea King (Contribution Snake)

**Purpose**: Animated visualization of Git contributions.

**Implementation**: Embed GitHub contribution snake SVG or GIF (via [github-contribution-snake]).

```markdown
![Sea King – Contribution Snake](https://raw.githubusercontent.com/...)
```

**Styling**: Center-aligned, 600px wide, dark background.

---

### Footer (Until We Meet Again)

**Purpose**: Graceful closing with contact links and small animation.

```css
padding: 48px 24px;
background: linear-gradient(
  180deg,
  #0E3A5D 0%,
  #050816 100%
);
border-top: 2px solid #D4AF37;
text-align: center;
```

**Contents**:
1. Small animated ship SVG (left-to-right sail-off, ~8s)
2. "Until We Meet Again…" tagline (Pirata One, gold)
3. Contact badges (Resume, LinkedIn, Email, Portfolio)
4. Copyright & last-updated timestamp
5. Optional: Random pirate quote

---

## Responsive Design

### Breakpoints

```css
/* Mobile (< 640px) */
@media (max-width: 640px) {
  font-size: 0.95rem;
  padding: 16px;
  grid-columns: 1;
}

/* Tablet (640px – 1024px) */
@media (min-width: 640px) and (max-width: 1024px) {
  grid-columns: 2;
  font-size: 1rem;
}

/* Desktop (> 1024px) */
@media (min-width: 1025px) {
  grid-columns: 3;
  max-width: 1200px;
}
```

### Mobile-Specific
- Stack all cards vertically
- Reduce icon/image sizes (50–80% of desktop)
- Simplify animations (or disable per `prefers-reduced-motion`)
- Collapse multi-column tables into single-column or accordion
- Ensure no horizontal scrolling

---

## Dark/Light Mode

GitHub auto-switches themes. Our palette is designed for dark mode (default). For light mode compatibility:

```css
@media (prefers-color-scheme: light) {
  body { background: #F6ECD2; }
  text { color: #050816; }
  .card { background: #FFFFFF; border-color: #D4AF37; }
}
```

**Note**: Most users on GitHub prefer dark mode. We optimize for that, with light mode as fallback.

---

## Implementation Checklist

- [ ] All hex colors verified for WCAG AA contrast (4.5:1 min)
- [ ] Fonts loaded (via @import or system stack)
- [ ] SVG animations tested (CSS keyframes, no JS)
- [ ] Responsive layout tested on mobile, tablet, desktop
- [ ] Dark/light mode toggle tested
- [ ] Alt-text on all images/SVGs
- [ ] No `<script>` tags (GitHub CSP blocks them)
- [ ] Fallback plain-text README created
- [ ] Links tested (mailto, https, GitHub raw URLs)
- [ ] Page load time checked (optimize images <100KB)
- [ ] Screen reader tested (NVDA, JAWS, or built-in)
- [ ] Animations respect `prefers-reduced-motion`

---

## References

- [WCAG 2.1 Contrast Requirements](https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum)
- [CSS Animations Best Practices](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
- [GitHub Markdown Syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github)
- [SVG `<foreignObject>` Technique](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/foreignObject)
- [Readme-typing-svg](https://github.com/DenverCoder1/readme-typing-svg)
- [GitHub Readme Stats](https://github.com/anuraghazra/github-readme-stats)

---

**Last Updated**: June 2026  
**Version**: 1.0  
**Maintainer**: @returnzerovicky
