# Assignment 04 — Axis Flip

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 4 §4 (the two axes)
**Build in:** `work/04-axis-flip/index.html` + `style.css`

---

## Goal

Prove to yourself that `flex-direction` decides which property controls which axis — the single most important fact in this class.

## What you'll practice

- `flex-direction: row` vs `column`
- That `justify-content` and `align-items` swap which axis they act on when direction flips

## Instructions

1. Build `index.html`: a `<section class="box">` with three child `<p>` boxes (with borders), container `height: 300px; width: 300px`.
2. In `style.css`, make `.box` a flex container with `flex-direction: row`, `justify-content: center`, `align-items: flex-start`.
3. Observe and note where the boxes sit.
4. Change **only** `flex-direction` to `column`. Do not touch `justify-content` or `align-items`.
5. Before looking, **predict** where the boxes will now sit. Then check.
6. Write one sentence: *when direction is `column`, which property now controls vertical positioning — `justify-content` or `align-items`?*

## Requirements

- [ ] Same `justify-content`/`align-items` values used for both the row and column version
- [ ] A written prediction made **before** switching to `column`
- [ ] The one-sentence answer to the question above

## Acceptance criteria

- In `row` mode: boxes are horizontally centred, aligned to the top.
- In `column` mode (same CSS, only `flex-direction` changed): boxes are vertically centred, aligned to the left.
- Your written answer correctly identifies that `justify-content` now controls the vertical axis.

## Hints

<details><summary>Show hint</summary>

`justify-content` always means "main axis", `align-items` always means "cross axis" — full stop. What changes is *which physical direction* each axis points, and that's entirely down to `flex-direction`.
</details>
