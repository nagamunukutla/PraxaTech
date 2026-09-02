# praxatech.github.io

Holding site for PraxaTech. One static file, no build step, no dependencies.

## Deploy

Create the GitHub **organisation** `praxatech` first, not a personal repo. Company assets should not hang off a personal account — moving them later is avoidable annoyance.

```bash
# in the org, create a repo named exactly:  praxatech.github.io
git init
git add index.html README.md
git commit -m "Holding site"
git branch -M main
git remote add origin git@github.com:praxatech/praxatech.github.io.git
git push -u origin main
```

Then **Settings → Pages → Source: Deploy from a branch → main / (root)**.

Live at `https://praxatech.github.io` within a couple of minutes. A repo named `<org>.github.io` serves from the root, so no subpath in the URL.

## Custom domain

Once `praxatech.com` is registered:

1. Add a file named `CNAME` at the repo root containing exactly `praxatech.com` (no protocol, no trailing slash).
2. At the registrar, create four `A` records for the apex pointing at `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, and a `CNAME` for `www` pointing at `praxatech.github.io`.
3. **Settings → Pages → Custom domain**, enter the domain, then tick **Enforce HTTPS** once the certificate provisions (can take up to a day).

Verify the current GitHub Pages IPs in their docs before relying on the list above — they change rarely but they do change.

## Editing

Everything is in `index.html`: styles in a single `<style>` block, chart as inline SVG.

The chart is hardcoded illustrative data — twenty mornings, a 34-minute baseline, delays of 3 to 51 minutes. It is **not** measured data and the page does not claim it is. If that ever changes, label it.

Bar geometry: `x=0` to `204` is baseline, the red rect starts at `204` and runs `delay × 6` pixels. Marker lines sit at `x=243` (median, 40.5 min) and `x=378` (P90, 63 min).
