# 9MM Pro Branding Pack — Agent Guide

This repo is the **single source of truth** for 9MM Pro's brand and UI across all
frontends (landing, dex, 9x, claim, xch, tokens, …). Product repos reference this
repo; they do not keep their own copies of brand CSS.

## How to use this pack (when working in a PRODUCT repo)

1. **Before any UI work**, read `DESIGN.md` here — colors, typography, components,
   layout/motion/z-index/accessibility rules all live there. `index.html` shows every
   component live with copyable markup (works from `file://`).
2. **Never copy component CSS into a product's globals.css.** Import
   `ui/9mm.css` (+ `fonts/fonts.css`) instead. Local copies are how the sites
   drifted apart. If a component needs to change, change it HERE.
3. **Check for design updates**: compare the product's recorded pack version against
   `VERSION`, then read `CHANGELOG.md` entries since. MAJOR = expect markup changes;
   MINOR = new things available; PATCH = silent value updates.
4. Tailwind utilities come from the `@theme` block in `ui/9mm.css`
   (`bg-ink-950`, `text-brass`, `text-fg-muted`, `font-mono`, `tracking-label`, …).
   Never define `--color-base`/`--color-eth`/`--color-chia` in `@theme` —
   `text-base` collides with Tailwind's font-size utility.
5. Icons: **lucide-react only**. Sizes/conventions in `DESIGN.md` §5.
6. **Theme-safe artwork:** white-on-transparent images (logo PNGs, og-image,
   protocol marks) vanish on the light theme. Swap the logo variant with the
   theme, or pin the image on a fixed `#08060b` ink chip. Rule + examples in
   `DESIGN.md` §2; live demos in `index.html` (header logo swap, favicon chips).
   Always verify new UI in BOTH themes before shipping.

## Rules for changing THIS repo

- Any change to `ui/9mm.css`, `tokens/`, `fonts/`, or `DESIGN.md`:
  bump `VERSION` (semver — see CHANGELOG header for the rules) and add a
  `CHANGELOG.md` entry.
- New or changed component → add/update its demo + copyable markup in `index.html`,
  and its entry in `DESIGN.md` §5.
- Verify visually before committing: open `index.html` headlessly, check BOTH themes
  (the MODE toggle), confirm zero console errors.
- `ui/9mm.css` must stay valid as **plain CSS** (it's consumed both through Tailwind
  builds and raw `<link>`). Use `rgb(var(--x-rgb) / 0.5)` syntax — never
  `rgba(var(--x-rgb), 0.5)`, which is invalid outside Tailwind builds.
- All animation must no-op under `prefers-reduced-motion: reduce`.
- Class names are public API — renames/removals are MAJOR version bumps.
- Keep `tokens/colors.css`, `tokens/tokens.json`, and the DESIGN.md §3 tables in
  sync — same values, three formats.

## Snippet for product repos' CLAUDE.md

Paste this into each consuming site's CLAUDE.md (adjust the path):

```markdown
## Design System
The brand source of truth is the branding repo (../branding or the
9mm-pro/branding GitHub repo). Before any visual/UI work: read its DESIGN.md;
use components from ui/9mm.css (imported in globals.css) — never re-implement
or locally copy them. This project is synced to branding pack version X.Y.Z —
when starting UI work, diff that against branding/VERSION and read
branding/CHANGELOG.md for anything newer, then update the pin here.
Do not deviate from DESIGN.md without explicit user approval.
```
