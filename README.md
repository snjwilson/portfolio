# Sanjay Wilson — Portfolio

A plain static portfolio site: **HTML + CSS + vanilla JS**, no build step, no dependencies.
Themed as a **retro arcade cabinet** (dark + teal, magenta/coin-yellow accents, CRT scanlines,
pixel fonts, a floating invader sprite).

## Structure

```
portfolio/
├── index.html              # The whole site (single page)
├── css/styles.css          # Arcade theme, CRT overlay, responsive layout
├── js/main.js              # Mobile nav, scroll reveal, footer year
├── assets/
│   ├── favicon.svg
│   ├── invader.svg         # Pixel invader sprite (hero + cards + logo)
│   └── Sanjay_Wilson_Resume.pdf   # ← add your resume PDF here
└── Sanjay_Wilson_Resume.docx       # Source resume (optional to commit)

**Fonts:** "Press Start 2P" + "VT323" are loaded from Google Fonts with
monospace fallbacks — the site still works fully offline, it just loses the
pixel type.
```

## Run locally

No build required. Either open `index.html` directly, or serve the folder:

```sh
python3 -m http.server 8000
# → http://localhost:8000
```

## TODO before going live

- [ ] **Resume PDF:** convert `Sanjay_Wilson_Resume.docx` to PDF and save it as
      `assets/Sanjay_Wilson_Resume.pdf` (the "Resume (PDF) ↓" button in the hero links to it).
- [ ] **Photo (optional):** if you want a headshot, drop an image into `assets/`
      and add a `<figure>` with it in the About section (`index.html`).
- [ ] **Project links (optional):** each card in "Selected Work" has a commented-out
      `<a class="card-link">` slot — uncomment and point it at a repo/demo URL.
- [ ] **Update the Open Graph `og:image`** in `index.html` if you add a social card.

## Deploying (any static host)

There's no build step, so the folder root is the publish directory.

### GitHub Pages
1. Create a repo (e.g. `sanjay-wilson.github.io` or any name) and push this folder.
2. Repo → **Settings → Pages → Source: Deploy from a branch** → `main` / root → Save.
3. Your site is live at `https://<username>.github.io/<repo>/`.

### Cloudflare Pages / Netlify / Vercel
1. Connect the repo.
2. Build command: leave **empty**. Publish directory: **`/`** (root).
3. Done.

## Customizing

- **Colors:** CSS variables at the top of `css/styles.css` (`--accent` teal, `--pink`,
  `--yellow`, `--bg`, `--border`, ...).
- **CRT effects:** scanlines/vignette live in the `body::before` / `body::after` rules
  — tweak opacity there or delete them for a flat look.
- **Content:** all resume-derived content lives in `index.html` — sections are clearly marked
  (STAGE 01–06).
