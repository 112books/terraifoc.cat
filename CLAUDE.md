# Terra i Foc — CLAUDE.md

## Project Overview

Hugo static site for **Terra i Foc**, an artisan ceramics workshop in El Pago (Subirats), Barcelona. Single-page bilingual site (Catalan primary, English secondary). Deployed to GitHub Pages.

**URL:** https://terraifoc.cat  
**CNAME:** terraifoc.cat  
**GitHub:** git@github.com:112books/terraifoc.cat.git  
**Default branch:** main

## Tech Stack

- **Framework:** Hugo (extended, latest version)
- **Language:** Go-based templating with i18n
- **CSS:** Custom, single file, no framework
- **Font:** Jost (Google Fonts, preconnected + preloaded)
- **CI/CD:** GitHub Actions (peaceiris/actions-hugo v3 + actions/configure-pages v5)

## Project Structure

```
/
├── archetypes/default.md          # Hugo content archetype
├── assets/css/main.css            # Single stylesheet (minified in build)
├── content/
│   ├── _index.md                  # Homepage frontmatter (CA) — dades_taller timeline data
│   └── en/_index.md               # Homepage frontmatter (EN)
├── data/glossary.yaml             # Bilingual glossary entries (ca/en)
├── hugo.toml                      # Hugo configuration
├── i18n/
│   ├── ca.yaml                    # Catalan translations (all UI strings)
│   └── en.yaml                    # English translations
├── layouts/
│   ├── _default/baseof.html       # Base template (CSP, SEO meta, lightbox, JS)
│   ├── index.html                 # Homepage layout (all sections: hero, joan, familia, taller, collab, glossari, galeria, contacte)
│   └── partials/
│       ├── header.html            # Fixed header with nav + language switcher
│       ├── footer.html            # Footer with logo, address, email
│       └── progress.html          # Reading progress bar + scroll-to-top button
├── static/
│   ├── CNAME                      # terraifoc.cat
│   ├── admin/
│   │   └── index.html             # GoatCounter analytics dashboard (public, no auth)
│   └── img/                       # All images (logos, portraits, workshop, gallery)
├── sync-terraifoc.sh              # Dev/management script (menu-driven)
└── .github/workflows/deploy.yml   # GitHub Actions deploy to Pages
```

## Configuration (hugo.toml)

```toml
baseURL = "https://terraifoc.cat/"
title = "Terra i Foc"
defaultContentLanguage = "ca"
disableKinds = ["taxonomy", "term", "RSS"]
enableRobotsTXT = true

[params]
  description = "Obrador de ceràmica artesanal"
  author = "Terra i Foc"
  email = "hola@terraifoc.cat"
  address = "Carrer de la Verge de Montserrat, 17, El Pago (Subirats), Barcelona"
  instagram = "https://www.instagram.com/terraifoc/"
  logo = "/img/terraifoc-logo.svg"

[languages]
  [languages.ca]
    languageName = "Català"
    contentDir = "content"
    weight = 1
  [languages.en]
    languageName = "English"
    contentDir = "content/en"
    weight = 2

[markup.goldmark.renderer]
  unsafe = true
```

## Key Implementation Details

### Password Gate
- Inline script in `baseof.html` (line 36)
- Password: `LinuxBCN2026`
- Stored in `sessionStorage` key `tf_pass`
- On failure: overwrites body with "Lloc web en construcció" message
- This is NOT a security measure, only a soft gate

### Security (CSP)
```
default-src 'self'
style-src 'self' fonts.googleapis.com 'unsafe-inline'
font-src fonts.gstatic.com
script-src 'self' 'unsafe-inline'
img-src 'self' data:
connect-src 'self'
frame-ancestors 'none'
base-uri 'self'
```

### SEO / Meta
- Canonical URLs per page
- hreflang alternates (ca, en, x-default)
- Open Graph (og:title, og:description, og:url, og:type, og:locale, og:site_name)
- Twitter Card (summary_large_image)
- theme-color: `#361712`
- SVG favicon + apple-touch-icon
- robots.txt enabled

### Contact Form
- Formspree endpoint: `https://formspree.io/f/xqeoyjjr`
- AJAX submit via fetch (no page reload)
- Honeypot field (`_gotcha`, display:none)
- Status messages via i18n (form_ok, form_error)

### CSS Architecture
- **Custom properties** in `:root` for entire design system
- **Palette:** Earth tones (`--terra: #361712`, `--foc: #c81111`, `--cendra: #8a7a6e`)
- **Font:** Jost throughout (weights 300, 350, 400, 500, 600)
- **Responsive breakpoints:** 1024px, 768px, 480px
- **Animations:** IntersectionObserver scroll-reveal (`.section-reveal`), respects `prefers-reduced-motion`
- **Layout:** CSS Grid for galleries/columns, max-width `1024px` content container

