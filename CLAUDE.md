# CLAUDE.md

## Project Overview

Static HTML/CSS website for **Kollyva Theologou** (ΚΟΛΛΥΒΑ ΘΕΟΛΟΓΟΥ), a bakery/confectionery in Kalamata, Greece specializing in traditional kollyva — a ceremonial sweet served in Orthodox Christian memorial services.

- **Domain**: kollyvatheologou.gr
- **Hosting**: GitHub Pages with custom domain (configured via `CNAME` file)
- **Language**: Content is in Modern Greek

## Repository Structure

```
/
├── index.html          # Entire website (single-page, ~380 lines)
├── CNAME               # GitHub Pages custom domain config
├── README.md           # Basic project info
├── CLAUDE.md           # This file
├── hero.jpg            # Hero section background image
├── *.jpg / *.png       # Product images (~20 files, ~10 MB total)
```

All files live at the repository root — there are no subdirectories for source code, assets, or configuration.

## Tech Stack

- **HTML5** with semantic elements (`<header>`, `<nav>`, `<section>`, `<footer>`)
- **CSS3** embedded in `<style>` within `index.html` (no external stylesheet)
- **Google Fonts** (CDN): Cormorant Garamond (headings), Montserrat (body)
- **Google Maps** embedded iframe for the contact section
- **No build system**, package manager, bundler, or JavaScript framework
- **No testing, linting, or CI/CD** infrastructure

## Architecture & Conventions

### Single-Page Layout

`index.html` contains everything — markup, styles, and content. The page is structured as:

1. **Header** — Sticky nav with anchor links (`#symbolism`, `#products`, `#contact`)
2. **Hero** — Full-width background image with dark overlay and CTA
3. **Symbolism** — 3×3 grid explaining the 9 symbolic kollyva ingredients
4. **Products** — Auto-fill CSS Grid of product cards with images
5. **Contact** — Two-column layout with business info + embedded map
6. **Footer** — Business name, address, GEMI registration number

### CSS

- **CSS Custom Properties** for theming: `--bg-color`, `--text-color`, `--accent-color`, `--font-main`, `--font-serif`
- **Responsive**: Single breakpoint at `768px` for mobile
- **Layout**: CSS Grid for product cards and symbolism items; Flexbox for header/nav
- **Transitions**: `0.3s` on interactive elements (buttons, cards)

### Images

All images are at the root level with descriptive Greek names (e.g., `amigdalo.jpg`, `stafida.jpg`, `tsureki.jpg`). Product images range from ~100 KB to ~800 KB. The hero image is ~1.8 MB.

## Development Workflow

1. Edit `index.html` directly — all markup and styles live there
2. Open in a browser to preview (no build step required)
3. Commit and push to deploy via GitHub Pages

There is no build, test, or lint step. The site is production-ready as static files.

## Deployment

The site is deployed via **GitHub Pages**. The `CNAME` file maps the custom domain `kollyvatheologou.gr`. Pushing to the main branch triggers deployment automatically.

## Key Guidelines for AI Assistants

- **Do not introduce a build system** unless explicitly requested — the simplicity is intentional
- **All CSS is inline** in `index.html`; do not extract it to a separate file without being asked
- **Content is in Greek** — preserve correct Greek text, accents, and encoding (UTF-8)
- **Images are at root level** — follow the existing flat structure for new assets
- **Keep the single-file architecture** — avoid splitting into multiple HTML pages unless requested
- **Preserve the CSS custom properties** pattern when adding new styles
- **Responsive design**: test changes against the 768px breakpoint
- **No JavaScript** currently exists on the site — avoid adding JS unless the feature requires it
