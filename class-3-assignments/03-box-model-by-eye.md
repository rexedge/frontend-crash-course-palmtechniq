# Assignment 03 — Box Model By Eye

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 3 §6 (the box model)
**Build in:** `work/03-box-model-by-eye/index.html` + `style.css`

---

## Goal

See the difference between padding, border, and margin with your own eyes, using the dev tools box-model diagram.

## What you'll practice

- Reading the dev tools box model (content / padding / border / margin)
- Feeling the difference between *space inside the border* and *space outside it*

## Instructions

1. Build `index.html` with three `<p>` elements, each with some text. Give all three a visible `border` so you can see their edges (e.g. `border: 1px solid #999`).
2. In `style.css`, add classes so that:
   - the **first** `<p>` also has `padding: 20px`
   - the **second** `<p>` also has `margin: 40px`
   - the **third** `<p>` has `border: 4px solid crimson` (a thick, obvious border)
3. Open dev tools (Inspect). Hover each `<p>` in the Elements panel — the browser highlights content (blue), padding (green), border (yellow), margin (orange) on the page. Look at the box-model diagram in the Styles/Computed panel for each.
4. In the HTML, under the three paragraphs, add one more `<p>` with a written sentence: **what visibly differs between the padding on box 1 and the margin on box 2?**

## Requirements

- [ ] 3 paragraphs, all with a visible border
- [ ] Box 1 has padding, box 2 has margin, box 3 has a thick coloured border
- [ ] A written one-sentence observation comparing padding vs margin

## Acceptance criteria

- Box 1: the border sits away from the text (space *inside*).
- Box 2: the border hugs the text, but the box is pushed away from its neighbours (space *outside*).
- Your sentence correctly names padding as inside-the-border space and margin as outside-the-border space.

## Hints

<details><summary>Show hint</summary>

Background colour fills content **and** padding, but never margin. Add a `background-color` to all three boxes and the padding vs margin difference becomes obvious.
</details>
