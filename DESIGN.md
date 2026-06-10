# 9MM Pro — Brand & Design Guide

The canonical reference for all 9MM Pro frontends. Token values in this document
mirror [`tokens/colors.css`](tokens/colors.css) and [`tokens/tokens.json`](tokens/tokens.json) —
those files are the machine source of truth; this document explains how to use them.

---

## 1. Brand overview

| | |
|---|---|
| **Name** | 9MM Pro |
| **Styled** | `9MM.PRO` — all caps, JetBrains Mono, the `.` rendered in brass |
| **Tagline** | Decentralized. Efficient. Yours. |
| **Twitter / X** | [@9mm_pro](https://x.com/9mm_pro) |
| **Telegram** | [t.me/ninemmpro](https://t.me/ninemmpro) |

**Product surfaces**

| Domain | Product |
|---|---|
| `9mm.pro` | Landing + docs |
| `dex.9mm.pro` | V2/V3 DEX |
| `9x.9mm.pro` | 9x aggregator |
| `claim.9mm.pro` | Revenue-share claims |
| `xch.9mm.pro` | XCH Terminal (Chia DEX aggregator) |

**Voice & tone.** Terminal / tactical HUD. Short declarative copy. Section labels
and nav items are ALL-CAPS monospace with underscores replacing spaces:
`CROSS_CHAIN_PRICE_DISCOVERY`, `XCH_TERMINAL`, `BUILT_BY_9MM_PRO`.
Separators (`.`, `/`, `//`) get the brass accent color. Sub-products are namespaced
under the brand: `9MM.PRO / XCH_TERMINAL`.

---

## 2. Logo

One mark exists: a heptagon containing a triangle with **9 / MM** — line art, single color.

| File | Use on |
|---|---|
| `logo/svg/9mm-mark-white.svg` | Dark/ink backgrounds (primary usage) |
| `logo/svg/9mm-mark-black.svg` | Light backgrounds, print |
| `logo/svg/9mm-mark-brass.svg` | Accent usage on dark backgrounds |

SVGs are the masters (auto-traced from the original 559×559 raster — verified faithful).
`logo/png/` holds the original white PNG plus recolored 559px and 1024px renders.

**Rules**

- Prefer the white mark on `ink-950`; never place the white mark on light backgrounds.
- Minimum size: 24px rendered height (the line work closes up below that — at small
  sizes use the favicon assets, which are tuned for 16/32px).
- Clear space: keep at least 25% of the mark's width clear on every side
  (the android-chrome icons in `favicon/` follow this ratio).
- Don't recolor outside white / black / brass, don't add fills, gradients, or strokes.

---

## 3. Color system

Brass on ink. Dark mode is the brand's home; light mode is a warm parchment scheme.
All tokens ship as RGB triples (`--brass-rgb: 200 168 78`) so alpha composition works:
`rgb(var(--brass-rgb) / 0.35)`.

### Brand accent — brass

| Token | Dark | Light | Role |
|---|---|---|---|
| `brass` | `#c8a84e` · `200 168 78` | `#8a7234` · `138 114 52` | Primary accent, CTAs, active states |
| `brass-hot` | `#e8c466` · `232 196 102` | `#a88c40` · `168 140 64` | Hover, highlights, glows |
| `brass-deep` | `#967c38` · `150 124 56` | `#5c4b1e` · `92 75 30` | Borders, muted accent |

> **Canonical dark brass is `#c8a84e`.** The landing page currently uses `#d7b249`
> for its dark primary — treat that as legacy drift; new work should use `#c8a84e`.

### Surfaces — ink scale (darkest token = page background)

| Token | Dark | Light | Role |
|---|---|---|---|
| `ink-950` | `#08060b` | `#faf7ef` | Page background |
| `ink-900` | `#0d0a12` | `#ffffff` | Card |
| `ink-800` | `#1c1822` | `#fbf7e8` | Popover, input |
| `ink-700` | `#141018` | `#f1ebdc` | Secondary |
| `ink-600` | `#24202a` | `#ece4d0` | Muted |

### Foreground hierarchy

| Token | Dark | Light | Role |
|---|---|---|---|
| `fg` | `#ffffff` | `#0e0b08` | Body text |
| `fg-muted` | `#a8a29e` | `#3e362e` | Secondary text |
| `fg-subtle` | `#76706a` | `#645c50` | Captions, metadata |

### Semantic

| Token | Dark | Light | Role |
|---|---|---|---|
| `warn` | `#e8b84a` | `#b5891a` | Warnings |
| `danger` | `#e0574e` | `#b8443d` | Errors, price-down |
| `success` | `#4ade80` | `#16a34a` | Success, price-up |

### Lines & glow

| Token | Dark | Light |
|---|---|---|
| `--hairline` | `rgba(255,255,255,0.08)` | `rgba(138,114,52,0.25)` |
| `--hairline-brass` | `rgba(200,168,78,0.35)` | `rgba(138,114,52,0.55)` |
| `--shadow-brand` | `0 0 40px -10px rgba(200,168,78,0.55)` | `0 0 40px -10px rgba(138,114,52,0.3)` |

Chain-brand colors (e.g. Chia green `#3AAC59`) are reserved for chain chips/badges
only — never as UI accent.

---

## 4. Typography

Two faces, self-hosted in [`fonts/`](fonts/) (see `fonts/fonts.css`):

| Face | Role | Weights |
|---|---|---|
| **JetBrains Mono** | Display, headlines, nav, labels, buttons, data (addresses, figures, terminal output) | 300–800 (+400 italic) |
| **Inter** | Body copy, long-form prose | 400–700 |

```css
--font-mono: 'JetBrains Mono', ui-monospace, SFMono-Regular, Menlo, monospace;
--font-sans: 'Inter', -apple-system, system-ui, sans-serif;
```

**Tracking tokens**

| Token | Value | Use |
|---|---|---|
| `--tracking-label` | `0.2em` | ALL-CAPS labels |
| `--tracking-label-wide` | `0.25em` | Hero eyebrows, section markers |
| `--tracking-tight2` | `-0.03em` | Large display headlines |

**Label convention:** monospace, uppercase, wide tracking, underscores for spaces,
usually `fg-subtle` or brass: `// NON_CUSTODIAL_INTERFACE`.

---

## 5. Design language

The shared component vocabulary. **The implementation is [`ui/9mm.css`](ui/9mm.css)** —
import it; do not copy these rules into a project's globals.css (copy-paste is how the
sites drifted). If a component needs to change, change it in `ui/9mm.css` and every
site picks it up on update.

- **Bracket cards** — cards decorated with 14px brass corner brackets
  (`.bracket-card`), brackets brighten/extend on hover.
- **Hairlines** — 1px borders from `--hairline`; brass hairlines for emphasis.
  Prefer hairlines over shadows for separation.
- **Backgrounds** — page backgrounds are **solid ink** (`bg-ink-950`); line grids were
  retired in the "Refined Terminal" redesign. For section depth, overlay `.grid-bg`
  (soft brass radial glow) or `.grid-bg-fine` (soft sweep) on an absolute
  `pointer-events-none` div.
- **Noise** — SVG noise overlay at ~0.035 opacity for texture on large dark areas.
- **Scanline** — slow vertical sweep (`@keyframes scan`, ~8s, 140px band). Decorative
  only; disable freely.
- **Buttons** — `.btn-terminal`: monospace uppercase label, brass hairline border,
  brass glow on hover. `.btn-ghost`: same shape, neutral hairline, no glow.
- **Motion** — `blink` (1s caret blink), `reveal` (0.7s fade + translate-up, staggered
  via `.stagger`), `marquee` (50s ticker), `flash-up` / `flash-down` (brass / danger
  glow pulse on price change). All motion must respect `prefers-reduced-motion: reduce`
  (`ui/9mm.css` handles this globally).
- **Inputs** — `.field` (hairline container, brass focus ring) wrapping `input.term`
  (transparent, monospace, brass caret).
- **Tooltip** — `.tooltip-container` + `.tooltip-box`: ink background, brass border,
  10.5px monospace.

### Icons

**lucide-react is the only icon library.** Do not mix in heroicons, react-icons,
or inline one-off SVGs for UI glyphs (chain/token marks from `assets/` are the
exception — they're brand artwork, not icons).

| Context | Size | Notes |
|---|---|---|
| Inline with labels / buttons | 14–16px (`h-3.5`/`h-4`) | inherit `currentColor` |
| Standalone controls (theme toggle, close) | 18–20px | |
| Token / chain avatars | 28px | usually an `assets/` image, not a lucide glyph |

Default `strokeWidth` (2) for UI glyphs; 1.5 for dense data visuals. Icons take
their color from the text token of their context (`fg-muted`, `brass`) — never
hardcode hex into an icon.

---

## 6. Favicons & page metadata

Everything needed is in [`favicon/`](favicon/) — copy the image files +
`site.webmanifest` to your `public/` root and paste `favicon/snippet.html`
into `<head>`.

- Theme color: `#08060b` (ink-950 dark).
- Page titles: `Product — descriptor | 9mm Pro` (e.g.
  `XCH Terminal — Chia DEX Aggregator & Cross-Chain Price Discovery | 9mm Pro`).
- OG images are 1200×630: dark ink background, brass corner brackets,
  `9MM.PRO / PRODUCT_NAME` lockup in JetBrains Mono. Static reference:
  `social/og-image.png`; dynamic example: `xch-terminal/src/app/opengraph-image.tsx`.

---

## 7. How to consume this pack

Other projects reference this repo — they don't maintain their own copies of the
brand CSS. Pull it in as a git submodule (recommended — updates are one
`git submodule update --remote` away), or vendor a pinned copy of the folder and
record the commit you took it from:

```bash
git submodule add https://github.com/<org>/branding.git branding
```

**Tailwind v4 projects (the standard path)** — import one file:

```css
/* globals.css */
@import "tailwindcss";
@import "../branding/ui/9mm.css";      /* adjust path to where the repo lives */
@import "../branding/fonts/fonts.css";
```

That single `ui/9mm.css` import brings the color tokens, the `@theme` block
(`bg-ink-950`, `text-brass`, `font-mono`, `tracking-label`, …), base styles, and
all shared component classes (`.bracket-card`, `.btn-terminal`, `.grid-bg`,
`.scanline`, `.stagger`, …). **Delete the local copies of those rules from your
globals.css** — local copies are how the sites drifted. Project-specific styles
go after the import and should be things this pack doesn't cover.

⚠ Never define `--color-base`, `--color-eth`, or `--color-chia` in `@theme` —
`text-base` collides with Tailwind's built-in font-size utility. Prefix chain
colors: `--color-chain-base`.

**Plain CSS / any stack** — `ui/9mm.css` works without Tailwind (browsers skip the
`@theme` block; the component classes are vanilla CSS). Or go minimal:

```html
<link rel="stylesheet" href="/branding/tokens/colors.css">
<link rel="stylesheet" href="/branding/fonts/fonts.css">
```

Toggle dark mode by adding `.dark` to `<html>`.

**Next.js fonts** — either self-host via `fonts/fonts.css`, or keep `next/font/google`
with the same families/weights. Self-hosting is preferred (no Google dependency).

**Programmatic** — read `tokens/tokens.json` (W3C design-tokens-style format).

**Updating** — bump the submodule (`git submodule update --remote`) or refresh the
vendored copy to a newer commit. Never fork a component locally; PR the change
here instead.
