# HANGOVR 180 — Brand Site

**Live URL:** Deployed on Vercel  
**Version:** 4.1  
**Last updated:** April 14, 2026!

## Overview

Static marketing site for HANGOVR 180, a pre-alcohol supplement brand based in Austin, TX.

## Tech Stack

- Static HTML/CSS (no framework, no build tools)
- Font: Montserrat (Google Fonts)
- Hosting: Vercel (auto-deploys from this repo)
- Images: WebP with `<picture>` art direction (portrait/landscape/desktop)

## Structure

```
/
├── index.html          Home
├── doa180.html         Do A 180
├── whos-in.html        Tomorrow People
├── inside.html         What's Inside
├── find-us.html        Find Us
├── stock-up.html       Stock Up
├── global.css          Shared styles (nav, buttons, footer, resets)
└── images/             All site images (44 WebP + 2 SVG)
```

## Brand Colors

| Name   | Hex       |
|--------|-----------|
| Yellow | `#FFD800` |
| Black  | `#303633` |
| Red    | `#C7084F` |
| White  | `#FFFFFF` |

## Deployment

Push to main branch. Vercel auto-deploys.

## Image System

Images use `<picture>` elements with up to 3 variants per image:

- **Category 1 (heroes):** 3 versions — desktop, mobile-portrait, mobile-landscape
- **Category 2 (mid-size):** 2 versions — desktop, mobile
- **Category 3 (small/square):** 1 version — single WebP

Breakpoints: portrait `(max-width:767px)`, landscape `(max-width:1023px) and (orientation:landscape)`, desktop fallback.

## v4.1 Changes (Landscape + Image Optimization)

### From v1.2 spec:
- **Nav breakpoint → 1024px:** Hamburger stays active on all phones including landscape
- **Landscape hero fixes:** `min-height:50vh`, scaled headlines via `clamp(2rem,6vw,3.5rem)`, page-specific `object-position` shifts
- **whos-in.html landscape:** Hero text constrained to left 50% so runner's face stays visible
- **doa180.html landscape:** Image shifts right (`object-position:70% center`) to keep product visible
- **index.html landscape:** Image shifts up (`object-position:center 30%`) to keep faces visible
- **All images → WebP** via `<picture>` with art-directed crops
- **Logos → SVG** for crispness at any size
- **`loading="lazy"`** on all below-fold images

### Carried from v4.0:
- Shared `global.css` for cross-page caching
- SVG hamburger icon (no Material Symbols dependency except whos-in.html rocket)
- Trimmed font weights (6 instead of 11)
- Footer mobile refinements
- Reviews carousel peek + dot pagination
- Portrait consistent ordering + 2-col at 480px
- Location badge stacking
- Cart button 48px touch targets
- Email form gap on mobile

## Notes

- Material Symbols font loaded only on whos-in.html (rocket icon)
- Email signup forms are placeholder only
- Cart buttons point to stock-up.html (Shopify integration pending)
- Images folder ships empty in this zip — client adds WebP/SVG files manually
