# 9MM Pro — Branding Pack

Canonical brand assets for all 9MM Pro frontends. Read **[DESIGN.md](DESIGN.md)**
for the full brand guide (logo rules, color system, typography, design language),
or open **[index.html](index.html)** in a browser for a visual showcase — logo
variants, live color swatches (click to copy hex), type specimens, and component
demos, with a dark/light mode toggle. It renders from the pack's own tokens and
fonts, so it doubles as a smoke test that the pack works.

## Contents

```
ui/
  9mm.css       canonical Tailwind v4 UI layer — tokens + @theme + base styles +
                shared component classes (.bracket-card, .btn-terminal, .grid-bg,
                .scanline, .stagger, …). Import this; never copy rules locally.
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

Reference this repo from your project (git submodule recommended, or a pinned
vendored copy — see DESIGN.md §7), then:

1. **Tailwind v4 sites:** `@import "<path>/ui/9mm.css";` and
   `@import "<path>/fonts/fonts.css";` after `tailwindcss` — that's the whole brand:
   tokens, utilities, and the shared component classes. Delete local copies of
   `.bracket-card` / `.btn-terminal` / etc. from your globals.css.
2. **Non-Tailwind pages:** the same two imports work (browsers skip the `@theme`
   block), or use just `tokens/colors.css` + `fonts/fonts.css` for tokens only.
3. **Favicons:** copy the image files + `site.webmanifest` from `favicon/` into
   `public/`, paste `favicon/snippet.html` into `<head>`.
4. **Logo:** use the SVGs in `logo/svg/` — white on dark, black on light.
5. **Icons:** lucide-react only — sizes and conventions in DESIGN.md §5.

## Notes

- The SVG logos were auto-traced from the original 559×559 PNG (no vector master
  existed). Trace verified faithful; if a hand-drawn vector ever surfaces, replace
  these masters.
- Canonical dark-mode brass is `#c8a84e`. The landing page's `#d7b249` is legacy
  drift — see DESIGN.md §3.
- Fonts are Google Fonts builds repackaged from Fontsource (SIL OFL — license
  files included alongside the woff2s).
