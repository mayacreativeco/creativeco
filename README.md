# Handoff: Maya Creative Co — full site

## Overview
Eight-page marketing site for Maya Creative Co (editor / content producer, Phoenix AZ). Two audiences: creators (Corner → Crash Course → Rough Cut retainer → Edit Suite) and brands (group content days, hotels/travel, assets, brand & web).

## Target
GitHub repo `mayacreativeco/creativeco`, branch `main`. The repo currently holds an OLD site (index.html, about.html, contact.html, intensive*.html, screenshots). Replace it: delete the old files and commit `site/` contents to the repo root. Enable GitHub Pages on main / root.

## About the Design Files
`site/` is a **working static site, no build step** — plain HTML + `support.js` runtime + assets. It runs as-is (open `index.html` or serve the folder). Claude Code's job:
1. Copy `site/*` to the repo root, remove the old site files.
2. Verify all relative paths resolve (`img/`, `uploads/`, `logos/`, `support.js`).
3. Optionally convert to a framework later — not required to launch.

Fidelity: **high-fidelity, final**. Recreate 1:1 if porting.

## Pages (site/)
index · creators · brands · shop · about · work · rough-cut · edit-suite. Nav/footer are identical on every page; "Book a Rough Cut" pill → rough-cut.html.

## Open slots — fill before launch
Search for `[` in the HTML: `[WHOP LINK]`, `[COURSE LINK]`, `[STRIPE / FORM LINK]`, `[CAL.COM / FORM LINK]`, `[BEACONS LINK]`, `[INSTAGRAM]`, `[EMAIL]`, `[VIDEO LINK]`, `[N]` videos/month, `[TURNAROUND]`, `[SEATS]`. Prices on rough-cut / edit-suite are hidden until a value is supplied (`price` prop). Placeholder tiles labelled `[Photo — …]` on brands.html need photos.

## Brand system (binding)
Colors: cream #F5EBD6 ground · paper #FBF6EA cards · dusty pink #E8A5A0 hero · deep forest #2C3A28 trust blocks · black #141414 ink/borders/shadows · tomato #D9471F primary buttons + link hover · lavender #C8C0EE headlines on forest only · hot pink #E75C8C marquee only · butter #F6E3B4 stickers/stripes.
Type (Google Fonts): Reenie Beanie (handwriting, ≥32px except 18–24px pills) · Boldonse uppercase (display: H1 clamp 34–60px, H2 clamp 26–38px, wordmark 15px) · Archivo 400/500/600 (body 16–17px/1.6, H3 600 17px) · Archivo Narrow 700 uppercase +0.12em 14px (buttons, nav, eyebrows).
Components: sticker pill (rounded-full, 2px black, rotated −8°…+6°, wobble on hover) · hard card (paper, 2px black, 20px radius, 6px 6px 0 #141414, lifts 2px) · outlined cutout (6px tomato/black border, 8px hard shadow) · photo-booth strip (black frame 14px padding, 12px gaps, tilted, B&W) · marquee (hot pink, ✶ separators, 45s loop) · stripe band 72px (butter/cream 18px) · buttons rounded-full 12px 22px.
Rules: no soft shadows; tomato text never on pink; lavender only on forest; ≤3 brand colors per section.

## Interactions
- Home hero booth strip: 4 frames cycle one at a time every 1.8s with a flash keyframe (selfie pool only).
- All videos autoplay muted, loop, playsInline. Exception: Edit Suite video on creators.html has a "tap for sound" toggle (starts muted).
- Shop / Work: sticker-pill filters (state in the page's logic class).
- Edit Suite form: client-side only; shows a confirmation line on submit. Wire to a real endpoint.
- Hover: pills rotate −2°, cards translateY(−2px), primary buttons go black.

## Assets
`img/` resized photos (booth selfies, group content, Frenchie / Onera / Flagstaff hotel stills). `uploads/` only the videos referenced by pages (bts1–3, web*, creat*, collstudio, editingsuite). `logos/` profile marks (pink, forest, monogram, 1024²) + favicons (co. 512/64, M 32) — favicon links already in each `<head>`.

## Source of truth
The editable design files remain in the Claude Design project as `*.dc.html`; `site/*.html` are their exported equivalents with cross-links renamed (`Home.dc.html` → `index.html`, etc.).
