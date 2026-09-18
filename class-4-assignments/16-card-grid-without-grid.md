# Assignment 16 — Card Grid Without Grid

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 4 §7, §9 (flex-wrap, flex-basis)
**Build in:** `work/16-card-grid-without-grid/index.html` + `style.css`

---

## Goal

Lay out 9 cards, 3 per row, evenly spaced, using **only** Flexbox — no CSS Grid (that's next class). Get the sizing maths right so the wrapped rows don't misbehave.

## What you'll practice

- `flex-wrap` combined with a fixed `flex-basis` to force a specific number of columns
- Why the *last* row of a wrapped flex layout is the tricky part
- The difference `flex-grow: 0` vs `1` makes to a short final row

## Instructions

1. Build `index.html` with 9 `<article class="card">` elements inside a `<section class="grid">`, each with a title and a short paragraph.
2. In `style.css`:
   - `.grid`: `display: flex`, `flex-wrap: wrap`, `gap: 20px`
   - `.card`: a `flex-basis` calculated so **3 fit per row** accounting for the gaps (e.g. `flex: 0 0 calc((100% - 40px) / 3)` for a 20px gap — work out the maths for your own gap value), plus `flex-grow: 0`
3. Confirm you get exactly 3 cards per row, 3 rows, evenly gapped both horizontally and vertically.
4. Now change the card count to 8 (remove one) and look at the last row — with `flex-grow: 0` it should leave a gap rather than stretching the remaining 2 cards to fill the row. Try `flex-grow: 1` instead and see the difference. Decide which you prefer and say why, in a comment.

## Requirements

- [ ] Exactly 3 cards per row at a normal desktop width, with 9 cards
- [ ] Even `gap` both between columns and between rows
- [ ] A `calc()`-based `flex-basis` that accounts for the `gap`, not a guessed round number
- [ ] A written comparison of `flex-grow: 0` vs `1` on an incomplete last row

## Acceptance criteria

- Counting cards per row gives exactly 3, every row, with 9 cards.
- The gap between cards in a row visually matches the gap between rows.
- You can explain, in your own words, why a plain `33.33%` `flex-basis` would be too wide once a `gap` is added (it doesn't account for the gap's width).

## Hints

<details><summary>Show hint</summary>

With a 20px `gap` and 3 columns, there are 2 gaps per row (between card 1–2 and 2–3) = 40px of gap to subtract before dividing by 3: `calc((100% - 40px) / 3)`.
</details>
