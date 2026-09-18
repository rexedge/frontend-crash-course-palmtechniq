# Assignment 08 — Three-Card Feature Row

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~35 min · 🧵 keep this file
**Prereqs:** Class 4 §9, §11, §12 (guided practice)
**Build in:** `work/08-three-card-feature-row/index.html` + `style.css`

---

## Goal

Build three equal-width, equal-height feature cards in a row, each with its "Learn more" link pinned to the bottom regardless of how much text is above it. This is the other half of the Class 4 hands-on.

## What you'll practice

- `flex: 1` for equal-width siblings
- Nesting `flex-direction: column` **inside** each card so `margin-top: auto` can pin the last item
- Combining two different flex containers (the row, and each card) for one layout

## Instructions

1. Build `index.html` with three `<article class="card">` elements inside a `<section class="cards">`. Give the three cards **different amounts of body text** on purpose — that's what makes the "pinned to bottom" behaviour visible.
   ```html
   <article class="card">
       <p class="icon">🚀</p>
       <h3>Fast</h3>
       <p>Short description.</p>
       <a href="#" class="cta">Learn more</a>
   </article>
   ```
2. In `style.css`:
   - `.cards`: `display: flex`, `gap`
   - `.card`: `flex: 1` (equal width), `display: flex`, `flex-direction: column`, `padding`, a `border`
   - `.cta`: `margin-top: auto`

## Requirements

- [ ] Three cards, deliberately different amounts of text in each
- [ ] `.cards` is a flex row with `gap`
- [ ] Every `.card` is `flex: 1` **and** its own `flex-direction: column` container
- [ ] Every `.cta` link sits at the same vertical position across all three cards, via `margin-top: auto`

## Acceptance criteria

- All three cards are exactly the same width and the same height.
- The "Learn more" links line up horizontally with each other, regardless of the differing text length above them.
- Removing `margin-top: auto` (try it, then put it back) makes the links jump to right under the text — proving what that declaration is doing.

## Hints

<details><summary>Show hint</summary>

`margin-top: auto` only pins something to the bottom **inside a column flex container that has a defined height** — here, that height comes from the card being `flex: 1` inside a row where `align-items` defaults to `stretch`, so all cards match the tallest one.
</details>

## Stretch (optional)

Make the middle card visually "featured" (a different `background-color`, or `flex: 1.2` so it's slightly wider than the other two).
