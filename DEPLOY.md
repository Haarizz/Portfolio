# Deploy Guide — Harikrishnan T Nair · Portfolio

You have **5 portfolio designs** + a **hub page** that previews all of them. This guide
covers the two things you'll actually do: ship ONE design as your real portfolio, and
(optionally) ship the hub as a side link. Everything is static — no build, no `npm install`.

```
Portfolio_neo_brutalist/
├── index.html        ← HUB (previews all 5)
├── neo-brutalist/    ← v1  Bold yellow
├── glass/            ← v2  Green glass
├── terminal/         ← v3  Terminal (recommended)
├── architecture/     ← v4  Architecture map
└── build-log/        ← v5  Git build-log
```

After deploy, each design lives at a clean path:
`your-site.vercel.app/terminal/`, `.../glass/`, `.../architecture/`, etc.

---

## ⭐ Recommended strategy

1. **Pick ONE design** as your real portfolio → deploy it on your main URL (e.g. a custom
   domain or `haarizz.vercel.app`). Don't make all 5 your public face — one confident
   statement beats a menu.
2. **(Optional)** Deploy the **hub** as a *separate* Vercel project (e.g.
   `haarizz-designs.vercel.app`) to show off the range, or just keep it local.

My pick for a backend/systems engineer: **v3 Terminal** (most memorable) or
**v2 Glassmorphic** (most conventional-professional).

---

## A) Deploy your chosen design (the important one)

The cleanest path is to put the **contents of your chosen folder at a repo root** so
`index.html` sits at the top (folder names here contain spaces/parentheses, which make
ugly URLs — flattening avoids that).

### Steps (GitHub + Vercel — recommended, auto-deploys on push)
1. Create a new folder locally, e.g. `haarizz-portfolio/`.
2. Copy **into it** (from your chosen variant folder):
   - `index.html`
   - `Harikrishnan-T-Nair-Resume.pdf`
   - `vercel.json`
3. `git init`, commit, push to a new GitHub repo (`harikrishnan-portfolio`).
4. Go to **https://vercel.com/new** → **Import** that repo.
5. Framework Preset: **Other** · Build Command: **(empty)** · Output Directory: **`.`**
6. **Deploy.** You're live at `https://<repo>.vercel.app`. Every `git push` redeploys.

### Or — fastest, no Git (drag & drop)
1. Open your chosen variant folder.
2. Go to **https://vercel.com/new** and drag the folder onto the page.
3. Preset **Other**, no build command → **Deploy**.

### Or — Vercel CLI
```bash
npm i -g vercel
cd "terminal_dev_os_(variant_3)"   # ← your chosen folder
vercel          # preview
vercel --prod   # production
```

---

## B) Deploy the hub (optional, secondary)

The hub (`index.html` at the repo root) previews all 5 via iframes, so it needs the
**5 subfolders present** alongside it.

- **Drag & drop:** drag the **whole `Portfolio_neo_brutalist` folder** to vercel.com/new.
  The hub loads at `/`, each design at its subpath.
- **GitHub:** push the whole folder (root `index.html` + 5 subfolders) and import.

> Heads-up: the iframe previews load each full page. That's fine for a personal hub, but
> it's why the hub should be your *secondary* link, not your résumé URL.

---

## C) Custom domain (optional)

1. Buy a domain (Namecheap / GoDaddy / Cloudflare) — e.g. `haarizz.dev`.
2. In your Vercel project → **Settings → Domains → Add** → enter the domain.
3. Add the DNS records Vercel shows you at your registrar (usually an `A` record or
   `CNAME`). HTTPS is automatic.
4. Done — `https://haarizz.dev` serves your portfolio.

---

## D) Make the contact form actually deliver (do this later)

The glassmorphic design (v2) has a contact form using a `mailto:` fallback. To receive
real submissions on a static host, wire it to a free form service — **no backend code**:

### Web3Forms (free, recommended)
1. Get a free access key at **https://web3forms.com** (just enter your email).
2. In `glassmorphic_nature_portfolio_(variant_2)/index.html`, find the `<form id="contactForm" ...>`
   and replace its `action`/`method` with:
   ```html
   <form id="contactForm" action="https://api.web3forms.com/submit" method="POST">
     <input type="hidden" name="access_key" value="YOUR-KEY-HERE">
     <!-- keep the existing name / email / message inputs -->
   ```
3. Redeploy. Submissions now land in your inbox.

(Formspree works the same way — `action="https://formspree.io/f/yourid"`.)

When you're ready, send me your Web3Forms key and I'll wire it in for you.

---

## What's already done for you
- ✅ Every design: SEO meta, Open Graph + Twitter cards, favicon, `theme-color`
- ✅ Branded 1200×630 OG preview images per design (`/assets/og-*.svg`)
- ✅ Every design: `vercel.json` (clean URLs, PDF caching, security headers)
- ✅ Real links throughout (verified GitHub repos, LinkedIn, email, phone)
- ✅ Resume PDF bundled in each folder
- ✅ Contact form (glass design) is Web3Forms-ready
- ✅ `prefers-reduced-motion` + touch fallbacks

## Activate the contact form (1 minute)
The glass design's form works as a `mailto:` fallback out of the box. To receive real
submissions in your inbox:
1. Get a free key at **https://web3forms.com** (enter your email — that's the inbox).
2. Open `glass/index.html`, search for `WEB3FORMS_KEY`, and paste your key:
   `const WEB3FORMS_KEY = 'your-key-here';`
3. `git add -A && git commit -m "enable contact form" && git push` → auto-deploys.

> OG link-preview images are branded SVGs hosted at `/assets/`. SVG previews render on
> most platforms (X, Telegram, Discord, Slack). LinkedIn occasionally prefers PNG — if you
> want guaranteed LinkedIn previews, drop a 1200×630 PNG screenshot in `/assets/` and point
> the `og:image` at it.
