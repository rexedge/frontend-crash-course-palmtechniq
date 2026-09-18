# Assignment 01 — Turn It On

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min (do it 3 times)
**Prereqs:** Class 4 §3 (turning it on)
**Build in:** `work/01-turn-it-on/index.html` + `style.css`

---

## Goal

Turn a vertical stack of elements into a horizontal row with one declaration, from memory, three times.

## What you'll practice

- `display: flex` on a container
- That only **direct children** become flex items
- `gap` for spacing

## Instructions

1. Build `index.html`: a `<section class="row">` containing three `<p>` elements with short text.
2. Confirm they stack one per line (the normal default).
3. In `style.css`, add `display: flex` to `.row`. Watch them line up horizontally.
4. Add `gap: 16px`.
5. Delete your CSS and redo steps 3–4 from memory. Then a third time in a brand new folder.

## Requirements

- [ ] `.row` becomes a flex container with one declaration
- [ ] Three `<p>` elements sit side by side with a visible gap
- [ ] Done 3 times, the third with nothing to refer to

## Acceptance criteria

- Before `display: flex`, the paragraphs stack vertically. After, they sit in a row with even spacing.
- You didn't need to look anything up on the third attempt.

## Hints

<details><summary>Show hint</summary>

`display: flex` only affects the **children** of the element it's applied to — it does nothing to how the container itself behaves among its own siblings.
</details>
