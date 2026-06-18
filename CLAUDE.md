# CLAUDE.md

Guidance for AI assistants (Claude Code and others) working in this repository.

## What this repository is

`demofiles` is an **asset / media repository**, not a software project. It
contains brand and marketing graphics for **Aardvark Technology** and related
betting/lottery products (e.g. "advbet"). There is **no application code, no
build system, no dependencies, no tests, and no CI**. The repository is a flat
collection of image files at the root.

Because there is nothing to build or run, the usual software workflows
(install, compile, lint, test) **do not apply**. Treat tasks here as
asset management: adding, replacing, renaming, optimizing, or organizing
image files.

## Repository layout

All files live in the repository root (flat structure). 28 media files,
grouped by purpose:

### Brand / logos
- `Aardvark_Icon_v3_White.svg` — Aardvark icon, white fill, 32×32 viewBox
- `adv-logo.png`, `adv-logo-wht.png` — Aardvark wordmark logos (dark / white)
- `logo_new.png` — updated logo
- `Horizontal.png`, `Vertical.png` — logo lockups in two orientations
- `skypilot-icon.png`, `skypilot.jpg`, `skypilot2.jpg` — "SkyPilot" product imagery

### Lottery game artwork ("shaman" themed `.webp`)
One illustration per lottery game, all sharing the `lotto_<game>_shaman.webp`
naming pattern:
- `lotto_daily_lotto_shaman.webp` (and a duplicate `lotto_daily_lotto_shaman (1).webp`)
- `lotto_euromillions_shaman.webp`
- `lotto_lotto_plus_shaman.webp`
- `lotto_megamillions_shaman.webp`
- `lotto_powerball_shaman.webp`, `lotto_powerball_plus_shaman.webp`
- `lotto_sa_lotto_shaman.webp`
- `lotto_set_for_life_shaman.webp`
- `lotto_uk49s_shaman.webp`

### Promo / themed graphics (aviation / sky theme)
- `advbet-cashback-promo.svg` — full 1920×1080 promo banner (dark teal `#00C4B4` palette)
- `Plane.svg`, `Plane001.svg`, `Rocket.svg`, `UFO.svg`, `Air-baloons.svg`, `Birds.svg`
- `converted_lightweight.webp`, `soccer_lightweight.webp` — optimized raster assets

## File formats and when to use them

- **SVG** — logos, icons, and vector illustrations. Preferred for anything that
  must scale crisply. Keep `viewBox` intact when editing.
- **WebP** — photographic / illustrated artwork (game tiles, promos). Used as
  the lightweight delivery format; note the `_lightweight` suffix convention for
  size-optimized variants.
- **PNG** — logos needing transparency where SVG isn't available.
- **JPG** — full-bleed photographic imagery without transparency.

## Conventions to follow

- **Naming:** lowercase with underscores for grouped sets (`lotto_<game>_shaman.webp`);
  brand assets keep their established names. Mirror the existing pattern of any
  set you add to rather than inventing a new scheme.
- **Light/dark variants:** suffix white/light versions with `-wht` or `_White`
  (matching `adv-logo-wht.png`, `Aardvark_Icon_v3_White.svg`).
- **Optimized variants:** suffix size-reduced versions with `_lightweight`.
- **Avoid duplicates:** the repo currently has a duplicate
  (`lotto_daily_lotto_shaman (1).webp`). Do not introduce ` (1)`-style copies;
  if a file with parentheses appears, it is almost certainly an accidental
  duplicate worth flagging or removing.
- **Color palette:** the advbet brand uses a dark background with teal accent
  (`#00C4B4`); match it when producing new promo art in the same family.

## Development workflow

This repo is populated mostly through GitHub's "Add files via upload" web flow
(visible throughout the commit history). When working from Claude Code:

- **Branch:** develop on the assigned feature branch and never push to `main`
  without explicit permission.
- **Commits:** use clear, descriptive messages (e.g. `Add powerball promo art`,
  `Optimize soccer hero to webp`) — improve on the generic "Add files via upload".
- **Push:** `git push -u origin <branch-name>`, retrying on network errors with
  exponential backoff.
- **Pull requests:** do **not** open a PR unless explicitly asked.

## Guidance for common tasks

- **Adding an asset:** place it at the repo root, name it per the conventions
  above, and confirm there isn't already a near-duplicate.
- **Replacing an asset:** overwrite in place so existing references (used by
  external sites/apps that consume these files) keep working; don't rename
  unless asked.
- **Optimizing images:** prefer WebP for raster art; preserve dimensions and the
  `_lightweight` naming convention.
- **Editing SVGs:** they are hand/tool-generated XML — keep the root `svg`
  attributes (`viewBox`, `width`, `height`, `xmlns`) and existing IDs intact so
  the graphics render correctly when embedded.

## Inspecting files

ImageMagick is not installed in this environment. To inspect assets:
- SVGs are plain text — open them directly with the Read tool.
- For raster files, rely on file size and naming; the Read tool can render
  PNG/JPG/WebP visually when you need to see the actual image.
