# Assignment 12 — Re-theme, Don't Re-structure

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min · 🧵 keep this file
**Prereqs:** Assignment 07 (styled About Me) done
**Build in:** `work/12-re-theme-dont-re-structure/` — `index.html`, `style.css`, `theme-dark.css`

---

## Goal

Prove that structure and style are separate: create a second, totally different look for the same HTML by swapping **only** the stylesheet.

## What you'll practice

- That one HTML file can wear different stylesheets
- Building a dark theme (background/text/accent/font all changed)
- Separation of concerns, made concrete

## Instructions

1. Copy your Assignment 07 `index.html` and `style.css` into this folder. Confirm it still looks right (this is your "light" theme).
2. Create `theme-dark.css` — a **complete alternative** stylesheet for the *same* HTML:
   - dark page `background-color`, light text `color`
   - a different accent colour for links/headers
   - a different `font-family`
   - keep the same layout numbers (max-width, spacing) so only the *look* changes
3. Switch themes by editing **one line** in the HTML — point the `<link>` at `style.css` or `theme-dark.css`. Do **not** edit the HTML structure otherwise.
4. Take a screenshot (or note) of both looks side by side.

## Requirements

- [ ] `index.html` is identical in structure to your Assignment 07 page (only the `<link>` `href` changes)
- [ ] `theme-dark.css` restyles background, text, accent, and font
- [ ] Layout/spacing stays consistent between the two themes
- [ ] Swapping themes is a one-line change

## Acceptance criteria

- Loading with each stylesheet gives two clearly different-looking pages from **one** HTML file.
- Diffing the two runs of the HTML shows only the `<link href>` value changed.
- Both themes are readable (contrast holds in dark mode too).

## Hints

<details><summary>Show hint</summary>

Build `theme-dark.css` by copying `style.css` and changing only the colour and font declarations — leave every `width`, `margin`, `padding`, and `font-size` alone. That's what makes it a *re-theme*, not a rebuild.
</details>
