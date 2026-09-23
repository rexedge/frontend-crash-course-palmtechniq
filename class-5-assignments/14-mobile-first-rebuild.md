# Assignment 14 — Mobile-First Rebuild

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 5 §13–14 (media queries, mobile-first)
**Build in:** `work/14-mobile-first-rebuild/index.html` + `style.css`

---

## Goal

Take a page you've already built, delete its layout CSS, and rebuild it strictly mobile-first: the phone layout as the base, then `min-width` queries that add columns.

## What you'll practice

- Writing the phone layout with no media query
- Adding layout with `min-width` queries, smallest first
- Noticing how much less you have to "undo"

## Instructions

1. Choose a page with a real multi-column layout. Good picks: your [Assignment 10](10-dashboard-card-grid.md) dashboard (desktop-first on purpose — perfect for this), your Class 4 pricing table, or your Class 4 blog homepage.
2. Copy it into `work/14-mobile-first-rebuild/`.
3. In `style.css`, delete every **layout** rule: `display: flex` / `display: grid`, templates, spans, `flex` values, widths used to make columns, and all media queries. Keep colours, fonts, spacing, and borders.
4. Look at the page at 375px. It's probably already a decent phone layout — HTML stacks things in one column on its own.
5. Fix anything that still looks wrong at 375px — **without** a media query.
6. Widen the window slowly. At the first width where the page looks stretched or empty, add `@media (min-width: ...)` and bring in the first columns. Keep widening, and add a second query only if you need one.

## Requirements

- [ ] The base styles contain **no** media queries and give a good phone layout
- [ ] Every media query uses `min-width`, and they appear smallest first
- [ ] There are no `max-width` queries at all
- [ ] A comment above each query saying why you chose that width (e.g. "at 720px the cards looked too wide")

## Acceptance criteria

- Checked at 375px, 768px, and 1280px, and each looks deliberate, not accidental.
- Your rebuilt CSS has no rules that exist only to undo something from a wider layout.
- A comment at the top of the file: roughly how many lines of layout CSS the original had, and how many the rebuild has.

## Hints

<details><summary>Show hint</summary>

If you're rebuilding the Assignment 10 dashboard: base = `1fr`; `@media (min-width: 600px)` = `repeat(2, 1fr)`; `@media (min-width: 1000px)` = `repeat(4, 1fr)`. The wide cards' `span 2` is written once, inside the 600px query — and there's nothing to reset.
</details>
