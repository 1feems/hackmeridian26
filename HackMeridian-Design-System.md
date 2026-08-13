# HackMeridian — Design System

Last updated: 2026-08-13
Status: Active — Homepage landing page

---

## Copy Limitations

All copy must stay within these limits to protect the layout at all breakpoints.

| Content Type | Limitation |
|---|---|
| Short Label / Eyebrow | Max 30 characters, max 4 words, 1 line |
| Headline / Heading | Max 60 characters, max 8 words, max 3 lines desktop / 4 mobile |
| Subcopy / Body Copy | 20–30 words, max 180 characters, max 4 lines desktop / 6 mobile |
| Image Overlay Copy | Max 40 characters, max 2 lines, recommended 2–5 words |
| CTA / Button | Max 30 characters, max 4 words, 1 line |
| Text Link | Optional. Max 30 characters, max 4 words, 1 line |
| FAQ Question | Max 100 characters, max 15 words, ideally 1–2 lines |
| FAQ Answer | Max 300 characters, max 50 words, ideally 3–5 lines |

Source of truth for copy content: `copy/Master Copy Doc - website .md`

---

## Colors

```css
--color-bg: #FFFFFF;
--color-surface: #FFFFFF;
--color-primary: #FDDA24;
--color-secondary: #000000;
--color-ink: #000000;
--color-muted: #B2B2B2;
--color-border: #B2B2B2;

--color-jacaranda: #8A7FCC;
--color-terracotta: #D45C39;
--color-river: #4F98BF;
```

### Color usage

- Generous Gold `#FDDA24` — homepage hero and primary visual areas
- White `#FFFFFF` — navigation, cards, page background
- Black `#000000` — primary text, headings, CTA text
- Gray `#B2B2B2` — borders and muted UI
- Jacaranda `#8A7FCC` — tertiary/stage indicator
- Terracotta `#D45C39` — tertiary/stage indicator
- River `#4F98BF` — tertiary/stage indicator
- Tertiary colors are used sparingly.

---

## Typography

Font family: **Inter Tight**

```css
font-family: "Inter Tight", sans-serif;
```

| Role | Font | Weight | Size | Line Height | Letter Spacing |
|---|---|---:|---:|---:|---:|
| Eyebrow | Inter Tight | 700 | [VALUE] | 100% | 30% |
| Headline | Inter Tight | 300 | [VALUE] | 90% | [VALUE] |
| Subheadline | Inter Tight | 300 | [VALUE] | 115% | 0% |
| Body | Inter Tight | 400 | [VALUE] | 160% | 0% |
| Label MD | Inter Tight | 500 | 24px | 24px | 0% |

Typography sizes remain independently editable through the typography tokens.

---

## Spacing

Base unit: **6px**

### Scale

```text
1px
6px
8px
12px
16px
20px
24px
32px
```

### Layout spacing

```css
--section-padding: 32px;
--hero-gap: 32px;
--card-gap: 32px;
```

Use the established spacing scale rather than arbitrary spacing values.

---

## Shapes

The visual system uses simple geometric shapes with restrained corner rounding.

```css
--radius-md: 12px;
```

### Shape rules

- Cards use a square 1:1 aspect ratio.
- Image blocks follow the card shape.
- Buttons use the established medium radius.
- Text links remain unrounded.
- Do not introduce arbitrary corner radii.

---

## Elevation & Depth

Depth is communicated primarily through flat surfaces, spacing, and restrained border contrast.

Heavy shadows are not the default visual treatment.

### Flat surface

Primary surfaces should remain visually flat.

### Border contrast

Use subtle gray borders to distinguish cards and supporting surfaces.

### Shadow

Use shadows sparingly, primarily for interactive states such as hover.

---

## Components

### Primary CTA

```yaml
button-primary:
  backgroundColor: "{colors.surface}"
  textColor: "{colors.secondary}"
  typography: "{typography.label-md}"
  rounded: "{rounded.md}"
  padding: "0px"
```

### Text Link

```yaml
button-link:
  textColor: "{colors.secondary}"
  typography: "{typography.label-md}"
  rounded: "0px"
  padding: "0px"
```

CTA text and URLs must be editable independently from component styling.

---

# Homepage

The homepage is a focused event landing page whose primary purpose is to drive applications for HackMeridian.

Desktop structure:

```text
WHITE NAVIGATION
        ↓
YELLOW TWO-COLUMN HERO
        ↓
THREE IMAGE-LED SQUARE CARDS
```

The homepage should not be interpreted as a generic SaaS/product landing page.

---

## Homepage Navigation

The navigation sits on a white background above the yellow hero.

There are currently no navigation destinations. Do not add placeholder navigation links.

### Navigation layout

