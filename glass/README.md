# HAARIZZ — Harikrishnan T Nair · Portfolio (Glassmorphic variant)

A single-file, **static** glassmorphic developer portfolio. No React, no build step, no `npm install`.
Everything is in one `index.html` (Tailwind via CDN, interactions via vanilla JavaScript).

This is the **green glassmorphic** design. A separate Neo-Brutalist variant lives in
`../neo-brutalist_portfolio_home_(variant_1)/`.

## Files
| File | Purpose |
|------|---------|
| `index.html` | The entire site (markup + styles + scripts) |
| `Harikrishnan-T-Nair-Resume.pdf` | Resume, linked from "Hire Me" / about / nav |
| `vercel.json` | Optional Vercel config (clean URLs, caching, security headers) |

## Run locally
Open `index.html` in any browser. Done.
```bash
python -m http.server 8000   # optional: http://localhost:8000
```

## Deploy to Vercel
Static site — Framework Preset **Other**, no build command, output dir `.`.

**Drag & drop:** go to https://vercel.com/new and drop this folder.
**GitHub:** put this folder's contents at a repo root, import it on Vercel.
**CLI:** `npm i -g vercel` then `vercel --prod` from this folder.

## Interactions (all vanilla JS)
Typing hero · animated counters · scroll reveals · scroll progress bar ·
active-nav highlight · parallax background orbs · 3D tilt on project images ·
custom cursor · mobile menu. All respect `prefers-reduced-motion`; cursor/tilt/
parallax disable on touch devices.

## Customize
- Accent color: change `primary` (`#13ec5b`) in the `tailwind.config` block.
- Project links: search for `github.com/Haarizz`.
- Real screenshots: replace the icon-gradient `<div>`s in each project card with `<img>`.

> Note: the contact form uses a `mailto:` action as a no-backend fallback. For real
> submissions on Vercel, wire it to a form service (Formspree, Web3Forms) or a
> Vercel Serverless Function later.
