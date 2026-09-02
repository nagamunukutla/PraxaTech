# Uploading to InfinityFree

Upload **every file in this folder** into `htdocs/`, keeping them all at the same level.
No subfolders — `index.html` refers to the images by bare filename.

```
htdocs/
  index.html
  hero-chart.svg
  mark-trans.svg
  favicon.svg
  favicon-32.png
  apple-touch-icon-180.png
  og-image-1200x630.png
```

If `htdocs/` already contains a default `index2.html` or a placeholder page, delete it.

## Checks after upload

- Chart appears between the headline and the legend. If it doesn't, the SVG didn't upload or landed in a subfolder.
- Favicon shows in the browser tab (hard-refresh; favicons cache aggressively).
- Page is readable on a phone.

## If the SVG will not display

Some free hosts don't serve `image/svg+xml` correctly. Swap in the PNG:

```html
<img src="hero-chart-1400.png" alt="...">
```

Copy `hero-chart-1400.png` from the brand folder alongside the rest.

## What changed from the GitHub version

The chart is now an external file rather than inline SVG, so page builders and import
tools can't strip it. The load animation is gone — a fair trade for a hero that
survives being moved around.