```text
┌──────────────────────────────────────────────────────────────┐
│  [LOGO IMAGE]                                                │
└──────────────────────────────────────────────────────────────┘
```

### Navigation specifications

```css
display: flex;
align-items: center;
justify-content: space-between;
background: #FFFFFF;
padding: 32px;
```

### Logo

The logo is an uploaded image asset. It must not be recreated as text.

```yaml
logo:
  src: "/assets/hackmeridian-logo.[FILETYPE]"
  alt: "[EDITABLE ALT TEXT]"
```

---

## Homepage Hero

The homepage hero is a Generous Gold `#FDDA24` two-column section.

The hero must remain a two-column composition on desktop:

```text
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│  HERO CONTENT                         HERO IMAGE             │
│                                                              │
│  [LABEL]                              [UPLOADED IMAGE]        │
│                                                              │
│  [HEADLINE]                                                    │
│                                                              │
│  [DESCRIPTION]                                                │
│                                                              │
│  [PRIMARY CTA]                                                │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

### Hero layout

```css
background: #FDDA24;
display: grid;
grid-template-columns: 1fr 1fr;
align-items: center;
gap: 32px;
padding: 32px;
```

### Hero content

```yaml
hero:
  label: "[EDITABLE LABEL]"
  title: "[EDITABLE HEADLINE]"
  description: "[EDITABLE DESCRIPTION]"

  primaryCta:
    text: "Apply for the Hackathon"
    href: ""

  secondaryLink:
    text: "[EDITABLE LINK TEXT]"
    href: ""
```

An empty `href` means the destination has not yet been defined.

### Hero Content Limitations

These limitations define the intended copy length so content can be written to fit the established hero composition without requiring layout changes.

#### Label

- Editable text.
- Maximum 30 characters.
- Maximum 4 words.
- Maximum 1 line.
- Should function as a short contextual label or eyebrow.

#### Headline

- Editable text.
- Maximum 60 characters.
- Maximum 8 words.
- Maximum 3 lines on desktop.
- Maximum 4 lines on mobile.
- Should communicate the primary message of the hackathon.
- Do not use multiple heading levels within the hero.

#### Description

- Editable text.
- Recommended 20–30 words.
- Maximum 180 characters.
- Maximum 4 lines on desktop.
- Maximum 6 lines on mobile.
- Single paragraph.
- Should support and clarify the headline rather than introduce a second headline.

#### Primary CTA

- Editable text.
- Maximum 30 characters.
- Maximum 4 words.
- Maximum 1 line.
- Must communicate a clear action.
- The primary CTA remains the main conversion action on the page.

#### Secondary Link

- Optional.
- Editable text.
- Maximum 30 characters.
- Maximum 4 words.
- Maximum 1 line.
- Does not render when no text or URL is provided.
- Must remain visually secondary to the primary CTA.

### Hero image

```yaml
heroImage:
  src: "/assets/hackmeridian-hero.[FILETYPE]"
  alt: "[EDITABLE ALT TEXT]"
  position: "right"
  fit: "contain"
  crop: false
  stretch: false
```

The image must remain in the right column.

Do not:

- Make the image full-bleed.
- Use the image as the entire hero background.
- Crop the artwork.
- Stretch the artwork.
- Remove the right-side image.

---

## Homepage Cards

The homepage contains three event-focused cards below the hero.

The cards communicate:

1. Who the hackathon is for
2. Where the hackathon takes place
3. What opportunity comes from attending ahead of Meridian

### Desktop layout

```css
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: var(--card-gap);
padding: var(--section-padding);
```

### Card Design Tokens

```css
--card-aspect-ratio: 1 / 1;
--card-gap: 32px;
--card-padding: 24px;
--card-radius: 12px;
--card-border: 1px solid #B2B2B2;
```

Card size, aspect ratio, spacing between cards, internal padding, border radius, and border must remain independently editable through these design tokens.

### Card Shape

Cards are square with a 1:1 aspect ratio.

Cards should be visually separated through consistent spacing.

```text
┌───────────────────────────────┐
│                               │
│            IMAGE              │
│                               │
│       OVERLAY TEXT            │
│                               │
├───────────────────────────────┤
│                               │
│  HEADING                      │
│                               │
│  Supporting copy across       │
│  approximately 2–3 lines.     │
│                               │
│  OPTIONAL TEXT LINK           │
│                               │
└───────────────────────────────┘
```

### Card Structure

Every card follows:

```text
IMAGE
↓
OPTIONAL IMAGE OVERLAY TEXT
↓
HEADING
↓
20–30 WORDS OF SUPPORTING COPY
↓
OPTIONAL TEXT LINK
```

Each card has one heading only.

Do not add an eyebrow + subheading + main heading hierarchy inside cards.

### Card Image

Each card has an independently editable image asset and optional editable overlay text.

```yaml
cards:
  card-01:
    image:
      src: "/assets/card-01.[FILETYPE]"
      alt: "[EDITABLE ALT TEXT]"
      overlayText: "[EDITABLE IMAGE OVERLAY TEXT]"
      overlayPosition: "center"

  card-02:
    image:
      src: "/assets/card-02.[FILETYPE]"
      alt: "[EDITABLE ALT TEXT]"
      overlayText: "[EDITABLE IMAGE OVERLAY TEXT]"
      overlayPosition: "center"

  card-03:
    image:
      src: "/assets/card-03.[FILETYPE]"
      alt: "[EDITABLE ALT TEXT]"
      overlayText: "[EDITABLE IMAGE OVERLAY TEXT]"
      overlayPosition: "center"
