# adaptablestructures.com — rebuilt site

Static HTML site rebuilt from GoDaddy export, May 2026. Target deployment:
Cloudflare Pages via GitHub, matching the fullboundarycarbon.org architecture.

## What's here

```
adaptablestructures/
├── index.html                          → adaptablestructures.com/
├── about-as/index.html                 → /about-as/
├── y-design/index.html                 → /y-design/
├── anyplace-ecosystem/index.html       → /anyplace-ecosystem/
├── validation/index.html               → /validation/   (NEW)
├── news/index.html                     → /news/
├── news/f/{16 article slugs}/index.html
├── contact/index.html                  → /contact/
├── assets/
│   ├── styles.css                      → shared CSS
│   ├── images/                         → logo, exploded views, video poster
│   ├── video/                          → hero video (desktop + mobile)
│   └── favicon/                        → favicon assets (multiple sizes)
├── favicon.ico                         → root-level favicon
├── _redirects                          → Cloudflare Pages redirect rules
├── robots.txt
└── sitemap.xml
```

Total: 23 HTML files + CSS + 6 image assets + 2 video files + favicon set + 3 config files.

## Asset inventory

- `logo-anyplace.png` — Anyplace QR-house brand mark. Functional 2D barcode.
  Used in header (32px), home hero, footer, and as favicon source.
- `module-exploded-vertical.png` — full 46-part exploded view (vertical layout).
  Used on Home and About AS as the visual proof of the DfIND output.
- `module-exploded-horizontal.png` (and 1600px + JPG variants) — wide exploded
  view in color, showing frame + panels. Used on Anyplace Ecosystem.
- `video-poster.jpg` — still frame from the build animation, used as poster
  for the hero video before playback starts.
- `hero-desktop.mp4` (4.8MB, 1080p) and `hero-mobile.mp4` (3MB, 720p) — silent
  looping build animation auto-playing in the home hero.
- `favicon-*.png` and `favicon.ico` — browser tab and PWA icons in standard
  sizes (16, 32, 48, 64, 128, 192, 512).

## What was preserved

- All six original page paths (Home, About AS, Y Design, Anyplace Ecosystem,
  News, Contact)
- All 16 news article slugs (URLs unchanged so external links survive)
- Original tone and voice in each article body
- Site structure for SEO continuity

## What was changed (factual corrections only)

- "fewer than 50 parts" → "46 parts" (always was 46; old copy was approximate)
- Apostrophes removed from two slugs (`jean-nouvel's...`, `sparknz...o'neal`)
  with 301 redirects in `_redirects` to keep old URLs alive
- Patent grant year clarified (priority 2014, granted 2017) on main pages only

## What was added (May 2026 record)

- New `/validation/` page consolidating all accolades, structural tests,
  partnerships, IP record, media, and recognition into one canonical list
- Updated main pages (Home, About AS, Anyplace Ecosystem) to reflect current
  state: Hydro NA TEDA (Feb 2026), 98% measured material recovery, DRL
  publication, US production preparation
- Footer cross-linking to all five spoke domains and DRL research

## What was deliberately NOT changed

- Article bodies dated 2014–2025 remain in their original voice and reflect
  the state of the world at the time they were written. Hydro NA agreement,
  validated 98%, and DRL Codex are NOT mentioned in pre-2026 posts because
  none of these existed at the dates of those posts. The Wayback Machine has
  cached the original articles; backdating progress would create a diff anyone
  can find.

## Image placeholders

Every image on the old GoDaddy site lived on `img1.wsimg.com` and will be
inaccessible when GoDaddy hosting is decommissioned. The rebuilt pages have
`<div class="img-placeholder">` blocks marking where images should go.
Replace these with real `<img>` tags pointing to files in `assets/images/`.

Recommended images to source:
- Module assembly diagram (Home, About AS) — could use the 4L-3W-0000-001
  gable assembly PDF rendered to PNG
- DfMA vs DfIND comparison — the `DfMA_vs_DfIND.pdf` from project files
- Ecosystem diagram (Anyplace Ecosystem) — five-application diagram, new
- Article-specific images (where the old articles had photos)

## Deployment to Cloudflare Pages

1. Create a new GitHub repo (e.g. `adaptable-structures-site`).
2. Drag/drop or `git push` the entire `adaptablestructures/` folder contents
   to the repo root.
3. In Cloudflare Pages dashboard: "Create a project" → "Connect to Git" →
   select the repo.
4. Build settings:
   - Framework preset: **None**
   - Build command: *(leave blank)*
   - Build output directory: `/`
   - Root directory: `/`
5. Deploy. Site goes live at `*.pages.dev` URL.
6. To cut over: in Cloudflare Pages, add custom domain `adaptablestructures.com`.
   Then at GoDaddy DNS, point the domain to Cloudflare's nameservers (or
   create CNAME/A records per Cloudflare's instructions).
7. Keep GoDaddy domain registration. Move only DNS / hosting.

## Cleanup tasks remaining

- [ ] Source / generate images, drop into `assets/images/`, replace placeholders
- [ ] Two photo captions in `the-andes-house-reimagined...` are tagged as
      headings — edit inline or delete
- [ ] Review article body text for any remaining typography quirks from the
      GoDaddy export
- [ ] When you publish new posts going forward (Hydro NA Feb 2026, DRL May
      2026, Ivory Prize, BIM Munich, Massey, etc.), add them as new dated
      articles in `news/f/{slug}/index.html` and add the entry to
      `news/index.html` and `sitemap.xml`
