# Pulsewave Landing Page

Single-page download portal for **pulsewavegame.com**.

Auto-detects visitor platform (Mac / Windows / Linux), serves the matching
launcher build straight from GitHub Releases. Mobile and unknown platforms
get pointed at the full release page.

## Deploy

Hosted via **Cloudflare Pages** with `pulsewavegame.com` as a custom domain.

To bump version when a new launcher build ships:

1. Update the version in `index.html`:
   - `BASE` URL constant in the `<script>` block
   - 3 `<a>` tags in `.alts` section

2. Commit + push. Cloudflare Pages auto-deploys on push to `main`.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Why static + GitHub release downloads

- Zero hosting cost (Cloudflare Pages free tier + GitHub Releases CDN)
- No bandwidth on our own VPS — the heavy zips are served by GitHub
- One file to edit when launcher version bumps
