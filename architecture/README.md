# HAARIZZ — Harikrishnan T Nair · Portfolio
## Spatial Architecture Map

Your work as an interactive **system-architecture diagram** you pan & zoom. Nodes (frontend, API, DB, ERP modules, projects) connect with animated data-flow lines; click any node to inspect it. Cyber / neon-glass aesthetic.

Single-file **static** site — no React, no build step, no `npm install`.
Everything is in one `index.html` (Tailwind via CDN, vanilla JS).

## Files
- `index.html` — the entire site
- `Harikrishnan-T-Nair-Resume.pdf` — resume (linked in the UI)
- `vercel.json` — clean URLs, caching, security headers

## Run locally
Open `index.html` in any browser. (Optional: `python -m http.server 8000`.)

## Deploy to Vercel
Static site → Framework Preset **Other**, no build command, output dir `.`.
- **Drag & drop:** https://vercel.com/new → drop this folder.
- **GitHub:** put this folder's contents at a repo root, import on Vercel.
- **CLI:** `npm i -g vercel` then `vercel --prod`.

All animations respect `prefers-reduced-motion`; pointer-heavy effects degrade on touch.

> One of five portfolio designs. Siblings: neo-brutalist (v1), glassmorphic (v2),
> terminal/dev-os (v3), architecture-map (v4), build-log (v5).