```

The image should occupy a substantial portion of the card.

Overlay text sits directly over the image and is centered.

Overlay text must remain editable text and must not be baked into the image asset.

Overlay text must have sufficient contrast against the image.

### Card Content Limitations

These limitations define the intended copy length so content can be written to fit the established card composition without requiring layout changes.

#### Image Overlay Text

- Editable text.
- Maximum 40 characters.
- Maximum 2 lines.
- Recommended 2–5 words.
- Centered on the image.
- Should communicate the immediate message or benefit of the card.
- Should not simply repeat the card heading.

#### Heading

- Editable text.
- Maximum 30 characters.
- Maximum 5 words.
- Maximum 2 lines.
- Should identify or contextualize the card.

#### Body

- Editable text.
- 20–30 words.
- Maximum 3 lines on desktop.
- Maximum 4 lines on mobile.
- Single paragraph.
- Should provide supporting detail for the overlay and heading.

#### Text Link

- Optional.
- Maximum 30 characters.
- Maximum 4 words.
- Text and URL are independently editable.
- Does not render when no text or URL is provided.
- Uses the established text-link component.

---

### Card 01

```yaml
card-01:
  heading: "Lorem Ipsum Dolor"
  body: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam finibus interdum tellus, eget elementum."

  image:
    src: "/assets/card-01.[FILETYPE]"
    alt: "[EDITABLE ALT TEXT]"
    overlayText: "LOREM IPSUM DOLOR"
    overlayPosition: "center"

  textLink:
    text: "Lorem Ipsum"
    href: ""
```

---

### Card 02

```yaml
card-02:
  heading: "Lorem Ipsum Dolor"
  body: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam finibus interdum tellus, eget elementum."

  image:
    src: "/assets/card-02.[FILETYPE]"
    alt: "[EDITABLE ALT TEXT]"
    overlayText: "LOREM IPSUM DOLOR"
    overlayPosition: "center"

  textLink:
    text: "Lorem Ipsum"
    href: ""
```

---

### Card 03

```yaml
card-03:
  heading: "Lorem Ipsum Dolor"
  body: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam finibus interdum tellus, eget elementum."

  image:
    src: "/assets/card-03.[FILETYPE]"
    alt: "[EDITABLE ALT TEXT]"
    overlayText: "LOREM IPSUM DOLOR"
    overlayPosition: "center"

  textLink:
    text: "Lorem Ipsum"
    href: ""
```

### Responsive Card Layout

```css
desktop:
  grid-template-columns: repeat(3, 1fr);
  gap: var(--card-gap);

tablet:
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;

mobile:
  grid-template-columns: 1fr;
  gap: 16px;
```

Cards remain 1:1 at all breakpoints.

Card padding may be reduced at smaller breakpoints without changing the card aspect ratio.

```css
desktop:
  --card-padding: 24px;

tablet:
  --card-padding: 20px;

mobile:
  --card-padding: 16px;
```

---

## Homepage FAQ

The FAQ section sits below the cards on a white background. It uses a section heading and a list of expandable accordion items.

### FAQ Layout

```css
background: #FFFFFF;
padding: var(--section-padding);
max-width: 800px;
margin: 0 auto;
```

### FAQ Heading

- Typography role: Subheadline (Inter Tight, weight 300)
- Editable text.

### FAQ Item Structure

```text
┌──────────────────────────────────────────────┐
│  QUESTION TEXT                            ▾  │
├──────────────────────────────────────────────┤
│  Answer text — visible when expanded.        │
└──────────────────────────────────────────────┘
```

Each FAQ item:
- Question acts as the toggle trigger.
- Answer is hidden by default, revealed on click.
- Click again to collapse.
- Uses the native HTML `<details>` and `<summary>` elements.

### FAQ Design Tokens

```css
--faq-border: 1px solid #B2B2B2;
--faq-padding: 20px 0;
--faq-answer-padding: 12px 0 20px;
```

### Adding a Question

To add a new FAQ item, copy one `<details>` block in `index.html` and update the question and answer text. No layout or style changes required.

### FAQ Content Limitations

#### Question
- Editable text.
- Maximum 100 characters.
- Maximum 15 words.
- Ideally 1–2 lines.

#### Answer
- Editable text.
- Maximum 300 characters.
- Maximum 50 words.
- Ideally 3–5 lines.

---

## Editable Content & Assets

All content and assets must be separated from layout and component styling.

Editable items:

```text
NAVIGATION
└── Logo image

