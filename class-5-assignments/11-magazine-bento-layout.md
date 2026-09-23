# Assignment 11 — Magazine / Bento Layout

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 5 §3–4, §12, §14 (`grid-auto-rows`, spanning, `minmax()`, mobile-first)
**Build in:** `work/11-magazine-bento-layout/index.html` + `style.css`

---

## Goal

Build a magazine-style front page on a 12-column grid, where stories come in different sizes — and where the whole thing is a simple single column on a phone.

## What you'll practice

- A 12-column grid with `repeat(12, 1fr)`
- Spanning columns **and** rows to make tiles of different sizes
- `grid-auto-rows` with `minmax()` for a minimum tile height
- Keeping every span inside a `min-width` query

## Instructions

1. Build `index.html`: a `<section class="magazine">` with 7 `<article>` stories, each with a heading and a short `<p>`. Give them size classes, in this order:
   - 1 × `story-hero`
   - 2 × `story-medium`
   - 4 × `story-small`
2. **Phone first**, no media query: `.magazine` is `display: grid` with a `gap`. That's it — one column, stories stacked, each row as tall as its content.
3. `@media (min-width: 700px)`:
   - `.magazine`: `grid-template-columns: repeat(12, 1fr)` and `grid-auto-rows: minmax(160px, auto)` — every row at least 160px tall, taller if the text needs it
   - `.story-hero`: `grid-column: span 8; grid-row: span 2;`
   - `.story-medium`: `grid-column: span 4;`
   - `.story-small`: `grid-column: span 3;`
4. Style each tile: `padding`, a `background-color`. For the hero, try a `background-image` with `background-size: cover` (Class 3).
5. Test at 375px and 1280px.

## Requirements

- [ ] 7 stories: 1 hero, 2 medium, 4 small
- [ ] Phone: a single column, with **no** spans active
- [ ] From 700px: a 12-column grid; the hero covers 8 columns × 2 rows; the two mediums cover 4 columns each and stack beside the hero; the smalls cover 3 columns each, four to a row
- [ ] `grid-auto-rows: minmax(160px, auto)` so tiles have a minimum height but still grow for long text
- [ ] No empty holes in the wide layout

## Acceptance criteria

- At 1280px the tiles form a solid rectangle: the hero top-left, the two mediums stacked on its right, and four smalls in a row underneath.
- At 375px: one column, and no horizontal scrollbar.
- With the grid overlay on, every tile's edges sit exactly on grid lines.

## Hints

<details><summary>Show hint</summary>

Check the maths row by row. The hero rows: 8 + 4 = 12. The small row: 3 + 3 + 3 + 3 = 12. If a row doesn't add up to 12, you'll get a hole, or a tile pushed down to the next row.
</details>

## Stretch (optional)

Add a tablet layout. Change the first query to a **6**-column grid (hero `span 6` × 2 rows, mediums `span 3`, smalls `span 3`), then add `@media (min-width: 1024px)` with the 12-column version. Check that both layouts add up with no holes.
