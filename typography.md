# Backyard Leisure — Typography System

> Updated March 2026 with confirmed logo fonts from official "Font & Colours.pdf".

---

## Font Families

### Alloy Bold — Logo Only ("BACKYARD")
- **Type:** Custom/specialty font — used exclusively in the logo wordmark
- **Character:** Heavy, geometric, bold — gives "BACKYARD" its strong presence
- **Do NOT use** for general headings, body copy, or web UI — logo only

### Moonlight — Logo Only ("LEISURE")
- **Type:** Custom/specialty font — used exclusively in the logo wordmark
- **Character:** Lighter, more refined — contrasts with the bold "BACKYARD" above it
- **Do NOT use** for general headings, body copy, or web UI — logo only

### Montserrat — Web Headings & Display (Google Fonts substitute)
- **Source:** Google Fonts (free) — https://fonts.google.com/specimen/Montserrat
- **Weights used:** 400 (Regular), 600 (SemiBold), 700 (Bold), 800 (ExtraBold)
- **Use for:** All headings (H1–H4), navigation, CTAs, pull quotes, product names
- **Character:** Geometric, modern, confident — closest web match to Alloy Bold's weight and feel
- **Why this substitute:** Alloy Bold is not available as a web font; Montserrat shares its geometric, heavy character

### Open Sans — Body & UI
- **Source:** Google Fonts (free) — https://fonts.google.com/specimen/Open+Sans
- **Weights used:** 400 (Regular), 600 (SemiBold)
- **Use for:** Body copy, captions, form labels, small UI text, product descriptions
- **Character:** Highly legible, warm, approachable — works at all sizes

### System Font Stack — Fallback
```css
font-family: 'Open Sans', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
```

---

## Type Scale

### Web / Digital

| Level | Element | Font | Weight | Size (desktop) | Size (mobile) | Line Height |
|---|---|---|---|---|---|---|
| Display | Hero headline | Montserrat | 800 | 56px / 3.5rem | 36px / 2.25rem | 1.1 |
| H1 | Page title | Montserrat | 700 | 40px / 2.5rem | 28px / 1.75rem | 1.2 |
| H2 | Section heading | Montserrat | 700 | 32px / 2rem | 24px / 1.5rem | 1.25 |
| H3 | Sub-section | Montserrat | 600 | 24px / 1.5rem | 20px / 1.25rem | 1.3 |
| H4 | Card title | Montserrat | 600 | 20px / 1.25rem | 18px / 1.125rem | 1.35 |
| Body Large | Intro paragraphs | Open Sans | 400 | 18px / 1.125rem | 16px / 1rem | 1.7 |
| Body | Standard copy | Open Sans | 400 | 16px / 1rem | 15px / 0.9375rem | 1.65 |
| Body Small | Captions, fine print | Open Sans | 400 | 14px / 0.875rem | 13px / 0.8125rem | 1.6 |
| Label | UI labels, nav | Montserrat | 600 | 13px / 0.8125rem | 12px / 0.75rem | 1.4 |
| CTA Text | Buttons | Montserrat | 700 | 15px / 0.9375rem | 14px / 0.875rem | 1 |

### Print

| Level | Font | Weight | Size |
|---|---|---|---|
| Cover headline | Montserrat | 800 | 48–60pt |
| Section heading | Montserrat | 700 | 24–32pt |
| Subheading | Montserrat | 600 | 16–20pt |
| Body copy | Open Sans | 400 | 10–11pt |
| Caption | Open Sans | 400 | 8–9pt |
| Footer/legal | Open Sans | 400 | 7–8pt |

---

## CSS Implementation

```css
/* Import */
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&family=Open+Sans:wght@400;600&display=swap');

/* Base */
:root {
  --font-heading: 'Montserrat', sans-serif;
  --font-body:    'Open Sans', -apple-system, sans-serif;

  --text-display: clamp(2.25rem, 5vw, 3.5rem);
  --text-h1:      clamp(1.75rem, 4vw, 2.5rem);
  --text-h2:      clamp(1.5rem, 3vw, 2rem);
  --text-h3:      clamp(1.25rem, 2.5vw, 1.5rem);
  --text-h4:      clamp(1.125rem, 2vw, 1.25rem);
  --text-lg:      1.125rem;
  --text-base:    1rem;
  --text-sm:      0.875rem;
  --text-xs:      0.8125rem;
}

body {
  font-family: var(--font-body);
  font-size: var(--text-base);
  line-height: 1.65;
  color: var(--bl-charcoal);
}

h1, h2, h3, h4, h5, h6 {
  font-family: var(--font-heading);
  font-weight: 700;
  line-height: 1.2;
  color: var(--bl-navy);
}
```

---

## Spacing & Rhythm

- **Base unit:** 8px
- **Heading margin-bottom:** 0.5em (tight connection to content below)
- **Paragraph spacing:** 1em bottom margin
- **Section padding:** 80px vertical (desktop), 48px (mobile)
- **Card padding:** 32px (desktop), 24px (mobile)

---

## Text Formatting Rules

### Capitalization
- Headlines: **Title Case** — "Build Your Backyard Sanctuary"
- CTAs: **Title Case** — "Get Started Today"
- Navigation: **Title Case** — "Hot Tubs", "Swim Spas"
- Body copy: **Sentence case** — standard prose rules
- ALL CAPS: Only for short labels/badges (max 3 words), never for body text

### Emphasis
- **Bold** (`font-weight: 700`) for key facts, product names, prices
- *Italic* sparingly — testimonial attributions, technical terms on first use
- Underline — links only, never for decorative emphasis

### Numbers & Prices
- Write out numbers under 10 in copy: "five years", "three seats"
- Use numerals for measurements and specs: "6-person", "120V"
- Prices: always include `$` and format with commas — `$12,999`

---

## ❌ Typography Don'ts
- Never use script/handwriting fonts in brand materials
- Never use more than 2 font families in a single document
- Never set body copy in Montserrat — it's too heavy for reading
- Never go below 12px on web, 8pt in print
- Never use `font-weight: 400` for Montserrat headings — minimum 600
- Never stretch or condense fonts — use appropriate font weights instead