HERO
├── Label
├── Headline
├── Description
├── Primary CTA text
├── Primary CTA URL
├── Secondary link text
├── Secondary link URL
└── Hero image

CARD 01
├── Heading
├── Body
├── Image
├── Image overlay text
├── Image overlay position
├── Text link text
└── Text link URL

CARD 02
├── Heading
├── Body
├── Image
├── Image overlay text
├── Image overlay position
├── Text link text
└── Text link URL

CARD 03
├── Heading
├── Body
├── Image
├── Image overlay text
├── Image overlay position
├── Text link text
└── Text link URL
```

Changing these must not require changing the underlying layout.

---

## Assets

The GitHub project should contain an assets directory.

```text
/assets
├── hackmeridian-logo.[FILETYPE]
├── hackmeridian-hero.[FILETYPE]
├── card-01.[FILETYPE]
├── card-02.[FILETYPE]
└── card-03.[FILETYPE]
```

Actual filenames may change when assets are uploaded.

Images should be referenced by file path rather than embedded into the layout specification.

---

## Links

All links have editable text and URL values.

```yaml
links:
  hero-primary:
    text: "Apply for the Hackathon"
    href: ""

  hero-secondary:
    text: "[EDITABLE]"
    href: ""

  card-01:
    text: "[EDITABLE]"
    href: ""

  card-02:
    text: "[EDITABLE]"
    href: ""

  card-03:
    text: "[EDITABLE]"
    href: ""
```

URLs are intentionally empty until destinations are available.

Do not invent URLs.

---

## Responsive Layout

Desktop is the primary design reference.

### Desktop

```css
hero:
  grid-template-columns: 1fr 1fr;

cards:
  grid-template-columns: repeat(3, 1fr);
```

### Tablet

```css
hero:
  grid-template-columns: 1fr 1fr;

cards:
  grid-template-columns: repeat(2, 1fr);
```

### Mobile

```css
hero:
  grid-template-columns: 1fr;
  image-order: after-content;

cards:
  grid-template-columns: 1fr;
```

---

## Motion

Motion should remain restrained and should never alter the established composition.

```yaml
motion:
  duration: "[VALUE]"
  easing: "[VALUE]"
  cardHover:
    transform: "[VALUE]"
  transition: "[VALUE]"
```

---

## Do's and Don'ts

### Do

- Keep navigation white.
- Use the uploaded logo image in the navigation.
- Keep the homepage hero Generous Gold `#FDDA24`.
- Keep the hero as a contained two-column layout.
- Keep hero content on the left.
- Keep the HackMeridian artwork on the right.
- Preserve the hero artwork aspect ratio.
- Keep three square cards on desktop.
- Keep cards at a 1:1 aspect ratio.
- Use a substantial image area within each card.
- Allow editable overlay text over the card image.
- Center overlay text on the image.
- Use one heading per card.
- Keep supporting card copy around 20–30 words.
- Keep hero copy within the defined content limitations.
- Keep CTA text editable.
- Keep CTA URLs editable.
- Keep text-link text editable.
- Keep text-link URLs editable.
- Keep text links optional.
- Keep card images independently editable.
- Keep card padding independently editable.
- Keep card gap independently editable.
- Keep card radius independently editable.
- Keep card border independently editable.
- Keep the application CTA as the primary conversion action.
- Use Inter Tight.
- Use the established spacing scale.
- Keep the visual treatment clean, flat, and editorial.

### Don't

- Don't add placeholder navigation links.
- Don't turn the hero into a full-bleed image.
- Don't remove the hero image.
- Don't place the hero image behind the entire hero.
- Don't crop or stretch the hero artwork.
- Don't make cards rectangular or excessively horizontal.
- Don't make cards excessively text-heavy.
- Don't exceed the defined hero content limitations without updating the design system.
- Don't add multiple heading levels inside cards.
- Don't include the full venue address in the card.
- Don't bake overlay text into images.
- Don't hardcode URLs into visual components.
- Don't render an optional text link when no text or URL is provided.
- Don't invent URLs when destinations are not available.
- Don't require a layout rebuild when copy, images, or URLs change.
- Don't introduce additional colors outside the established palette.
- Don't use heavy shadows as the default card treatment.
- Don't reinterpret the homepage as a generic SaaS/product landing page.