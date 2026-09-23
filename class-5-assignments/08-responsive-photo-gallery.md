# Assignment 08 — Responsive Photo Gallery

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~45 min · 🧵 keep this file
**Prereqs:** Class 5 §9, §11–15 (guided practice)
**Build in:** `work/08-responsive-photo-gallery/index.html` + `style.css`

---

## Goal

Build a 12-photo gallery that reflows from one column on a phone to five on a wide screen, with a big featured photo once there's room. This is the Class 5 hands-on.

## What you'll practice

- `repeat(auto-fit, minmax(220px, 1fr))` — a column count with no media query
- `aspect-ratio` + `object-fit: cover` to turn mixed-shape photos into neat squares
- A mobile-first `min-width` query that adds a 2 × 2 span only where there's room for it
- Fluid spacing and headings with `clamp()`

## Instructions

1. Follow the lesson's guided practice (Class 5 §15). Type it by hand — don't paste.
2. Use photos of **mixed shapes** on purpose, e.g. `https://picsum.photos/800/600?random=1`, `https://picsum.photos/600/800?random=2`, `https://picsum.photos/600/600?random=3`… The `?random=` number makes each photo different; without it, the browser may show the same photo twelve times.
3. Structure:
   - `<header class="intro">` with an `<h1>` and a short `<p>`
   - `<main>` containing a `<section class="gallery">` with 12 `<img>` elements; the first one has `class="featured"`
4. Styles:
   - The `box-sizing` reset and the `img` reset (`max-width: 100%; height: auto; display: block;`)
   - `body`: font, colours, and `padding: 24px clamp(16px, 5vw, 48px)`
   - `.intro`: `max-width: 40rem`, centred; its `h1` sized with `clamp()`
   - `.gallery`: `max-width: 1200px`, centred, `display: grid`, the `auto-fit` / `minmax(220px, 1fr)` columns, and a `gap`
   - `.gallery img`: `width: 100%; aspect-ratio: 1 / 1; object-fit: cover;`
   - `@media (min-width: 700px)`: a slightly bigger `gap`, and `.gallery .featured` covering 2 columns and 2 rows
5. Test at 375px, 768px, 1024px, and 1280px. Then drag the window slowly from 320px to 1440px.

## Requirements

- [ ] The viewport tag is in the `<head>`
- [ ] 12 images of mixed shapes, every one with `alt` text
- [ ] The columns come from `repeat(auto-fit, minmax(220px, 1fr))` — no media query changes the column count
- [ ] Every image is a square, via `aspect-ratio: 1 / 1` + `object-fit: cover`
- [ ] Exactly one media query, `min-width: 700px`, which features photo 1 (2 × 2) and widens the gap
- [ ] The intro text is centred and no wider than `40rem`

## Acceptance criteria

- 375px: one column. 768px: two columns, with photo 1 as a big square across both. 1280px: five columns, with photo 1 covering 2 × 2 cells.
- No horizontal scrollbar at any width from 320px to 1440px.
- No photo is squashed or stretched.
- Try this once: move the two span lines **out** of the media query and look at 375px. You'll see why the span has to live inside the query. Then put them back.

## Hints

<details><summary>Show hint</summary>

If photo 1 makes the page scroll sideways on a phone, its `grid-column: span 2` has escaped the media query. On a one-column grid, a 2-column span forces the browser to add an extra column — wider than the screen.
</details>

## Stretch (optional)

Swap the placeholders for 12 of your own photos, and replace every `alt` with a real description of what's in the picture.
