# Changelog — 9MM Pro Branding Pack

Agents and humans: check this file (and `VERSION`) to see what changed since your
site last synced with the pack. Every change to `ui/9mm.css`, `tokens/`, `fonts/`,
or `DESIGN.md` gets an entry here and a version bump:

- **MAJOR** — breaking: a class or token renamed/removed, a value change that
  requires consumer markup edits.
- **MINOR** — new components, classes, tokens, or assets. Backwards compatible.
- **PATCH** — value tweaks, doc fixes, asset regenerations.

## 1.2.0 — 2026-06-10

Close the asset gaps found auditing the landing repo against the pack — the
landing was the only source of truth for collection artwork.

- **`assets/nfts/`** — OG collection art (pulse-og, based-og, sonic-og,
  genesis-og) plus the four per-chain PUSSY 404 renders, copied verbatim from
  the landing's `public/nfts/`.
- **`assets/tokens/pussy.webp`** — the PUSSY 404 token icon (the landing token
  table and NFT cards use it; the pack only had the four 9MM icons).

Still known-missing (needs design tooling/art, tracked here so it isn't lost):
a horizontal wordmark/lockup SVG (mark + `9MM.PRO` type as paths) for contexts
where type can't be set; product marks for DEX / Claim / XCH Terminal; a social
kit beyond the one OG card (X banner, square avatar exports, the per-product
OG template described in DESIGN.md §7).

## 1.1.0 — 2026-06-10

Light theme replaced with **aged paper** + default-scheme policy. Prompted by
repeated "light mode is too bright" user feedback.

- **Light palette is now aged paper — manila, field-manual tone, no pure white.**
  The old `#ffffff` card on `#faf7ef` read as glare. New surfaces:
  bg `#e7dfc9`, card `#efe8d4`, input `#e0d6ba`, secondary `#d8cca8`,
  muted `#cfc098`. Light brass deepened to read rich on the toned paper:
  `#6e5a24` / hot `#8a7330` / deep `#4a3c16`. Light fg warmed (`#1c1609`),
  hairlines strengthened (`rgba(110,90,36,0.38)`), light semantics deepened
  (warn `#a07812`, danger `#b03e37`, success `#136f38`).
  Dark theme unchanged. Token-only change — no markup edits needed in consumers;
  sites pick it up on next sync.
- **Policy: every site defaults to dark mode.** Light is an explicit, persisted
  toggle (DESIGN.md §3). The tokens portal currently defaults to light — out of
  compliance until updated.

## 1.0.0 — 2026-06-10

Initial release.

- **Tokens** — canonical brass/ink color system (light + dark) in `tokens/colors.css`,
  `tokens/tokens.json`, Tailwind v4 `@theme` snippet. Canonical dark brass declared
  `#c8a84e` (landing's `#d7b249` marked legacy drift).
- **UI layer** — `ui/9mm.css`: base styles, buttons, bracket cards, fields, tables
  (+ sticky-head), ticker rows, tabs, pagination, badges, form controls, switch,
  modal, toasts, loading/empty states, tooltip, prose, ambient washes, glows,
  scrollbars, focus ring, z-index scale, all animations with reduced-motion guards.
  Line-grid backgrounds retired in favor of solid ink + ambient washes.
- **Logos** — SVG masters traced from the 559px raster (white/black/brass) + PNG renders.
- **Favicons** — full set incl. generated android-chrome 192/512, theme-aware
  `icon.svg`, maskable PWA icon, corrected `site.webmanifest`, head snippet.
- **Fonts** — self-hosted JetBrains Mono (300–800 + italic) and Inter (400–700)
  woff2 with `fonts.css` and OFL licenses.
- **Docs** — `DESIGN.md` brand guide (logo, color, type, components, layout/motion/
  z-index/accessibility specs, consumption), `index.html` live component reference.
- **Assets** — chain icons, 9MM token icons, 9x protocol marks, OG image reference.
