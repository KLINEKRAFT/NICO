# 11147 S Quebec Avenue — Property Site

A single-page cinematic real estate site for the English manor estate at 11147 South Quebec Avenue, Tulsa, Oklahoma. Listed by Janelle Nicolay & Stuart Gallagher (NICO Group · Coldwell Banker Select).

## Structure

```
/
├── index.html                  ← the site (everything inlined except images + libs)
├── images/
│   ├── property/               ← 70 listing photos (1920px JPEGs, ~28MB)
│   └── floorplans/             ← 3 floor plans (cream-on-dark plan diagrams)
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

- Type: **Fraunces** (display, italic for bronze accents) · **Inter Tight** (body) · **IBM Plex Mono** (labels and data)
- Palette: warm near-black `#0c0a08` ground, ivory `#ece4d6` type, single bronze accent `#b08858`
- Motion: GSAP + ScrollTrigger reveals, Lenis smooth-scroll, pinned image expansion on the architecture section, parallax on every full-bleed media block
- Footer carries the Coldwell Banker / Anywhere Advisors disclaimer and the KLINEKRAFT wordmark

## Browser support

Modern evergreen browsers (Chrome, Safari, Firefox, Edge). The site degrades gracefully if JavaScript fails — a safety reveal in the IIFE ensures all content remains readable even if GSAP or Lenis fail to load.