### Navigation
- Single-page anchor navigation (#joan, #familia, #taller, #collaboracions, #glossari, #galeria, #contacte)
- Header shrinks on scroll (`.header-scrolled` at >80px)
- Underline hover effect on nav links
- Language switcher toggles between / and /en/

### Gallery & Lightbox
- Gallery grid with 3 columns, 2px gap
- Hover zoom effect (scale 1.04)
- Lightbox: click image → fullscreen overlay, close via button/click-outside/Escape
- Image aspect-ratio: 1 (square) with object-fit: cover

### Reading Progress
- Top bar (2px, --foc color) that fills as user scrolls
- Scroll-to-top floating button (appears after 300px scroll)

## Content Management

### Adding/Modifying Content
- **Page text:** Edit `i18n/ca.yaml` and `i18n/en.yaml`
- **Timeline data:** Edit `content/_index.md` and `content/en/_index.md` frontmatter `dades_taller` array
- **Glossary entries:** Edit `data/glossary.yaml` (ca → entries → array; en → entries → array)
- **Images:** Place in `static/img/` subdirectories, reference with `/img/...` paths

### Adding New Sections
1. Add translation keys to both `i18n/ca.yaml` and `i18n/en.yaml`
2. Add section HTML to `layouts/index.html`
3. Add nav link in `layouts/partials/header.html`
4. Add any new CSS to `assets/css/main.css`

## Development Commands

```bash
# Local dev server with drafts
./sync-terraifoc.sh  # option 3, or:
hugo server -D

# Build locally with minification
./sync-terraifoc.sh  # option 4, or:
hugo --minify --buildDrafts

# Full sync (commit + pull rebase + push)
./sync-terraifoc.sh  # option 2

# Deploy to production (pushes main → triggers GitHub Action)
./sync-terraifoc.sh  # option 5
```

## Deployment

GitHub Actions workflow in `.github/workflows/deploy.yml`:
1. Trigger: push to `main` or manual dispatch
2. Build: `peaceiris/actions-hugo@v3` with `hugo --minify`
3. Upload: `actions/upload-pages-artifact@v3` (path: `./public`)
4. Deploy: `actions/deploy-pages@v4`

Output is deployed to GitHub Pages at `https://terraifoc.cat/` via the CNAME record.

## Naming Conventions

- **Files:** kebab-case (e.g., `sync-terraifoc.sh`, `baseof.html`, `main.css`)
- **Translation keys:** snake_case (e.g., `hero_tagline`, `section_joan_title`)
- **CSS classes:** kebab-case with BEM-lite (e.g., `section-title`, `section-title--large`, `gallery-item--wide`)
- **CSS custom properties:** `--kebab-case`
- **Git commits:** Catalan or English, imperative mood

## Git Workflow

- **Branch:** main (single branch, no develop branch)
- **Commit style:** descriptive present tense ("Afegeix galeria d'imatges")
- **Sync process:** `git add -A` → commit → `pull --rebase` → push
- **Deploy:** push to main → GitHub Actions auto-deploys

## Design System

| Token | Value | Usage |
|---|---|---|
| `--bg` | `#f5f0eb` | Page background |
| `--bg-alt` | `#ebe3db` | Alt section background |
| `--bg-card` | `#ffffff` | Form inputs, card surfaces |
| `--text` | `#361712` | Body text |
| `--text-dim` | `rgba(54,23,18,0.55)` | Secondary text |
| `--terra` | `#361712` | Brand dark (earth) |
| `--foc` | `#c81111` | Brand accent (fire) |
| `--cendra` | `#8a7a6e` | Muted / ash |
| `--content` | `1024px` | Max content width |
| `--content-narrow` | `680px` | Narrow content width |
| Font | Jost | All text (weights 300-600) |
| Body size | 17px | Base font size |
| Body weight | 350 | Base font weight |

## GoatCounter Analytics

- **Account:** `terraifoc-cat` (https://terraifoc-cat.goatcounter.com)
- **Tracking script:** In `baseof.html` `<head>`, loads from `gc.zgo.at`
- **Dashboard:** `static/admin/index.html` — public, no password
  - Fetches `analytics.json` from the same directory
  - Chart.js for temporal charts, Canvas 2D for visualizations
  - Earth-tone palette matching main site (`--foc: #c81111`)
  - Catalan UI, tabs: Temporal / Pàgines / Dispositius
  - Sections mapped: Joan, Família, Taller, Col·laboracions, Glossari, Crèdits, Galeria, Contacte
- **CSP:** `script-src` includes `gc.zgo.at`, `connect-src` includes `terraifoc-cat.goatcounter.com`
- **TODO:** Create GitHub Actions workflow to fetch `analytics.json` from GC API (requires `GC_API_KEY` secret)

## Contact

- **Email:** hola@terraifoc.cat
- **Instagram:** https://www.instagram.com/terraifoc/
- **Address:** Carrer de la Verge de Montserrat, 17, El Pago (Subirats), Barcelona

---

**Important:** Always run `hugo --minify` before committing to verify no build errors. The site is bilingual — any new text must be added to both `ca.yaml` and `en.yaml`. The admin stats page (`/admin`) is public and has no password protection.
