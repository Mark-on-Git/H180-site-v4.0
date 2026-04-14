# HANGOVR 180 — Brand Site

**Live URL:** Deployed on Vercel  
**Version:** 4.0  
**Last updated:** April 13, 2026

## Overview

Static marketing site for HANGOVR 180, a pre-alcohol supplement brand based in Austin, TX.

## Tech Stack

- Static HTML/CSS (no framework, no build tools)
- Font: Montserrat (Google Fonts)
- Hosting: Vercel (auto-deploys from this repo)

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
└── images/             All site images (24 files)
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

## v4.0 Changes (Mobile Optimization)

- **Shared CSS:** Extracted ~180 lines of duplicated nav/button/footer CSS into `global.css` for cross-page caching
- **Hamburger icon fix:** Replaced Material Symbols font icon with inline SVG on all 6 pages — icon now renders correctly everywhere
- **Font weight trim:** Reduced Google Fonts payload from 11 weights to 6 (~40% reduction)
- **Footer mobile refinements:** Reduced padding, bumped link font size for readability
- **Home:** Hero subtext split into two lines for mobile, pack image uses aspect-ratio instead of fixed height, email form gap added
- **Do A 180:** Review cards peek at 85% width on mobile (hints at more content), added dot pagination indicators
- **Tomorrow People:** Portrait cards use consistent image-first order on mobile, 2-column grid at 480px to reduce scroll
- **Find Us:** Location badges stack below address on mobile instead of being pushed off-screen
- **Stock Up:** Cart buttons have explicit 48px min-height for touch target compliance

## Notes

- Each HTML page links to `global.css` for shared styles and contains page-specific CSS inline
- Only JavaScript on the site is the mobile menu toggle and the reviews carousel on doa180.html
- Email signup forms are placeholder only (`onsubmit="event.preventDefault();"`)
- Cart link points to stock-up.html (headless Shopify integration pending)
- Material Symbols font is only loaded on whos-in.html (for rocket icon in bento section)
