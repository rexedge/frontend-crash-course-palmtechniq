# Assignment 06 — gap vs margin

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 4 §8 (gap)
**Build in:** `work/06-gap-vs-margin/index.html` + `style.css`

---

## Goal

Space out a row of cards two ways — with `gap`, and with `margin` — and feel why `gap` wins.

## What you'll practice

- `gap` on a flex container
- The "extra margin on the last child" annoyance that `gap` avoids

## Instructions

1. Build `index.html` with **two** identical rows of 4 cards each (`<section class="row row-gap">` and `<section class="row row-margin">`), each card a `<p>` with a `border` and some `padding`.
2. Make both rows `display: flex`.
3. On `.row-gap`, space the cards with `gap: 20px`.
4. On `.row-margin`, instead give every card `margin-right: 20px`.
5. Look closely at the right edge of both rows. Note what's different.
6. Write one sentence describing the problem with the margin approach, and how you'd normally have to fix it (hint: `:last-child`).

## Requirements

- [ ] Two rows, 4 cards each, otherwise identical
- [ ] One uses `gap`, the other uses `margin-right` on every card
- [ ] Written note on the difference

## Acceptance criteria

- The `gap` row has even spacing with no extra space after the last card.
- The `margin` row has a visible extra 20px hanging off the right edge, past the last card.
- Your note identifies that fix as needing an extra rule to zero out the last child's margin — work `gap` avoids entirely.

## Hints

<details><summary>Show hint</summary>

The fix for the margin row would be `.row-margin p:last-child { margin-right: 0; }`. It works, but it's one more rule to remember every single time — which is exactly why `gap` is preferred.
</details>
