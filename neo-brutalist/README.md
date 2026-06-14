# HAARIZZ — Harikrishnan T Nair · Portfolio

A single-file, **static** Neo-Brutalist developer portfolio. No React, no build step, no `npm install`.
Everything is in one `index.html` (styling via Tailwind CDN, interactions via vanilla JavaScript).

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire site (markup + styles + scripts) |
| `Harikrishnan-T-Nair-Resume.pdf` | Resume, linked from the "Hire Me" / "Resume" buttons |
| `vercel.json` | Optional Vercel config (clean URLs, caching, security headers) |
| `README.md` | This file |

## Run locally

Just open `index.html` in any browser. That's it.
(Optional) to serve it like a real host:

```bash
# Python
python -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to Vercel

You do **not** need a framework preset — this is a plain static site.

### Option A — Drag & drop (fastest, no Git)
1. Go to https://vercel.com/new
2. Drag this folder (`neo-brutalist_portfolio_home_(variant_1)`) onto the page.
3. Framework Preset: **Other** · Build Command: **(leave empty)** · Output Directory: **(leave empty / `.`)**
4. Click **Deploy**. Done — you get a live `*.vercel.app` URL.

### Option B — GitHub + Vercel (recommended for updates)
1. Put **the contents of this folder** at the root of a new GitHub repo
   (so `index.html` is at the repo root, not nested).
2. On https://vercel.com/new, **Import** that repo.
3. Framework Preset: **Other**, no build command, output dir `.`.
4. Deploy. Every `git push` now auto-deploys.

### Option C — Vercel CLI
```bash
npm i -g vercel
cd "neo-brutalist_portfolio_home_(variant_1)"
vercel        # preview deploy
vercel --prod # production deploy
```

> **Note on the folder name:** the current folder has spaces/parentheses.
> For Option B it's cleaner to copy `index.html`, the PDF, and `vercel.json`
> into a fresh repo root (e.g. `portfolio/`) so URLs stay tidy.

## Customizing later
- Text/sections: edit the relevant `<section>` in `index.html`.
- Accent color: change `primary` (`#f2f20d`) in the `tailwind.config` block near the top.
- Project links: search the file for `github.com/Haarizz`.
- Add real screenshots: drop image files in this folder and replace the icon
  placeholder `<div>`s inside each project card with `<img>` tags.

## Interactions (all vanilla JS, zero dependencies)
Draggable stickers · custom cursor · magnetic buttons · 3D card tilt ·
animated counters · typing hero · scroll progress bar · active-nav highlight ·
scroll reveals · dark mode. All respect `prefers-reduced-motion` and disable
cursor/tilt/magnetic effects on touch devices.
