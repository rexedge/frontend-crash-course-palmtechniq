# Assignment 03 — align-items Tour

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 4 §6 (align-items and align-self)
**Build in:** `work/03-align-items-tour/index.html` + `style.css`

---

## Goal

Cycle through every `align-items` value on a tall container with unevenly-sized items, and find out which value is the (surprising) default.

## What you'll practice

- `align-items` acting on the **cross axis**
- That the default is `stretch`, not `flex-start`
- `baseline` alignment, which nothing else in the course looks like

## Instructions

1. Build `index.html`: a `<section class="row">` with `height: 200px`, containing three `<p>` boxes with **different** amounts of text (so they'd naturally be different heights) and a visible `border` on each so you can see their edges.
2. Make `.row` a flex container.
3. Try each `align-items` value in turn, checking the result each time: `stretch`, `flex-start`, `center`, `flex-end`, `baseline`.
4. At the bottom of the page, write one `<p>` noting: **which value made all three boxes the same height, and why.**

## Requirements

- [ ] Container has an explicit `height` taller than its content
- [ ] Three boxes of visibly different natural heights, each with a border
- [ ] All five `align-items` values tried (keep the last one you land on, or make five labelled copies like Assignment 02)
- [ ] Written note answering the "which value stretches them" question

## Acceptance criteria

- `stretch` makes all three boxes fill the full 200px height.
- `flex-start` / `center` / `flex-end` visibly shift the (now different-height) boxes to the top / middle / bottom.
- Your note correctly names `stretch` as the default and explains it's why flex children often come out "full height" unexpectedly.

## Hints

<details><summary>Show hint</summary>

`baseline` aligns items by the baseline of their **text**, not their box edges — it only looks meaningfully different from the others when the boxes have different font sizes or padding at the top.
</details>
