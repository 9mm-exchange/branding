# 9MM Pro Branding Pack — Agent Guide

This repo is the **canonical reference** for 9MM Pro's brand and UI across all
frontends (hub, dex, 9x, claim, royal gate, xch, launch, tokens, …). It is not a
runtime dependency and does not claim that any product currently carries its
assets, token values, or recipes.

## How to use this pack (when working in a PRODUCT repo)

1. **Before any UI work**, read `DESIGN.md` and `SURFACES.md` here — colors,
   typography, product lockups, status boundaries, and accessibility rules live
   there. `index.html` shows the reference recipes with copyable markup.
2. **Do not add this repo as a submodule or import its CSS/assets across repositories.**
   If a product change is approved, implement it in that product's own source tree.
   Do not promise automatic inheritance of later brand changes or claim that the
   product is currently synced to this reference.
3. **Use the changelog as context.** Before proposing a cross-surface change, compare
   the guide and changelog with the product's local implementation. Adoption is
   manual and optional; this repository records no consumer state.
4. `ui/9mm.css` and the Tailwind `@theme` block are **reference code**, not a shared
   stylesheet. When translating its utilities locally, never define
   `--color-base`/`--color-eth`/`--color-chia` in `@theme` — `text-base` collides with
   Tailwind's font-size utility. Prefix chain colors, for example `--color-chain-base`.
5. Icons: **lucide-react only**. Sizes/conventions in `DESIGN.md` §5.
6. **Theme-safe artwork:** white-on-transparent images (logo PNGs, OG image,
   protocol marks) vanish on the light theme. Swap the logo variant with the
   theme, or pin the image on a fixed `#08060b` ink chip. Rule + examples in
   `DESIGN.md` §2; live demos in `index.html` (header logo swap, favicon chips).
   Always verify new UI in BOTH themes before shipping.

## Rules for changing THIS repo

- Any change to `ui/9mm.css`, `tokens/`, `fonts/`, or `DESIGN.md`:
  bump `VERSION` (semver — see CHANGELOG header for the rules), add a
  `CHANGELOG.md` entry, and update the version badge at the top of `README.md`.
- If the showcase's look changes materially, regenerate the README preview
  images (`docs/preview-dark.png` / `docs/preview-light.png`, 1280×800 viewport
  screenshots of `index.html` in each theme).
- New or changed component → add/update its demo + copyable markup in `index.html`,
  and its entry in `DESIGN.md` §5.
- Verify visually before committing: open `index.html` headlessly, check BOTH themes
  (the MODE toggle), confirm zero console errors.
- `ui/9mm.css` must stay valid as **plain CSS** so it remains a usable reference.
  Use `rgb(var(--x-rgb) / 0.5)` syntax — never `rgba(var(--x-rgb), 0.5)`, which
  is invalid outside Tailwind builds.
- All animation must no-op under `prefers-reduced-motion: reduce`.
- Class names are public API — renames/removals are MAJOR version bumps.
- Keep `tokens/colors.css`, `tokens/tokens.json`, and the DESIGN.md §3 tables in
  sync — same values, three formats.

## Optional note for a product repo's CLAUDE.md

Use this only if you want a local reminder that the reference exists:

```markdown
## Design System
The brand reference is https://github.com/9mm-exchange/branding. Before visual/UI
work, read its DESIGN.md and SURFACES.md. This product does not use the branding
repo as a submodule, runtime asset source, or imported stylesheet. Compare any
proposed brand change with this product's local implementation before applying it.
Do not deviate from DESIGN.md without explicit user approval.
```
