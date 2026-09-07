# Assignment 04 — Colour Formats

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 3 §7 (colours), §9 (backgrounds)
**Build in:** `work/04-colour-formats/index.html` + `style.css`

---

## Goal

Write the same kind of value (a colour) six different ways, and use `rgba()` transparency over a background image.

## What you'll practice

- Named colours, `#hex` (3- and 6-digit), `rgb()`, `rgba()` with alpha
- `background-color` vs `color`, and readable contrast
- `rgba()` letting a background show through

## Instructions

1. Build `index.html` with an `<h1>` and six `<section>` (or `<p>`) blocks.
2. In `style.css`, give each block a different `background-color`, written as:
   - block 1 — a **named** colour
   - block 2 — a 6-digit `#hex`
   - block 3 — a 3-digit `#hex` (e.g. `#0af`)
   - block 4 — an `rgb()` value
   - block 5 — a different `rgb()` value
   - block 6 — an `rgb` colour applied as text `color` over a `background-image` (use `https://picsum.photos/600/200`), plus a semi-transparent `rgba()` `background-color` on top so the text stays readable
3. Put the actual colour value as **text inside each block** (`#e63946`, `rgb(230, 57, 70)`, …). Set each block's text `color` so it's readable against its background.
4. Give the six blocks a fixed `height` and some `padding` so they're easy to see.

## Requirements

- [ ] 6 blocks, 6 colour values, using all of: named, `#hex` (×2, one short), `rgb()` (×2), `rgba()`
- [ ] Block 6 layers an `rgba()` colour over a `background-image` and text is still readable
- [ ] Each block displays its own value as text
- [ ] Text/background contrast is readable on every block

## Acceptance criteria

- All six backgrounds render; none of the text is unreadable (no light grey on white).
- Block 6: you can see the photo *and* read the text because of the `rgba()` layer.

## Hints

<details><summary>Show hint</summary>

The 4th value in `rgba(0, 0, 0, 0.5)` is alpha: `0` = fully transparent, `1` = fully solid. `rgba(255, 255, 255, 0.7)` over a photo gives a frosted-white panel you can put dark text on.
</details>
