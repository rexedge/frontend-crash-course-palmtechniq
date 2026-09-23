# Assignment 04 — Spanning

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 5 §3–4 (`grid-auto-rows`, grid lines and spanning)
**Build in:** `work/04-spanning/index.html` + `style.css`

---

## Goal

Make items cover more than one cell — with `span`, line numbers, and `-1` — and predict where everything else will land before you check.

## What you'll practice

- `grid-column: span 2`, `grid-row: span 2`, and `grid-column: 1 / -1`
- Line numbers vs column counts (the off-by-one trap)
- The dev-tools grid overlay with line numbers

## Instructions

1. Build a `<section class="grid">` with 8 `<p>` boxes numbered 1–8. Give each a `background-color`, `padding`, and `margin: 0`.
2. Style the grid. The fixed row height makes row spans easy to see:
   ```css
   .grid {
       display: grid;
       grid-template-columns: repeat(4, 1fr);
       grid-auto-rows: 80px;
       gap: 12px;
   }
   ```
3. Add a class to three of the boxes and write these rules:
   - box 1: `grid-column: span 2;`
   - box 3: `grid-row: span 2;`
   - box 5: `grid-column: 1 / -1;`
4. **Before you save**, sketch on paper where you think each box will land. Then save and compare.
5. Turn on the grid overlay (Elements panel → the `grid` badge) and switch on line numbers in the **Layout** tab. Check each span against the numbers.
6. Change box 1 to `grid-column: 1 / 3`. Does anything move? Now try `1 / 4` and count the columns it covers. Put it back to `span 2`.

## Requirements

- [ ] Box 1 covers 2 columns, box 3 covers 2 rows, box 5 covers the full row
- [ ] Your paper prediction is kept (right or wrong), with a note of what actually happened
- [ ] You viewed the grid overlay with line numbers

## Acceptance criteria

- You can explain why `grid-column: 1 / 3` covers **two** columns, not three.
- Row 2 has two empty cells. You can explain why: box 5 needs a whole row to itself, so it starts a new row, and Grid doesn't go back to fill the gap it left.
- Change the grid to `repeat(6, 1fr)`: box 5 still covers the full width. You can explain why `-1` makes that work.

## Hints

<details><summary>Show hint</summary>

Four columns have **five** lines: 1, 2, 3, 4, 5. `-1` is always the last line, however many columns there are.
</details>
