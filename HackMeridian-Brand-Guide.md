# HackMeridian Brand Guide

For designers. No code knowledge required.
If you need to make a change, update this document and notify the developer or Claude.

---

## Colors

The palette is intentionally minimal. Use colors as described below. Do not introduce new colors.

### Primary

| Name | Hex | Use |
|---|---|---|
| Generous Gold | `#FDDA24` | Hero background, primary visual areas |
| White | `#FFFFFF` | Navigation, cards, page background |

### Secondary

| Name | Hex | Use |
|---|---|---|
| Black | `#000000` | All body text, headings, CTA text |
| Gray | `#B2B2B2` | Borders, dividers, muted UI elements |

### Tertiary

Used sparingly — only for stage indicators. Do not use as background or primary UI color.

| Name | Hex |
|---|---|
| Jacaranda | `#8A7FCC` |
| Terracotta | `#D45C39` |
| River | `#4F98BF` |

---

## Typography

**One font only: Inter Tight**
Available on Google Fonts. All weights are sourced from there.

| Style | Weight | Used For |
|---|---|---|
| Eyebrow / Label | Bold (700) | Short labels above headlines |
| Headline | Light (300) | Main page and section headings |
| Subheadline | Light (300) | Supporting headings |
| Body | Regular (400) | Paragraph copy |
| Label MD | Medium (500) | Buttons and text links |

### Rules
- Do not introduce a second font.
- Do not use more than these five type styles.
- Headline text should feel light and editorial, not heavy.

---

## Logo

- The logo is an uploaded image file (`logomer.svg`).
- It must never be recreated as typed text.
- It sits in the top-left of the navigation on a white background.
- Do not recolor, resize disproportionately, or place on a non-white background.

---

## Spacing

Base unit is 6px. Spacing always follows this scale:

`6px · 8px · 12px · 16px · 20px · 24px · 32px`

Do not use arbitrary spacing values like 10px, 15px, or 22px.

---

## Layout

### Navigation
- White background.
- Logo on the left only.
- No navigation links until destinations are confirmed.

### Hero
- Gold (`#FDDA24`) background — always.
- Two columns on desktop: copy on the left, artwork on the right.
- The artwork must never be cropped, stretched, or placed behind the full hero as a background.
- On mobile, the image stacks below the copy.

### Cards
- Three square cards on desktop.
- Cards are 1:1 aspect ratio — do not make them rectangular.
- Each card has: an image, overlay text on the image, a heading, and 20–30 words of body copy.
- Overlay text sits centered on the image and must have enough contrast to be readable.

### FAQ
- Sits below the cards.
- Section heading followed by expandable question/answer pairs.
- Click to expand, click again to collapse.

---

## Images

| Asset | Location | Notes |
|---|---|---|
| Logo | `assets/logomer.svg` | Do not replace with a raster file if possible |
| Hero artwork | `assets/Hero - image.png` | Preserve aspect ratio, never crop |
| Card 01 | `assets/card 1.png` | Square crop preferred |
| Card 02 | `assets/card2.png` | Square crop preferred |
| Card 03 | `assets/card 3 .png` | Square crop preferred |

When replacing an image: drop the new file into the `assets/` folder on GitHub with the same filename, or notify the developer with the new filename so they can update the reference.

---

## Copy Limitations

All copy must stay within these limits. Going over will break the layout.

| Content Type | Limit |
|---|---|
| Short Label / Eyebrow | Max 30 characters, max 4 words, 1 line |
| Headline / Heading | Max 60 characters, max 8 words, max 3 lines desktop / 4 mobile |
| Body Copy | 20–30 words, max 180 characters, max 4 lines desktop / 6 mobile |
| Image Overlay Copy | Max 40 characters, max 2 lines, recommended 2–5 words |
| CTA / Button | Max 30 characters, max 4 words, 1 line |
| Text Link | Optional. Max 30 characters, max 4 words, 1 line |
| FAQ Question | Max 100 characters, max 15 words, ideally 1–2 lines |
| FAQ Answer | Max 300 characters, max 50 words, ideally 3–5 lines |

All copy is written and approved in `copy/Master Copy Doc - website .md`.

---

## What You Can Change

| Change | How |
|---|---|
| Copy (text, headlines, CTAs) | Update the copy doc, notify developer |
| Images | Drop replacement into `assets/`, notify developer with new filename |
| Color usage rules | Update this Brand Guide, notify developer |
| New component or section | Update this Brand Guide + Design System, discuss with developer before building |

## What Requires a Developer

- Changing layout, grid, or spacing values
- Adding a new page
- Adding a new component
- Changing font sizes or weights
- Any changes to `index.html` or `style.css`

---

## Things to Never Do

- Do not introduce colors outside the defined palette.
- Do not use a font other than Inter Tight.
- Do not use the tertiary colors (Jacaranda, Terracotta, River) as backgrounds or primary UI.
- Do not crop or stretch the hero artwork.
- Do not make cards rectangular.
- Do not add navigation links until destinations are confirmed.
- Do not use heavy drop shadows as a default visual treatment.
- Do not exceed copy length limits — they exist to protect the layout.
