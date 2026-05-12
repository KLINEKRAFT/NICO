# 11147 S Quebec Avenue — Property Site

A single-page cinematic real estate site for the English manor estate at 11147 South Quebec Avenue, Tulsa, Oklahoma. Listed by Janelle Nicolay & Stuart Gallagher (NICO Group · Coldwell Banker Select).

## Structure

```
/
├── index.html                  ← the site (everything inlined except images, fonts + libs)
├── fonts/
│   ├── Bauziet-Light.otf       ← CB primary display font (per 2025 standards)
│   ├── Bauziet-Italic.otf
│   ├── Bauziet-Medium.otf
│   └── Bauziet-Bold.otf
├── images/
│   ├── property/               ← 70 listing photos (1920px JPEGs, ~28MB)
│   └── floorplans/             ← 3 floor plans
└── vendor/
    ├── gsap.min.js             ← GSAP 3.12.5
    ├── ScrollTrigger.min.js    ← GSAP ScrollTrigger plugin
    └── lenis.min.js            ← Lenis smooth-scroll 1.0.42
```

No build step. Drop these four directories into any static host.

## Deploy via GitHub web UI → Vercel/Cloudflare Pages

1. Create a new repository in the KLINEKRAFT org (e.g. `quebec-estate`).
2. Upload all four items above to the repo root via the GitHub web UI.
3. In Vercel or Cloudflare Pages: New project → Import repository → defaults are fine (no framework, no build command, output directory is repo root).
4. Optional: point `quebec.colinkline.com` (or similar) at the deployment in your Cloudflare DNS.

## Editing

- **Copy**: All listing copy lives directly in `index.html` — search for the phrase you want to change.
- **Photos**: Replace files in `images/property/`. Keep the same filenames or update the `src` / `background-image` references in `index.html`.
- **Floor plans**: `images/floorplans/floor-1.jpg`, `floor-2.jpg`, `floor-basement.jpg`.
- **Agent contact**: Search for `Janelle Nicolay` in `index.html` to find the contact block.

## Design system

Aligned with the Coldwell Banker® 2024–2025 Brand Identity Standards.

- Type: **Bauziet** (display, served locally from `/fonts`) · **Roboto** (body) · **Roboto Mono** (labels and data)
- Palette: CB Midnight `#0A1730` ground, near-white `#F4F7FB` type, CB Celestial `#418FDE` accent for italic emphasis. Footer in CB Blue `#012169`. No gold or bronze anywhere on the site.
- The CB Monogram (white North Star + "CB" silhouette) appears in the nav and footer locked up with "Coldwell Banker® Select · NICO Group". The Monogram form is used because it sits on dark / CB Blue surfaces — per the 2025 standards.
- Motion: GSAP + ScrollTrigger reveals, Lenis smooth-scroll, pinned image expansion on the architecture section, parallax on every full-bleed media block
- Footer carries the full Coldwell Banker / Anywhere Advisors disclaimer (printed-materials wording from the 2025 standards), Equal Housing Opportunity, REALTOR® lockup, and the KLINEKRAFT wordmark
- Fully responsive: breakpoints at 980px (single-column duos), 860px (compact nav), 780px (stacked grids), 560px and 420px (mobile micro-adjustments). Custom cursor is disabled on touch devices.

## Browser support

Modern evergreen browsers (Chrome, Safari, Firefox, Edge). The site degrades gracefully if JavaScript fails — a safety reveal in the IIFE ensures all content remains readable even if GSAP or Lenis fail to load.
