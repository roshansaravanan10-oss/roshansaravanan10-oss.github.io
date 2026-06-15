# FwdDeploy — Landing Site

The complete front-end source for the **FwdDeploy** marketing website
("The Only Tech Team You Need to Move Forward") — a forward-deployed engineering
firm based in Bengaluru.

This is a **self-contained static site**: every page is plain HTML with its CSS inlined
and all fonts served locally, plus a layer of hand-written vanilla-JS interactions
(scroll reveals, an interactive blueprint cursor grid, animated process cards, count-ups,
magnetic CTAs). No build step, no framework runtime, no backend — open it and it runs.

## Structure

```
.
├── index.html                 # Home
├── about/index.html           # About
├── playbook/index.html        # Playbook (the full method)
├── start/index.html           # Start a project (intake)
├── work/
│   ├── dental-os/index.html        # Case 01 — Dental OS
│   └── machine-monitor/index.html  # Case 02 — Machine Monitor
├── privacy-policy/index.html  # Legal
├── data-deletion/index.html   # Legal
├── terms/index.html           # Legal
├── _next/static/              # Shared CSS chunk + woff2 fonts (Fraunces / Archivo / IBM Plex Mono)
├── icon.svg
└── manifest.webmanifest
```

Each route is a folder with an `index.html` so clean URLs (`/about`, `/work/dental-os`)
resolve on any static host.

## Run locally

```sh
# from the repo root
python3 -m http.server 8910
# then open http://127.0.0.1:8910
```

Any static file server works (`npx serve`, `caddy file-server`, etc.).

### Share a temporary public URL (optional)

```sh
ngrok http 8910
```

## Deploy

Drop the whole folder on any static host — **Vercel, Netlify, Cloudflare Pages, or GitHub Pages**.
No configuration required; the site root is `index.html`.

## Interactions (homepage)

- Cursor-reactive blueprint dot-grid (revealed in a halo that follows the pointer)
- Scroll-progress bar + smooth scroll-reveals (fade + rise, Expo easing)
- "How we work" process cards with oversized ghost numerals + hover lift
- Count-up numbers on the deployment log (Day 7 / Week 3 / Week 8)
- 3D tilt on the deployment-log panel + magnetic primary CTAs

All motion respects `prefers-reduced-motion` and is disabled on small screens.

## Notes

- Brand palette: ink `#11271c`, primary green `#0b7a3f`, signal gold `#b8770c`, paper/mint surfaces.
- Type: Fraunces (display serif), Archivo (sans), IBM Plex Mono (labels).
