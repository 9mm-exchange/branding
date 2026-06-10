# 9MM Pro — Branding Pack

Canonical brand assets for all 9MM Pro frontends. Read **[DESIGN.md](DESIGN.md)**
for the full brand guide (logo rules, color system, typography, design language),
or open **[index.html](index.html)** in a browser for a visual showcase — logo
variants, live color swatches (click to copy hex), type specimens, and component
demos, with a dark/light mode toggle. It renders from the pack's own tokens and
fonts, so it doubles as a smoke test that the pack works.

## Contents

```
logo/
  svg/          Vector masters — 9mm mark in white / black / brass
  png/          Original 559px raster + recolored 559px and 1024px renders
favicon/
  favicon.ico, favicon-16x16/32x32.png, apple-touch-icon.png,
  android-chrome-192/512.png, site.webmanifest, snippet.html
fonts/
  jetbrains-mono/   woff2, weights 300–800 + 400 italic (OFL license included)
  inter/            woff2, weights 400–700 (OFL license included)
  fonts.css         ready-made @font-face rules + font-stack variables
tokens/
  colors.css            canonical CSS custom properties (light + dark)
  tokens.json           machine-readable design tokens
  tailwind-snippet.css  Tailwind v4 @theme block
social/
  og-image.png          1200×630 Open Graph reference card
assets/
  chains/      chain icons (pulse, base, ethereum, sonic, solana, bsc, chia)
  tokens/      9MM token icons per chain
  protocols/   9x aggregator marks
```

## Quick start

1. **Colors + fonts:** copy or import `tokens/colors.css` and `fonts/fonts.css`
   (plus the `fonts/*/` woff2 folders).
2. **Tailwind v4:** also paste the `@theme` block from `tokens/tailwind-snippet.css`.
3. **Favicons:** copy the image files + `site.webmanifest` from `favicon/` into
   `public/`, paste `favicon/snippet.html` into `<head>`.
4. **Logo:** use the SVGs in `logo/svg/` — white on dark, black on light.

## Notes

- The SVG logos were auto-traced from the original 559×559 PNG (no vector master
  existed). Trace verified faithful; if a hand-drawn vector ever surfaces, replace
  these masters.
- Canonical dark-mode brass is `#c8a84e`. The landing page's `#d7b249` is legacy
  drift — see DESIGN.md §3.
- Fonts are Google Fonts builds repackaged from Fontsource (SIL OFL — license
  files included alongside the woff2s).
