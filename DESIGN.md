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

Brass on ink. Dark mode is the brand's home; light mode is **aged paper** — a
distinctly toned manila, field-manual feel. All tokens ship as RGB triples
(`--brass-rgb: 200 168 78`) so alpha composition works: `rgb(var(--brass-rgb) / 0.35)`.

> **Default scheme policy: every site opens in dark mode.** Light is an explicit,
> persisted toggle — never the landing default. (Rationale: dark is the brand's
> home, and "light mode is too bright" feedback traced largely to users dropped
> into light by default.)
>
> **No pure white anywhere.** The original light theme (`#ffffff` cards on
> `#faf7ef`) read as glare and was replaced in v1.1.0 with the aged-paper
> palette below. Don't reintroduce white surfaces.

### Brand accent — brass

| Token | Dark | Light | Role |
|---|---|---|---|
| `brass` | `#c8a84e` · `200 168 78` | `#6e5a24` · `110 90 36` | Primary accent, CTAs, active states |
| `brass-hot` | `#e8c466` · `232 196 102` | `#8a7330` · `138 115 48` | Hover, highlights, glows |
| `brass-deep` | `#967c38` · `150 124 56` | `#4a3c16` · `74 60 22` | Borders, muted accent |

> **Canonical dark brass is `#c8a84e`.** The landing page currently uses `#d7b249`
> for its dark primary — treat that as legacy drift; new work should use `#c8a84e`.

### Surfaces — ink scale (darkest token = page background)

| Token | Dark | Light | Role |
|---|---|---|---|
| `ink-950` | `#08060b` | `#e7dfc9` | Page background |
| `ink-900` | `#0d0a12` | `#efe8d4` | Card (light: never pure white) |
| `ink-800` | `#1c1822` | `#e0d6ba` | Popover, input |
| `ink-700` | `#141018` | `#d8cca8` | Secondary |
| `ink-600` | `#24202a` | `#cfc098` | Muted |

### Foreground hierarchy

| Token | Dark | Light | Role |
|---|---|---|---|
| `fg` | `#ffffff` | `#1c1609` | Body text |
| `fg-muted` | `#a8a29e` | `#41382a` | Secondary text |
| `fg-subtle` | `#76706a` | `#6b5f45` | Captions, metadata |

### Semantic

| Token | Dark | Light | Role |
|---|---|---|---|
| `warn` | `#e8b84a` | `#a07812` | Warnings |
| `danger` | `#e0574e` | `#b03e37` | Errors, price-down |
| `success` | `#4ade80` | `#136f38` | Success, price-up |

### Lines & glow

| Token | Dark | Light |
|---|---|---|
| `--hairline` | `rgba(255,255,255,0.08)` | `rgba(110,90,36,0.38)` |
| `--hairline-brass` | `rgba(200,168,78,0.35)` | `rgba(110,90,36,0.6)` |
| `--shadow-brand` | `0 0 40px -10px rgba(200,168,78,0.55)` | `0 0 40px -10px rgba(110,90,36,0.3)` |

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
- **Tables** — `.table-terminal`: uppercase tracked headers (`fg-subtle`, sortable →
  brass), hairline row separators, right-aligned tabular numerals, brass row-hover
  tint, `.num-up`/`.num-down` semantics. `.sticky-head` variant for scrolling panels
  (opaque brass-tinted sticky thead — claim holders pattern).
- **Ticker rows** — `.ticker-row` (rank `.rowno` / name / figures grid), `.is-selected`
  gets a 3px brass inset edge.
- **Scrollbars** — styled globally: 10px, transparent track, ink-700 thumb, brass on
  hover. Ships in `ui/9mm.css`; nothing to add per project.
- **Gradients & glows** — page backdrop is either flat `bg-ink-950` (xch) or
  `.body-gradient` (landing: brass top glow + faint vertical gradient) — one per site,
  never both. `--shadow-brand` for featured panels; `.glow` / `.glow-sm` / `.glow-text`
  for brass element glows.
- **Prose** — `.acc-body` for FAQ/compliance/long-form: Inter 14px/1.65 at `fg/72`,
  dashed-brass-underline links, disc lists.
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

## 6. Layout & system specs

### Spacing & layout

- **Base unit:** 4px (Tailwind scale). Density is *compact-comfortable* — data UIs
  (tables, tickers) run tight (`py-2`–`py-3` rows); marketing sections breathe.
- **Content shell:** centered container, `max-w-6xl`–`max-w-7xl` (1152–1280px),
  `px-4` mobile / `px-6` desktop.
- **Section rhythm:** `py-16`–`py-24` (64–96px) between landing sections; section
  separators are hairlines, not whitespace alone.
- **Card padding:** `p-5` for interactive cards, `p-7`/`p-8` for content panels.
- **Corners:** square. `border-radius: 0` everywhere except token/chain avatars
  (`rounded-full`). No rounded cards or buttons — radius is the fastest way to
  break the terminal aesthetic.

### Breakpoints

Tailwind defaults — `sm` 640, `md` 768, `lg` 1024, `xl` 1280. Conventions in use:
nav links hide below `md` (hamburger/launch link instead), sub-product lockup text
hides below `lg`, table columns drop with `hidden md:table-cell`.

### Z-index scale

Defined as CSS vars in `ui/9mm.css` — keep every layer on this ladder:

| Var | Value | Layer |
|---|---|---|
| `--z-noise` | 1 | `.noise::before` |
| `--z-scanline` | 2 | `.scanline::after` |
| `--z-sticky` | 10 | sticky table heads, in-panel chrome |
| `--z-header` | 40 | site header |
| `--z-tooltip` | 50 | tooltips |
| `--z-toast` | 90 | toast stack |
| `--z-modal` | 100 | modal backdrop + panel |

### Motion standard

- **Durations:** 150ms small hovers (borders, text color) · 200–250ms buttons,
  cards, theme transitions · 220ms toast entry · 700ms reveal/stagger · one-shot
  1s price flashes. Nothing between 1s and ambient (8s scanline, 50s marquee).
- **Easing:** `ease` / `ease-out` for micro-interactions; entrances use
  `cubic-bezier(0.2, 0.8, 0.2, 1)` (the reveal curve).
- **Policy:** motion is functional or ambient, never decorative-per-element.
  Entrances stagger once per page load (`.stagger`); state changes flash; the rest
  is hover feedback. Everything respects `prefers-reduced-motion` (handled
  globally in `ui/9mm.css`).

### Accessibility

- **Focus:** never remove outlines. `ui/9mm.css` ships a global `:focus-visible`
  brass ring (1px, 2px offset).
- **Contrast:** the `text-fg/N` opacity overrides in `ui/9mm.css` exist to keep
  low-opacity captions at AA — don't bypass them with hardcoded rgba text colors.
  Brass-on-ink passes AA at ≥12px; don't set brass body text below that.
- **Semantics:** color is never the only signal — pair `num-up`/`num-down` with
  ▲/▼, badges with text, status dots with labels.
- **Motion:** all animation must no-op under `prefers-reduced-motion: reduce`
  (already covered for every class in `ui/9mm.css`; match that for new ones).

## 7. Favicons & page metadata

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

## 8. How to consume this pack

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
