# Backyard Leisure — Color System

> Confirmed from official "Font & Colours.pdf" brand document (March 2026).
> Logo color hex values are hand-annotated on the document and confirmed.

---

## Primary Palette (from logo)

### Brand Teal — Primary Brand Color
- **Hex:** `#2F7769` (confirmed)
- **RGB:** 47, 119, 105
- **Use for:** Navigation bars, footer, primary headings, "BACKYARD" wordmark, CTAs, button backgrounds
- **Represents:** Trust, depth, water, nature — the dominant logo color

### Aqua — Secondary / Water Color
- **Hex:** `#79CBC5` (confirmed)
- **RGB:** 121, 203, 197
- **Use for:** Accent highlights, hover states, secondary buttons, icons, dividers, the water drop in the logo
- **Represents:** Water, vitality, the core product (hot tubs, pools, swim spas)

### Lime Green — Accent / Energy
- **Hex:** `#8FC855` (confirmed)
- **RGB:** 143, 200, 85
- **Use for:** Success states, accent details, the green leaf in the logo, badges, positive indicators
- **Represents:** Nature, freshness, growth, outdoor living

### Mint — Light Accent
- **Hex:** `#D0EFE9` (confirmed)
- **RGB:** 208, 239, 233
- **Use for:** Light backgrounds, card highlights, hover states, section accents, the lightest logo element
- **Represents:** Softness, invitation, calm

---

## Secondary Palette

### Off-White — Primary Background
- **Hex:** `#F8F6F2`
- **Use for:** Page backgrounds, card backgrounds, content sections
- **Never use:** Pure white `#FFFFFF` as the main background — it feels cold

### Charcoal — Body Text
- **Hex:** `#2C2C2C`
- **Use for:** All body copy, captions, descriptions
- **Never use:** Pure black `#000000` for body text

### Light Grey — Subtle UI
- **Hex:** `#E8E6E2`
- **Use for:** Borders, dividers, disabled states, form fields

### Deep Teal — Dark Variant
- **Hex:** `#1D5A4E`
- **Use for:** Darker variant of Brand Teal for gradients, hover states, footer backgrounds

### Sand — Warm Neutral (supplementary)
- **Hex:** `#C8A96E`
- **Use for:** Warm accent details, testimonial backgrounds, section dividers (complements the green/teal palette with warmth)

---

## Color Usage Rules

### Text on Backgrounds
| Background | Approved Text Colors |
|---|---|
| Off-White `#F8F6F2` | Charcoal `#2C2C2C`, Brand Teal `#2F7769` |
| Brand Teal `#2F7769` | White `#FFFFFF`, Off-White `#F8F6F2` |
| Aqua `#79CBC5` | Charcoal `#2C2C2C`, Brand Teal `#2F7769` |
| Mint `#D0EFE9` | Charcoal `#2C2C2C`, Brand Teal `#2F7769` |

### Button Colors
| Button Type | Background | Text | Border |
|---|---|---|---|
| Primary CTA | Brand Teal `#2F7769` | White | None |
| Secondary CTA | Transparent | Brand Teal | Brand Teal 2px |
| Ghost/Tertiary | Transparent | Aqua `#79CBC5` | Aqua 1px |
| Disabled | Light Grey | Mid Grey | None |

### Gradients (Approved)
- **Hero gradient:** Brand Teal `#2F7769` → Deep Teal `#1D5A4E` (135deg)
- **Subtle section break:** Off-White `#F8F6F2` → Light Grey `#E8E6E2` (top to bottom)
- **Logo-inspired:** Aqua `#79CBC5` → Brand Teal `#2F7769` (for decorative elements)
- **Avoid:** Rainbow, pastel-only, or purely decorative gradients

---

## CSS Variables (Web Implementation)

```css
:root {
  /* Brand colors (confirmed from brand doc) */
  --bl-teal:      #2F7769;
  --bl-aqua:      #79CBC5;
  --bl-green:     #8FC855;
  --bl-mint:      #D0EFE9;

  /* Supporting palette */
  --bl-offwhite:  #F8F6F2;
  --bl-charcoal:  #2C2C2C;
  --bl-lightgrey: #E8E6E2;
  --bl-deepteal:  #1D5A4E;
  --bl-sand:      #C8A96E;

  /* Semantic aliases */
  --color-primary:     var(--bl-teal);
  --color-secondary:   var(--bl-aqua);
  --color-accent:      var(--bl-green);
  --color-background:  var(--bl-offwhite);
  --color-text:        var(--bl-charcoal);
  --color-border:      var(--bl-lightgrey);
}
```

---

## Accessibility

- **Brand Teal on Off-White:** Contrast ratio ~5.1:1 — WCAG AA for normal text
- **Charcoal on Off-White:** Contrast ratio ~11.5:1 — WCAG AAA
- **White on Brand Teal:** Contrast ratio ~5.1:1 — WCAG AA
- **Charcoal on Mint:** Contrast ratio ~10.2:1 — WCAG AAA
- **Brand Teal on Mint:** Contrast ratio ~3.5:1 — WCAG AA for large text only

Always test contrast ratios when using Aqua or Lime Green as backgrounds with text.

---

## Forbidden Color Uses
- No neon or fluorescent colors
- No purple, pink, or orange — outside brand palette
- No pure black `#000000` for body text
- No pure white `#FFFFFF` as primary page background
- Do not use Lime Green for large background areas — accent use only
- Do not use Aqua for body text — insufficient contrast on white
