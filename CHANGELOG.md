# Changelog — 9MM Pro Branding Pack

Agents and humans: check this file (and `VERSION`) to see what changed since your
site last synced with the pack. Every change to `ui/9mm.css`, `tokens/`, `fonts/`,
or `DESIGN.md` gets an entry here and a version bump:

- **MAJOR** — breaking: a class or token renamed/removed, a value change that
  requires consumer markup edits.
- **MINOR** — new components, classes, tokens, or assets. Backwards compatible.
- **PATCH** — value tweaks, doc fixes, asset regenerations.

## 1.1.0 — 2026-06-10

Light theme softened + default-scheme policy. Prompted by repeated "light mode
is too bright" user feedback.

- **Light palette lowered ~4% across the ladder; pure white eliminated.**
  The old `#ffffff` card on `#faf7ef` read as glare. New surfaces:
  bg `#f1ebdb`, card `#f8f4e7`, input `#ece5d0`, secondary `#e5dcc4`,
  muted `#ded3b6`. Light brass deepened one step to hold contrast:
  `#7d672c` / hot `#997f38` / deep `#54431a`. Light fg warmed (`#171208`),
  hairlines strengthened (`rgba(125,103,44,0.32)`), light success now `#157a3d`.
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
