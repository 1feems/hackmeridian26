# HackMeridian Website

Homepage landing page for HackMeridian 2026.
Built with plain HTML and CSS. Deployed on Vercel via this GitHub repo.

---

## Who Reads What

| Document | Audience | Purpose |
|---|---|---|
| `HackMeridian-Brand-Guide.md` | Designers | Colors, typography, layout rules, image guidelines — no code required |
| `copy/Master Copy Doc - website .md` | Copy / Founders | All website text. This is the source of truth for copy |
| `HackMeridian-Design-System.md` | Developers | Code-level specs: CSS tokens, component structure, do's and don'ts |
| `README.md` | Everyone | This file — project overview and process |

---

## How to Update Copy

1. Edit `copy/Master Copy Doc - website .md` directly on GitHub
2. Message the developer (or Claude) with what changed and where
3. Developer updates the site code and pushes
4. Vercel redeploys automatically — live in ~30 seconds

**Never edit `index.html` directly.**

---

## How to Update Design

1. Designer updates `HackMeridian-Brand-Guide.md` with the change
2. If it affects code-level specs, also update `HackMeridian-Design-System.md`
3. Notify the developer — they translate the change into `style.css`
4. Push to GitHub → Vercel redeploys

---

## How to Swap Images

1. Drop the new image into the `assets/` folder on GitHub
2. If the filename is different from the original, notify the developer
3. Developer updates the image reference in `index.html` and pushes

---

## How to Add a New Page

Before any code is written:
1. Agree on the page structure and content in the copy doc
2. Update `HackMeridian-Design-System.md` with any new components needed
3. Developer builds the page following the existing design system
4. No new colors, fonts, or layout patterns without updating the design system first

---

## File Structure

```
/
├── index.html                        — Homepage (do not edit directly)
├── style.css                         — All styles (do not edit directly)
├── HackMeridian-Brand-Guide.md       — Designer reference
├── HackMeridian-Design-System.md     — Developer reference
├── README.md                         — This file
├── assets/
│   ├── logomer.svg                   — Logo
│   ├── Hero - image.png              — Hero artwork
│   ├── card 1.png                    — Card 01 image
│   ├── card2.png                     — Card 02 image
│   └── card 3 .png                   — Card 03 image
└── copy/
    └── Master Copy Doc - website .md — All website copy
```

---

## Deployment

- Repo: `github.com/1feems/hackmeridian-web26`
- Deploys automatically to Vercel on every push to `main`
- No build step — plain HTML/CSS
