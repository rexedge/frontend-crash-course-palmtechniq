# Assignment 02 — justify-content Tour

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 4 §5 (justify-content)
**Build in:** `work/02-justify-content-tour/index.html` + `style.css`

---

## Goal

See all six `justify-content` values side by side and learn to tell them apart on sight.

## What you'll practice

- `justify-content` acting on the **main axis**
- The visual difference between `space-between`, `space-around`, and `space-evenly` — the three everyone mixes up

## Instructions

1. Build `index.html` with **five** copies of the same row: a `<section class="row">` containing 3 small coloured boxes (`<p>` with a `background-color` works fine).
2. Give each copy its own class (`.row-1` … `.row-5`), and label it with an `<h3>` above it.
3. In `style.css`, make every `.row-N` a flex container, then set a **different** `justify-content` on each: `flex-start`, `flex-end`, `center`, `space-between`, `space-around`. Label each `<h3>` with the value it demonstrates.
4. *(Bonus)* add a sixth row for `space-evenly` and compare it to `space-around`.

## Requirements

- [ ] 5 (or 6) labelled rows, each a flex container with 3 boxes
- [ ] Each row demonstrates a different `justify-content` value, correctly labelled
- [ ] Boxes are wide enough and the row wide enough that the spacing differences are actually visible

## Acceptance criteria

- You can point at any row and correctly name its `justify-content` value without checking the CSS.
- `space-between` clearly has no gap at the outer edges; `space-around`/`space-evenly` clearly do.

## Hints

<details><summary>Show hint</summary>

If all the boxes look bunched together, your row isn't wide enough relative to the boxes for the spacing values to show a difference. Give the row a wider `width` or the boxes a smaller one.
</details>
