# PEAK Badge Tracker

A zero-build Progressive Web App for tracking PEAK badges. It is plain HTML, CSS, and JavaScript and can be hosted on any static HTTPS host.

## Features

- Checklist for 64 badges, stored locally in the browser with `localStorage`
- Search across names, requirements, tips, biomes, and difficulty
- Filters for completion status, biome, and difficulty; sorting by game order, name, or difficulty
- Expandable tips/details for every badge
- Responsive mobile layout
- Installable PWA manifest and offline cache via service worker
- Badge content kept separately in `badges.json`
- Local placeholder badge artwork, so the project does not redistribute third-party badge images

## Run locally

A service worker and JSON fetch require an HTTP origin. From this directory, run for example:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`. For installation outside localhost, host over HTTPS.

## Hosting

Upload the entire folder unchanged to GitHub Pages, Netlify, Cloudflare Pages, an S3-compatible static host, or any ordinary HTTPS web server. No build step is required.

## Updating badge data

Edit `badges.json`. Each entry contains `id`, `name`, `description`, `tip`, `biome`, `difficulty`, `icon`, and `details`. If you update cached files, increment the cache name in `service-worker.js` (for example `peak-badges-v2`) so installed copies refresh cleanly.

## Data and artwork notes

The included list was assembled for the current 64-badge set visible in public PEAK references around the Final Ascent / 2.0 era and reviewed September 8, 2026. Public references used for verification include the PEAK wiki on wiki.gg and the PEAK Daily Map badge list. Game updates may change wording or requirements; the in-game Accolades screen is authoritative.

The app intentionally uses an original generic SVG placeholder for every badge rather than copying game or wiki artwork. If you have permission to use official/community icons, place them under `assets/icons/` and update each entry's `icon` field. PEAK, its names, and its game assets belong to their respective owners. This project is unofficial and not affiliated with Aggro Crab or Landfall.

The wiki.gg PEAK wiki states its page content is available under CC BY-SA 4.0 unless otherwise noted. If you incorporate wiki text or images beyond the short factual requirements in this project, follow the applicable attribution/share-alike terms and verify each asset's license.

## Files

- `index.html` — app shell
- `styles.css` — responsive visual design
- `app.js` — filtering, rendering, progress persistence, install flow
- `badges.json` — badge dataset
- `manifest.webmanifest` — PWA metadata
- `service-worker.js` — offline cache
- `assets/icon-192.png`, `assets/icon-512.png` — install icons
- `assets/badge-placeholder.svg` — local generic badge placeholder

## License

App code may be reused and modified. Third-party names and game-related factual data remain subject to their respective rights and terms.
