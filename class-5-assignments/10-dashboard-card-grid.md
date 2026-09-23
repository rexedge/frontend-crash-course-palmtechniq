# Assignment 10 — Dashboard Card Grid

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min
**Prereqs:** Class 5 §3–4, §13–14 (tracks, spanning, media queries, mobile-first)
**Build in:** `work/10-dashboard-card-grid/index.html` + `style.css`

---

## Goal

Build a stats dashboard whose column count steps down at set widths. This one is written **desktop-first**, with `max-width` queries, on purpose — so you can feel how it differs from mobile-first.

## What you'll practice

- `max-width` media queries, ordered largest to smallest
- Resetting a span when the column count drops
- Why desktop-first means *undoing* things

## Instructions

1. Build `index.html`: an `<h1>`, then a `<section class="dashboard">` with 8 `<article>` cards, all with `class="stat"`:
   - Six are small stats: a label and a big number, e.g. "Visitors" / "1,204".
   - Two are wide: add a second class, `stat stat-wide`, with the titles "Revenue chart" and "Recent activity" (a placeholder `<p>` inside each is fine). Put them 5th and 6th.
2. **Desktop first** — base styles, no media query:
   - `.dashboard`: `display: grid`, `grid-template-columns: repeat(4, 1fr)`, a `gap`
   - `.stat-wide`: `grid-column: span 2`
3. `@media (max-width: 1000px)`: `.dashboard` goes to `repeat(2, 1fr)`. The wide cards can keep `span 2` — that's now the full width.
4. `@media (max-width: 600px)`: `.dashboard` goes to `1fr`, **and** `.stat-wide` goes back to `grid-column: auto`. Otherwise it would still try to cover 2 columns in a 1-column grid.
5. Style the cards (background, padding, a big `font-size` for the numbers) and test at 1280px, 900px, and 375px.

## Requirements

- [ ] 4 columns by default, 2 at 1000px and below, 1 at 600px and below
- [ ] The two wide cards cover 2 columns on desktop
- [ ] Queries ordered **largest first** (`1000px` above `600px`) — the opposite of mobile-first
- [ ] The span is reset inside the smallest query

## Acceptance criteria

- At 1280px: four columns, with the two wide cards each covering two.
- At 375px: one clean column, and no horizontal scrollbar.
- In a comment at the bottom of `style.css`, 2–3 sentences: what did you have to *undo* in the queries, and how would the same layout look written mobile-first? ([Assignment 14](14-mobile-first-rebuild.md) asks you to actually do it.)

## Hints

<details><summary>Show hint</summary>

Try deleting the span reset from the 600px query and look at 375px. A `span 2` on a one-column grid makes the browser add a second column — and a horizontal scrollbar. That "remember to undo it" step is the price of desktop-first.
</details>
