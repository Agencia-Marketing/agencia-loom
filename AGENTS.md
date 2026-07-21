# AGENTS — Plantilla 2 | Neo-Brutalist Agency

## Project Overview

Neo-brutalist landing page template for a digital marketing agency. Built with Astro + Tailwind CSS, deployable to Cloudflare Pages. Includes standalone HTML version for quick delivery. Visual counterpart to Plantilla 1 — same content, radically different aesthetic.

## Critical Conventions

- **Two variants coexist**: `src/` (Astro with local Tailwind + PostCSS) and `html/` (standalone HTML with Tailwind CDN + inline CSS). Keep both in sync when making visual/style changes.
- **All brand colors**: defined as CSS custom properties in `:root` in `src/styles/global.css` and each HTML file's `<style>` block.
- **Tailwind is v3**, not v4. Use `@tailwind base/components/utilities` directives.
- **Zero border-radius everywhere** — this is a design constraint, not a bug.

## Commands

| Command | Action |
|---|---|
| `npm run dev` | Start local dev server at `localhost:4321` |
| `npm run build` | Build to `dist/` |
| `npm run preview` | Preview build locally |

## Design System

### Colors — `:root`
- `--color-bg: #0A0A0A` — near-black background
- `--color-surface: #111111` — card/section surface
- `--color-surface-raised: #191919` — elevated surface
- `--color-border: #2A2A2A` — subtle border
- `--color-border-strong: #3D3D3D` — visible border
- `--color-accent: #AAFF00` — neon lime (primary accent)
- `--color-accent-dark: #88CC00` — accent hover
- `--color-accent-dim: #1A2600` — accent bg tint
- `--color-accent-on: #0A0A0A` — text on accent
- `--color-secondary: #FF3C00` — neon orange-red
- `--color-text: #F0F0F0` — main text
- `--color-text-muted: #888888` — secondary text
- `--color-footer-border: #AAFF00` — footer top border

### Typography
- **Display/Headings**: Barlow Condensed (900/800/700 weight, UPPERCASE)
- **Labels/Tags/Nav**: JetBrains Mono (700 weight, UPPERCASE, tracking-widest)
- **Body**: Barlow (400/500 weight)

### Design Rules
- `border-radius: 0` everywhere — no exceptions
- Hard offset shadows: `box-shadow: 4px 4px 0 var(--color-accent)` — no blur
- Borders: minimum 2px, visible and structural
- Images: `filter: contrast(1.05) saturate(0.85)` by default

### Rebranding flow
Change colors in TWO places:
1. `:root` block in `src/styles/global.css` (and each HTML file's `<style>`)
2. `theme.extend.colors` in `tailwind.config.mjs` (and inline config in HTMLs)

## Key CSS Classes

| Class | What it does |
|---|---|
| `.brut-btn` | Button: 2px accent border, hard shadow, hover: fills with accent |
| `.brut-btn-dark` | Button variant for accent-bg sections |
| `.brut-btn-filled` | Filled accent button |
| `.brut-btn-secondary` | Orange-red variant |
| `.brut-card` | Card: 2px border, 4px hard shadow, hover: border+shadow turn accent |
| `.brut-tag` | Inline tag: filled accent, JetBrains Mono uppercase |
| `.brut-section-label` | Small monospace section prefix in accent color |
| `.brut-reveal` | Fade-up on scroll via `.visible` class (IntersectionObserver) |
| `.brut-grid-bg` | Subtle grid pattern background |
| `.brut-accent-border-*` | 4px thick accent borders (top/left/bottom) |

## Deployment

Push to `main` on GitHub → Cloudflare Pages auto-builds.
