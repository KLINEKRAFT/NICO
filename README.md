# 11147 S Quebec Avenue — Property Site

A single-page cinematic real estate site for the English manor estate at 11147 South Quebec Avenue, Tulsa, Oklahoma. Listed by Janelle Nicolay & Stuart Gallagher (NICO Group · Coldwell Banker Select).

## Structure

```
/
├── index.html                              ← the site (everything inlined except assets + libs)
├── assets/
│   ├── fonts/                              ← Bauziet OTF family (CB primary display font)
│   │   ├── Bauziet-Light.otf
│   │   ├── Bauziet-Italic.otf
│   │   ├── Bauziet-Medium.otf
│   │   └── Bauziet-Bold.otf
│   ├── logo/
│   │   └── Logo_133009_Select_HZ_W_MO.png  ← Official Coldwell Banker Select horizontal lockup (white, monogram)
│   └── images/
│       ├── property/                       ← 70 listing photos (1920px JPEGs, ~28MB)
│       └── floorplans/                     ← 3 floor plans
└── vendor/
    ├── gsap.min.js                         ← GSAP 3.12.5
    ├── ScrollTrigger.min.js                ← GSAP ScrollTrigger plugin
    └── lenis.min.js                        ← Lenis smooth-scroll 1.0.42
```

No build step. Drop `index.html`, `assets/`, and `vendor/` into any static host.

## Deploy via GitHub web UI → Vercel/Cloudflare Pages

1. Create a new repository in the KLINEKRAFT org (e.g. `quebec-estate`).
2. Upload all four items above to the repo root via the GitHub web UI.
3. In Vercel or Cloudflare Pages: New project → Import repository → defaults are fine (no framework, no build command, output directory is repo root).
4. Optional: point `quebec.colinkline.com` (or similar) at the deployment in your Cloudflare DNS.

## Editing

- **Copy**: All listing copy lives directly in `index.html` — search for the phrase you want to change.
- **Photos**: Replace files in `assets/images/property/`. Keep the same filenames or update the `src` / `background-image` references in `index.html`.
- **Floor plans**: `assets/images/floorplans/floor-1.jpg`, `floor-2.jpg`, `floor-basement.jpg`.
- **Brokerage logo**: `assets/logo/Logo_133009_Select_HZ_W_MO.png` — referenced from the nav, the contact section, and the footer. Drop in a replacement at the same path/filename to swap.
- **Agent contact**: Search for `Janelle Nicolay` in `index.html` to find the contact block.

## Design system

Aligned with the Coldwell Banker® 2024–2025 Brand Identity Standards.

- Type: **Bauziet** (display, served locally from `assets/fonts`) · **Roboto** (body) · **Roboto Mono** (labels and data)
- Palette: CB Midnight `#0A1730` ground, near-white `#F4F7FB` type, CB Celestial `#418FDE` accent for italic emphasis. Footer in CB Blue `#012169`. No gold or bronze anywhere on the site.
- The official **Coldwell Banker Select horizontal lockup** (white, monogram) appears in three places: top-left of the nav, at the bottom of the agent contact block, and at the top of the CB Blue footer band.
- Hero is editorial: title anchored bottom-left, address and offer price bottom-right, a hairline rule across the bottom edge — no animated scroll cue.
- Motion: GSAP + ScrollTrigger reveals on `expo.out`, Lenis smooth-scroll, pinned image expansion on the architecture section, parallax on every full-bleed media block. The custom cursor was removed by request.
- Figure captions are editorial — short mono labels with a Celestial-blue accent rule, sitting on a subtle bottom gradient instead of a chip background.
- Footer carries the full Coldwell Banker / Anywhere Advisors disclaimer (printed-materials wording from the 2025 standards), Equal Housing Opportunity, REALTOR® lockup, and the KLINEKRAFT wordmark.
- Fully responsive. Hero meta stacks under the title at ≤900px (covers tablets). Nav collapses at ≤860px and drops the Plans link at ≤420px.

## Browser support

Modern evergreen browsers (Chrome, Safari, Firefox, Edge). The site degrades gracefully if JavaScript fails — a safety reveal in the IIFE ensures all content remains readable even if GSAP or Lenis fail to load.
