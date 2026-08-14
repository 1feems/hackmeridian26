# HackMeridian Website — Project Handoff

This document captures the current state of the project so any new session, developer, or collaborator can pick up exactly where we left off without starting fresh.

Last updated: 2026-08-13

---

## Project Overview

HackMeridian 2026 is a hackathon event hosted ahead of Meridian 2026 in Lisbon, Portugal. This site is the primary landing page to drive applications.

**Event:** October 25–26, 2026
**Location:** Lisbon, Portugal
**Primary CTA:** Apply to Hack (URL TBA)

---

## Repo & Deployment

| | |
|---|---|
| GitHub | `github.com/1feems/hackmeridian26` |
| Vercel | `https://hackmeridian26.vercel.app/` |
| Branch | `main` |
| Deploy trigger | Every push to `main` auto-deploys via Vercel |
| Build | None — plain HTML/CSS, no build step |

---

## File Structure

```
/
├── index.html                        — Homepage (do not edit directly)
├── style.css                         — All styles (do not edit directly)
├── HANDOFF.md                        — This file
├── README.md                         — Project overview and process for the team
├── HackMeridian-Brand-Guide.md       — Designer reference (plain English)
├── HackMeridian-Design-System.md     — Developer reference (code specs)
├── assets/
│   ├── hackmd26logo.svg              — Nav logo (800×400, SVG)
│   ├── stellar-logo-black.svg        — Footer logo (Stellar, black)
│   ├── Hero - image.png              — Hero artwork (right column)
│   ├── card 1.png                    — Card 01 image
│   ├── card2.png                     — Card 02 image
│   └── card 3 .png                   — Card 03 image
└── copy/
    └── Master Copy Doc - website .md — All website copy (source of truth)
```

---

## What's Built — Homepage

### Navigation
- White background
- Logo: `hackmd26logo.svg` at 48px height, auto width
- No nav links yet (none confirmed)

### Hero
- Gold (`#FDDA24`) two-column layout
- Left: label, headline, description, bold event date/location, CTA button
- Right: hero artwork image
- CTA "Apply to Hack" — **URL TBA**

### Cards (3 square cards)
| | Card 01 | Card 02 | Card 03 |
|---|---|---|---|
| Overlay | Build for the future | Build in the heart of Lisbon | Next Stop: Meridian |
| Heading | Choose Your Path | A Creative District by the River | Take It Further at Meridian |
| Link text | Apply | View | Explore |
| Link URL | **TBA** | https://www.oneyourfirststop.com/ | https://meridian.stellar.org/ |
| Link status | Comment in HTML — activate when URL confirmed | Live | Live |

### FAQ
4 questions, accordion (click to expand):
1. Do I need Stellar experience? → No.
2. Can I apply with an existing project? → Yes. Scale is designed for more experienced teams.
3. Can I apply alone? → Pending final policy.
4. Is travel support available? → Yes, for selected participants. Details coming soon.

### Footer
- Gold (`#FDDA24`) background matching hero
- Stellar black logo centered (`stellar-logo-black.svg` at 40px height, 200px width)
- Footer nav bar (social icons + legal links) — **placeholder in HTML, not yet activated**

---

## Pending Items

| Item | Status | Notes |
|---|---|---|
| Hero CTA URL | TBA | Application form link not yet available |
| Card 01 link URL | TBA | Text is "Apply" — activate when URL confirmed |
| Footer nav bar | Placeholder | Social icons (Discord, LinkedIn, X, YouTube) + legal links when ready |
| Nav links | None yet | No destinations confirmed |
| Card images | Placeholder | Real images to be dropped into `assets/` when ready |
| FAQ policy | Pending | "Can I apply alone?" answer pending final policy |

---

## Workflow

### To update copy
1. Edit `copy/Master Copy Doc - website .md` on GitHub
2. Tell Claude what changed and where
3. Claude updates `index.html` and pushes
4. Vercel redeploys automatically

### To update design
1. Designer updates `HackMeridian-Brand-Guide.md`
2. Tell Claude what changed
3. Claude updates `HackMeridian-Design-System.md` and `style.css` and pushes

### To swap an image
1. Drop new image into `assets/` folder on GitHub
2. If filename differs from original, tell Claude the new filename
3. Claude updates the `src` reference in `index.html` and pushes

### To activate a pending link
1. Update `copy/Master Copy Doc - website .md` with the confirmed URL
2. Tell Claude which card/section
3. Claude uncomments the link in `index.html` and pushes

### To add a new page
1. Agree on structure and copy in the copy doc
2. Designer adds specs to `HackMeridian-Brand-Guide.md`
3. Claude builds from the design system — no new colors, fonts, or layout patterns without updating the Brand Guide first

---

## Key Design Decisions

| Decision | Reason |
|---|---|
| Plain HTML/CSS (no framework) | Simple to deploy, no build step, anyone can read it |
| Gold footer matches hero | Brand consistency, design system spec |
| All links open in new tab | User experience — keeps site open |
| Fixed logo dimensions | Swapping logo image doesn't break layout |
| `object-fit: cover` on card images | Any image fills the square without stretching |
| `details`/`summary` for FAQ | Native HTML accordion, no JavaScript needed |
| Copy doc separate from code | Non-technical team can update copy without touching code |

---

## Logo Notes

- **Nav logo:** `hackmd26logo.svg` — SVG exported from Canva at 800×400. If replacing, keep same filename or update `src` in `index.html`. Fixed at 48px height.
- **Footer logo:** `stellar-logo-black.svg` — Black version of Stellar Development Foundation logo. Fixed at 40px height × 200px width.
- **Old logo:** `logomer.svg` still in `assets/` — no longer in use, can be deleted.

---

## Font

Inter Tight — loaded from Google Fonts in `style.css`. No installation needed.

```css
@import url("https://fonts.googleapis.com/css2?family=Inter+Tight:wght@300;400;500;700&display=swap");
```

---

## Who Reads What

| Document | Audience |
|---|---|
| `HANDOFF.md` | Everyone — project status and context |
| `README.md` | Everyone — process and file guide |
| `HackMeridian-Brand-Guide.md` | Designers |
| `copy/Master Copy Doc - website .md` | Copy / Founders |
| `HackMeridian-Design-System.md` | Developers |
