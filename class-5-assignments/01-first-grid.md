# Assignment 01 — First Grid

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min (do it 3 times)
**Prereqs:** Class 5 §2–3 (turning on Grid, `fr` and `repeat()`)
**Build in:** `work/01-first-grid/index.html` + `style.css`

---

## Goal

Turn six stacked elements into a grid of 3 columns and 2 rows with three declarations — from memory, three times.

## What you'll practice

- `display: grid` on a container
- `grid-template-columns` with `repeat()` and `fr`
- `gap` — the same property you used in Flexbox
- That the **container** decides the columns; the items just fill the cells

## Instructions

1. Build `index.html` (with the viewport tag in the `<head>`): a `<section class="grid">` containing six `<p>` elements numbered 1 to 6.
2. In `style.css`, give the `<p>`s a `background-color`, some `padding`, and `margin: 0` so each cell is easy to see. Confirm they stack one per line.
3. Add three declarations to `.grid`:
   ```css
   .grid {
       display: grid;
       grid-template-columns: repeat(3, 1fr);
       gap: 16px;
   }
   ```
   Two neat rows of three appear.
4. Add a seventh `<p>`. Where does it go? Remove it again.
5. Delete the three declarations and type them again from memory. Then do it a third time, in a brand-new folder.

## Requirements

- [ ] `.grid` becomes a 3-column grid with exactly three declarations
- [ ] Six boxes in two rows of three, with an even gap in both directions
- [ ] You added a seventh item and saw a new row appear by itself
- [ ] Done 3 times, the third with nothing to refer to

## Acceptance criteria

- The three columns are equal width and fill the container at any window width.
- The gap between columns matches the gap between rows.
- No Flexbox and no widths on the `<p>`s — only the container is styled for layout.

## Hints

<details><summary>Show hint</summary>

If nothing changes, check the declarations are on `.grid` — the **parent** — not on the `<p>`s. Just like Flexbox, `display: grid` only arranges an element's direct children.
</details>
