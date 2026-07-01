# NovaMind AI — Landing Page

> **"Your Second Mind for Better Thinking."**  
> A premium, fully static landing page built with semantic HTML5 and CSS3 — no frameworks, no JavaScript, no dependencies.

---

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Live Preview](#2-live-preview)
3. [Tech Stack](#3-tech-stack)
4. [Project Structure](#4-project-structure)
5. [Page Sections](#5-page-sections)
6. [Design System](#6-design-system)
7. [Responsive Breakpoints](#7-responsive-breakpoints)
8. [Accessibility](#8-accessibility)
9. [CSS Architecture](#9-css-architecture)
10. [Typography](#10-typography)
11. [Getting Started](#11-getting-started)
12. [Customisation Guide](#12-customisation-guide)
13. [Browser Support](#13-browser-support)
14. [Known Limitations](#14-known-limitations)
15. [Author](#15-author)

---

## 1. Project Overview

NovaMind AI is a **thinking-partner web app** — not a chatbot. The landing page communicates that distinction clearly through calm, intelligent design language inspired by products like Notion, Linear, and Apple.

This project was built as a **Frontend Internship submission** with the following goals:

| Goal | Approach |
|---|---|
| Premium visual design | Generous white space, refined typography, consistent spacing |
| Semantic, accessible HTML | Proper landmark elements, heading hierarchy, ARIA labels |
| No external dependencies | Zero JS, zero CSS frameworks, zero libraries |
| Full responsiveness | CSS Grid + Flexbox + `clamp()` fluid type |
| Portfolio-ready code quality | BEM class names, CSS custom properties, organised comments |

---

## 2. Live Preview

Open `index.html` directly in any modern browser — no build step or local server required.

```
novamind/
└── index.html   ← open this file
```

> **Note:** Google Fonts are loaded via CDN. An internet connection is needed for the correct typefaces to render.

---

## 3. Tech Stack

| Technology | Version | Purpose |
|---|---|---|
| HTML5 | — | Semantic document structure |
| CSS3 | — | Layout, visual design, micro-interactions |
| Google Fonts | CDN | Plus Jakarta Sans, Inter, IBM Plex Mono |
| JavaScript | **None** | All interactive elements (accordion, sticky nav) use native HTML/CSS |

**No frameworks. No libraries. No build tools.**

---

## 4. Project Structure

```
novamind/
├── index.html        # Complete HTML document (single page)
├── style.css         # Full stylesheet with CSS variables and BEM classes
└── README.md         # This file
```

All HTML and CSS are contained in two files to keep the project approachable and submission-ready.

---

## 5. Page Sections

The page is divided into **13 sections**, each contained in a semantic landmark element.

| # | Section | HTML Element | ID / Landmark |
|---|---|---|---|
| 1 | Sticky Navigation | `<header>` + `<nav>` | `aria-label="Primary navigation"` |
| 2 | Hero | `<section>` | `aria-label="Introduction"` |
| 3 | Social Proof / Statistics | `<section>` | `aria-label="Usage statistics"` |
| 4 | Before vs After | `<section>` | `aria-labelledby="transform-heading"` |
| 5 | Thinking Capabilities | `<section>` | `id="capabilities"` |
| 6 | How NovaMind Works | `<section>` | `id="how-it-works"` |
| 7 | Product Showcase / Dashboard | `<section>` | `id="showcase"` |
| 8 | Mission & Vision | `<section>` | `aria-labelledby="mission-heading"` |
| 9 | Testimonials | `<section>` | `aria-labelledby="testimonials-heading"` |
| 10 | Pricing | `<section>` | `id="pricing"` |
| 11 | FAQ (Accordion) | `<section>` | `id="faq"` |
| 12 | Contact + Newsletter | `<section>` | `id="contact"` |
| 13 | Footer | `<footer>` | — |

---

## 6. Design System

### Color Palette

| Token | Hex | Usage |
|---|---|---|
| `--color-bg` | `#F9F6F1` | Page background |
| `--color-surface` | `#FFFFFF` | Cards, panels, modals |
| `--color-text` | `#18181B` | Primary body text |
| `--color-text-secondary` | `#5A5A5A` | Supporting text, labels |
| `--color-accent` | `#4F46E5` | Primary CTA, active states, icons |
| `--color-accent-2` | `#14B8A6` | Secondary highlights, success states |
| `--color-highlight` | `#F59E0B` | Text highlights, floating badges |
| `--color-border` | `#E5E7EB` | Dividers, card borders, inputs |

### Spacing

| Token | Value | Usage |
|---|---|---|
| `--section-padding` | `clamp(4rem, 8vw, 7rem)` | Vertical padding between sections |
| `--max-width` | `1180px` | Content container width |

### Elevation

| Token | Value | Usage |
|---|---|---|
| `--shadow-soft` | `0 4px 16px rgba(24,24,27,0.06)` | Default card shadow |
| `--shadow-lift` | `0 12px 32px rgba(24,24,27,0.10)` | Hover / elevated state |

### Border Radius

| Token | Value | Usage |
|---|---|---|
| `--radius-sm` | `10px` | Panels, inputs, small cards |
| `--radius-md` | `14px` | Section cards, pricing, notebook |

---

## 7. Responsive Breakpoints

All breakpoints are defined inline using `@media` queries inside `style.css`.

| Breakpoint | Width | Layout changes |
|---|---|---|
| Desktop (default) | > 980px | Full multi-column layouts |
| Large tablet | ≤ 980px | Capabilities grid collapses to 2 columns |
| Tablet | ≤ 860px | Nav links hidden; hero, testimonials, pricing go single-column |
| Small tablet | ≤ 760px | Transform, mission, contact collapse; proof grid → 2 columns |
| Mobile | ≤ 540px | Capabilities → single column |
| Small mobile | ≤ 480px | Footer → single column |

Fluid typography is applied using `clamp()` — headings and section paddings scale continuously between viewport sizes without hard jumps.

---

## 8. Accessibility

| Feature | Implementation |
|---|---|
| Landmark roles | `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` |
| Heading hierarchy | One `<h1>` in the hero; all sections use `<h2>`; cards use `<h3>` |
| `aria-label` | Applied to all `<nav>` and `<section>` elements without visible headings |
| `aria-labelledby` | Sections with visible headings reference their `id` |
| `aria-hidden` | Decorative elements (icons, notebook mockup, dashboard) are hidden from screen readers |
| Keyboard navigation | All interactive elements are natively focusable; `:focus-visible` ring styled in accent colour |
| FAQ accordion | Uses native `<details>/<summary>` — keyboard accessible with no JavaScript |
| Reduced motion | `@media (prefers-reduced-motion: reduce)` disables all transitions and animations |
| Form labels | Every `<input>` and `<textarea>` has an associated `<label>` with matching `for`/`id` |
| Colour contrast | All text/background combinations meet WCAG AA minimum contrast ratios |

---

## 9. CSS Architecture

`style.css` is organised into **16 numbered sections**, each preceded by a comment block:

```css
/* ---------- 1.  CSS VARIABLES   ---------- */
/* ---------- 2.  RESET           ---------- */
/* ---------- 3.  UTILITIES       ---------- */
/* ---------- 4.  HEADER / NAV    ---------- */
/* ---------- 5.  HERO            ---------- */
/* ---------- 6.  SOCIAL PROOF    ---------- */
/* ---------- 7.  BEFORE / AFTER  ---------- */
/* ---------- 8.  CAPABILITIES    ---------- */
/* ---------- 9.  PROCESS         ---------- */
/* ---------- 10. SHOWCASE        ---------- */
/* ---------- 11. MISSION         ---------- */
/* ---------- 12. TESTIMONIALS    ---------- */
/* ---------- 13. PRICING         ---------- */
/* ---------- 14. FAQ             ---------- */
/* ---------- 15. CONTACT         ---------- */
/* ---------- 16. FOOTER          ---------- */
```

### Naming Convention

Classes follow a **BEM-inspired** pattern:

```
block                   .capability-card
block__element          .capability-card__icon
block--modifier         .price-card--highlighted
```

Utility classes (`.btn`, `.eyebrow`, `.highlight`, `.tag`, `.pill`) are kept small and reused across sections to avoid duplication.

---

## 10. Typography

| Role | Family | Weights used | Usage |
|---|---|---|---|
| Headings | Plus Jakarta Sans | 700, 800 | `<h1>`, `<h2>`, `<h3>`, logo |
| Body | Inter | 400, 500, 600 | Paragraphs, nav, buttons, labels |
| Mono / Labels | IBM Plex Mono | 400, 500 | Eyebrows, tags, dashboard labels, panel captions |

Type scale uses `clamp()` for major headings:

```css
/* Hero headline */
font-size: clamp(2.4rem, 5vw, 3.6rem);

/* Section headings */
font-size: clamp(1.75rem, 3vw, 2.5rem);

/* Section padding */
padding: clamp(4rem, 8vw, 7rem);
```

---

## 11. Getting Started

### Prerequisites

- Any modern web browser (Chrome, Firefox, Safari, Edge)
- No Node.js, no npm, no build step required

### Running Locally

1. Download or clone the project folder.
2. Ensure `index.html` and `style.css` are in the **same directory**.
3. Open `index.html` in your browser.

```bash
# If you have Python installed, you can also spin up a quick local server:
python3 -m http.server 8080
# Then open http://localhost:8080 in your browser
```

### Folder Placement

```
your-folder/
├── index.html    ✓
├── style.css     ✓  (must be alongside index.html)
└── README.md
```

---

## 12. Customisation Guide

### Change the colour scheme

All colours are CSS custom properties in `:root` at the top of `style.css`. Edit them once and they apply everywhere:

```css
:root {
  --color-accent: #4F46E5;   /* ← change this to update all CTAs and accents */
  --color-bg:     #F9F6F1;   /* ← change this for the page background */
}
```

### Change the fonts

Replace the Google Fonts `<link>` in `<head>` and update the font variables:

```css
:root {
  --font-heading: 'Your Heading Font', sans-serif;
  --font-body:    'Your Body Font', sans-serif;
  --font-mono:    'Your Mono Font', monospace;
}
```

### Add a new section

1. Add a `<section>` inside `<main>` in `index.html` with an `aria-labelledby` attribute.
2. Add a corresponding `<h2>` with a matching `id`.
3. Add a new comment block in `style.css` and write styles scoped to your new section's class name.

### Update pricing

Pricing copy is in the `<!-- PRICING -->` section of `index.html`. Change the numbers, feature list items, and card headings directly in HTML.

---

## 13. Browser Support

| Browser | Support |
|---|---|
| Chrome 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 90+ | ✅ Full |
| Internet Explorer | ❌ Not supported |

> CSS custom properties, `clamp()`, CSS Grid, and native `<details>` are used throughout. IE does not support these features.

---

## 14. Known Limitations

- **No JavaScript:** The mobile navigation menu is hidden at narrow widths (≤ 860px) and not replaced with a hamburger menu, as this would require JavaScript. Consider adding a `<details>`-based menu for a JS-free toggle.
- **No real backend:** The contact form and newsletter form have no `action` attribute. Connect them to a service like Formspree, Netlify Forms, or a custom endpoint before deploying.
- **Fonts require internet:** Google Fonts are loaded via CDN. Self-host the font files for fully offline use.
- **Dashboard is decorative:** The product dashboard in Section 7 is a static HTML/CSS mockup with `aria-hidden="true"` — it is not interactive.

---

## 15. Author

**Built for a Frontend Internship submission.**

| | |
|---|---|
| Project | NovaMind AI Landing Page |
| Stack | HTML5 · CSS3 |
| Design inspiration | Notion · Linear · Apple |
| Purpose | Portfolio / internship submission |

---

*© 2026 NovaMind AI. All rights reserved.*