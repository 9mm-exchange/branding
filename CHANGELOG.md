# Changelog — 9MM Pro Branding Pack

Agents and humans: check this file (and `VERSION`) before carrying reference
material into a product. Every change to `ui/9mm.css`, `tokens/`, `fonts/`,
`DESIGN.md`, or `SURFACES.md` gets an entry here and a version bump:

- **MAJOR** — a published reference class/token rename/removal, or a value change
  that requires a deliberate local migration.
- **MINOR** — new components, classes, tokens, or assets. Backwards compatible.
- **PATCH** — value tweaks, doc fixes, asset regenerations.

## 1.3.0 — 2026-07-28

**Reference-model clarification.** This repository documents the brand baseline;
it is not a git submodule, cross-repository CSS import, remote asset source, or
runtime dependency. It does not assert that existing product repositories are
synced to it. When a product change is chosen, its implementation remains local to
that product.

- **`README.md`, `DESIGN.md`, and `CLAUDE.md`** — replaced the automatic-import
  contract with a deliberate adoption and review workflow. `ui/9mm.css` and the
  Tailwind theme are now reference code to translate locally.
- **`SURFACES.md`** — added the canonical product/environment directory: hub, DEX,
  9x, Claim, Claim Dev, Royal Gate, XCH Terminal, and 9MM Launch. It defines
  lockups, status vocabulary, copy guardrails, active versus legacy assets, and
  the boundary between shared branding and product-owned behavior.
- **Product shell recipes** — added `.product-lockup`, `.system-status`,
  `.step-rail`, and `.network-chip` reference primitives to `ui/9mm.css` and the
  component showcase. They are text-first patterns, not new bespoke product marks.
- **Current asset additions** — copied the Robinhood and Arc chain marks from the
  current `landing` GitHub branch, plus the current XCH Chia mark from the
  `xch-terminal` GitHub branch. Robinhood and Arc remain informational `SOON`
  placeholders: no wallet, RPC, API, proof, claim, or transaction behavior is
  implied.
- **Light-theme wording** — clarified that no pure-white *surfaces* are allowed;
  white remains valid for dark-theme primary text and the white masterbrand mark.

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
