# Assignment 10 — Colour Palette Page

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 3 §5 (grouping selectors), §7 (colours)
**Build in:** `work/10-colour-palette-page/index.html` + `style.css`

---

## Goal

Present a 6-colour palette as labelled swatches, and use grouped selectors for the rules that repeat.

## What you'll practice

- `background-color` swatches with readable text on top
- Grouping selectors (`A, B, C { … }`) for shared rules
- Choosing text `color` for contrast against each swatch

## Instructions

1. Pick or invent a 6-colour palette (a brand palette, or 6 colours you like).
2. Build `index.html`: an `<h1>`, an intro `<p>`, then six `<section>` swatches. Each swatch contains its hex value and its `rgb()` equivalent as text.
3. In `style.css`:
   - one **grouped** rule for what all six swatches share (`height`, `padding`, `margin-bottom`, base `font`), e.g. `.swatch { … }` or `section { … }`
   - one rule per swatch setting its `background-color` and a readable text `color`
4. Add a class like `.dark-text` / `.light-text` and apply whichever each swatch needs — don't repeat the `color` declaration six times if a shared class will do.

## Requirements

- [ ] 6 swatches, each showing its own hex + rgb values as text
- [ ] Shared swatch styles written **once** via a grouped/single selector, not copied 6 times
- [ ] Text is readable on every swatch (no low-contrast combos)
- [ ] `<h1>` + intro `<p>` above the swatches

## Acceptance criteria

- Changing the shared padding/height means editing **one** rule, not six.
- Every value shown as text matches the actual `background-color` applied.
- All six labels are comfortably readable.

## Hints

<details><summary>Show hint</summary>

Rough contrast rule of thumb: use dark text on light/bright backgrounds, light text on dark/saturated ones. If you're unsure, dev tools shows a contrast ratio when you edit a `color` value in the Styles panel.
</details>
