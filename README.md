# Mobaloom

Unofficial fan gallery hub for Mobile Legends: Bang Bang players. Plain static site: Render serves this folder as it is, with no build step.

Generated from `index.dc.html` by `build/build-deploy.js` and `build/copy-binaries.js` in the design project. Do not hand-edit this folder.

## Pages
- `index.html`: every page as a hash route: `#/` (home), `#/heroes`, `#/gameplay`, `#/tips` (`#/tips/facts`), `#/events`, `#/banner`, `#/settings`
- `404.html`: not-found page (noindex, absolute paths)

## Files
```
├── index.html, 404.html
├── support.js                  page runtime (stays at the root)
├── image-slot.js               image slots (art placeholders)
├── .image-slots.state.json     slot images (empty until real art is added)
├── favicon.ico, site.webmanifest, robots.txt, sitemap.xml
├── render.yaml                 Render hosting and headers
├── .gitignore, README.md
└── assets/
    └── logo/                   favicon.svg, favicon-32.png, apple-touch-icon.png, icon-192/512, maskable
```

## Deploy (Render)
1. Replace the repo contents with this folder (as the repo root), deleting everything that is not in it.
2. Render: New → Blueprint, pick the repo. `render.yaml` sets the publish path `.` and the headers. Later: push, then Manual Deploy → Deploy latest commit.
3. Check the address Render gives. If it is not `https://mobaloom.onrender.com`, set `SITE` in `build/build-deploy.js`, rebuild and push again.

## Caching
- `index.html`, `/`, `404.html`, `sitemap.xml`: `no-cache`.
- `support.js`, `image-slot.js`, `assets/`: cached for a year. Every link carries a content hash (`?v=…`), so a changed file gets a new URL.
- The live build id is in the `mobaloom-build` meta tag.

## Before launch
- Live domain: confirm the Render address (see Deploy step 3).
- Share image: add a 1200×630 `og-image.jpg` (not made yet).
- Official MLBB logos and art come from the owner; MLBB marks belong to Moonton.
