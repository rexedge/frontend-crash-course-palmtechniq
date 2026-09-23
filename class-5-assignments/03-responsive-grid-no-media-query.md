# Assignment 03 — Responsive Grid, No Media Query

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 5 §12 (`auto-fit` + `minmax()`)
**Build in:** `work/03-responsive-grid-no-media-query/index.html` + `style.css`

---

## Goal

Build a card grid that chooses its own number of columns as the window changes size — with one line of CSS and zero media queries.

## What you'll practice

- `repeat(auto-fit, minmax(200px, 1fr))`
- Reading `minmax()` as "at least … at most …"
- The difference between `auto-fit` and `auto-fill`

## Instructions

1. Build `index.html` with a `<section class="cards">` holding 8 `<article class="card">` elements, each with an `<h3>` and a short `<p>`.
2. Style the cards so you can see them: `background-color`, `padding`, a `border`.
3. On `.cards`:
   ```css
   .cards {
       display: grid;
       grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
       gap: 16px;
   }
   ```
4. Drag the window slowly from wide to narrow. Count the columns as they drop away, all the way down to 1.
5. Delete cards until only **2** are left. Make the window wide. Switch `auto-fit` to `auto-fill` and back, and compare.
6. Put the cards back to 8. At the bottom of the page, add a `<p>` with one sentence explaining what `minmax(200px, 1fr)` is doing.

## Requirements

- [ ] One `grid-template-columns` declaration controls the column count at every width
- [ ] No `@media` anywhere in the file
- [ ] You compared `auto-fit` and `auto-fill` with only 2 cards on a wide window
- [ ] A one-sentence explanation of `minmax(200px, 1fr)` on the page

## Acceptance criteria

- With 8 cards, the grid goes from 4 or more columns on a wide window down to 1 column on a narrow one, and the cards always fill the row edge to edge.
- At 375px wide there is no horizontal scrollbar.
- You can say which of `auto-fit` / `auto-fill` stretched the 2 cards across the whole row, and which kept them card-sized.

## Hints

<details><summary>Show hint</summary>

Read it from the inside out. `minmax(200px, 1fr)`: each column is never narrower than 200px and never wider than one equal share. `repeat(auto-fit, ...)`: make as many of those columns as will fit.
</details>
