# Changelog — 9MM Pro Branding Pack

Agents and humans: check this file (and `VERSION`) to see what changed since your
site last synced with the pack. Every change to `ui/9mm.css`, `tokens/`, `fonts/`,
or `DESIGN.md` gets an entry here and a version bump:

- **MAJOR** — breaking: a class or token renamed/removed, a value change that
  requires consumer markup edits.
- **MINOR** — new components, classes, tokens, or assets. Backwards compatible.
- **PATCH** — value tweaks, doc fixes, asset regenerations.

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
