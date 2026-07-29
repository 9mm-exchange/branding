<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="logo/svg/9mm-mark-white.svg">
  <img src="logo/svg/9mm-mark-black.svg" alt="9MM Pro" width="120">
</picture>

# 9MM<span>.</span>PRO — Branding Pack

**The canonical reference for the 9MM Pro brand and UI.**
Tokens, component recipes, fonts, logos, favicons, and product-surface guidance —
one maintained reference for documenting and comparing the 9MM Pro ecosystem.

[![version](https://img.shields.io/badge/pack-v1.3.0-c8a84e?style=flat-square&labelColor=08060b)](CHANGELOG.md)
[![design guide](https://img.shields.io/badge/guide-DESIGN.md-c8a84e?style=flat-square&labelColor=08060b)](DESIGN.md)
[![live reference](https://img.shields.io/badge/live_reference-index.html-c8a84e?style=flat-square&labelColor=08060b)](index.html)

*Decentralized. Efficient. Yours.*

</div>

---

This repo is a **reference, not a runtime dependency**. It captures the brand
baseline across the hub, DEX, 9x, Claim, Royal Gate, XCH Terminal, and 9MM Launch.
It does not assert that any product currently imports, mirrors, or is synced to
this pack. No submodules, remote assets, or cross-repository CSS imports are part
of the intended production contract.

| | |
|---|---|
| 📖 **[DESIGN.md](DESIGN.md)** | The brand guide: logo rules, color system, typography, components, layout/motion/z-index/accessibility specs |
| 🧭 **[SURFACES.md](SURFACES.md)** | Product directory: canonical lockups, environment/status semantics, and what belongs in the shared brand layer |
| 🖥️ **[index.html](index.html)** | Live component reference — every shared class rendered with copyable markup, dark/light toggle, click-to-copy color swatches. Just open it in a browser |
| 📋 **[CHANGELOG.md](CHANGELOG.md)** + [VERSION](VERSION) | What changed in the reference since its last release |
| 🤖 **[CLAUDE.md](CLAUDE.md)** | Protocol for AI agents building 9MM Pro frontends |

## Preview

The component reference (`index.html`) — rendered entirely from the pack's own
tokens, fonts, and logos, so if it looks right, the pack works:

| Dark (default) | Light — aged paper (opt-in) |
|---|---|
| ![dark](docs/preview-dark.png) | ![light](docs/preview-light.png) |

## Use the reference

1. Read [DESIGN.md](DESIGN.md) and [SURFACES.md](SURFACES.md) before changing a
   product's visual identity or cross-surface copy.
2. Compare the relevant product implementation with the reference, then make any
   chosen changes directly in that product's repository. Do not import this
   repository's CSS or assets at build time or runtime.
3. Use [CHANGELOG.md](CHANGELOG.md) to understand what changed in the reference.
   Brand updates are manual; this repository does not establish a sync mechanism.

**Favicons** — copy the image files + `site.webmanifest` from
[`favicon/`](favicon/) into `public/`, paste [`favicon/snippet.html`](favicon/snippet.html)
into `<head>`.

**Logo** — use the SVG masters in [`logo/svg/`](logo/svg/): white on dark,
black or brass on light. Never let white-on-transparent artwork sit on a
theme-driven background (DESIGN.md §2).

**Icons** — [lucide-react](https://lucide.dev) only. Sizes and conventions
in DESIGN.md §5.

## Two rules that keep the brand coherent

1. **Never link this pack into a product at runtime.** Carry selected source
   material into the product and keep a recorded source version so reviews are
   deliberate and auditable.
2. **Dark is the default scheme on every site.** Light (aged paper) is an
   explicit, persisted toggle. No pure-white surfaces; white is reserved for
   dark-theme primary text and the white logo mark.

## Version history

[`VERSION`](VERSION) + [`CHANGELOG.md`](CHANGELOG.md) track every design change:

- **MAJOR** — a published reference class/token is renamed or removed, or a
  reference value changes in a way that requires a deliberate local migration
- **MINOR** — new components, classes, tokens, or assets
- **PATCH** — value tweaks, doc fixes, asset regenerations

When starting UI work, read the current guide and the relevant changelog entries,
then compare them with the product's local implementation before deciding what to
change. This repository does not imply that a product has previously adopted a
particular version.

## What's inside

```
ui/9mm.css      reference implementation — tokens, @theme, base styles, component recipes
tokens/         colors.css (CSS custom properties) · tokens.json · tailwind-snippet.css
fonts/          JetBrains Mono (300–800 + italic) · Inter (400–700) · fonts.css · OFL licenses
logo/           svg/ traced masters (white · black · brass) · png/ renders (559 + 1024)
favicon/        .ico, PNGs, theme-aware icon.svg, maskable PWA icon, manifest, head snippet
assets/         chain icons · 9MM + PUSSY 404 token icons · 9x protocol marks · nfts/ OG collection art · provenance notes
social/         og-image.png (1200×630 reference card)
docs/           README preview images
DESIGN.md       the brand guide
SURFACES.md     canonical product directory and status boundaries
index.html      the live component reference
```

## Brand at a glance

| | Dark (home) | Light (aged paper) |
|---|---|---|
| Background | `#08060b` ink | `#e7dfc9` manila |
| Card | `#0d0a12` | `#efe8d4` |
| Brass (accent) | `#c8a84e` | `#6e5a24` |
| Text | `#ffffff` | `#1c1609` |

**Type:** JetBrains Mono carries the brand (display, labels, data) · Inter for body copy.
**Voice:** terminal / tactical HUD — `ALL_CAPS_LABELS`, hairlines over shadows,
brackets over rounded corners, square everything.

## Notes

- The SVG logos were auto-traced from the original 559×559 PNG (no vector master
  existed). Trace verified faithful; replace if a hand-drawn vector surfaces.
- Fonts are Google Fonts builds repackaged from Fontsource — SIL OFL, license
  files included beside the woff2s. Brand artwork is proprietary to 9MM Pro.
