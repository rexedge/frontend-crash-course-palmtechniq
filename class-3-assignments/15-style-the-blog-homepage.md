# Assignment 15 — Style the Blog Homepage

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1 hr · 🧵 keep this file
**Prereqs:** Class 2 Assignment 08 (blog homepage) done; Class 3 §5–13
**Build in:** `work/15-style-blog-homepage/index.html` + `style.css`

---

## Goal

A full CSS pass over your Class 2 blog homepage — a bigger page than About Me, still laid out with the box model only.

## What you'll practice

- Applying a **spacing scale** consistently across a whole page
- `display: inline-block` to lay nav links in a row (no Flexbox yet)
- Separators via `border`, visual grouping via `background`/`padding`

## Instructions

1. Copy your Class 2 blog homepage into `work/15-style-blog-homepage/index.html`. Add the `<link>`. HTML structure otherwise unchanged.
2. Style it in `style.css`:
   - `box-sizing` reset; `body` font/colour/background
   - a centred content column (`max-width` + `margin: 0 auto`)
   - `<header>` + `<nav>`: nav links as `display: inline-block` with padding and spacing, sitting in a row
   - each `<article>` preview: `padding`, and a **bottom `border`** as a separator between previews
   - the `<aside>`: visually distinct (its own `background-color` or `border` + `padding`)
   - `<footer>`: styled to match the header
3. **Spacing scale:** choose three values (e.g. `8px / 16px / 32px`) and use **only** those for every margin and padding on the page.

## Requirements

- [ ] External `style.css` only; HTML structure unchanged
- [ ] Nav links sit in a horizontal row via `inline-block` (no Flexbox/Grid)
- [ ] Article previews are separated by a border, not just whitespace
- [ ] The `<aside>` is clearly a different region
- [ ] Every margin/padding value on the page is one of your three scale values

## Acceptance criteria

- The page reads as a designed blog front page: clear header, scannable post list, distinct sidebar, tidy footer.
- Searching your CSS for `margin` and `padding` values turns up only the three numbers in your scale.
- No horizontal scrollbar at normal widths.

## Hints

<details><summary>Show hint</summary>

Without Flexbox, a row of nav links = each `<a>` set to `display: inline-block` with `padding` and a small `margin-right`. The parent `<li>`s (if the nav uses a list) also need `display: inline-block` and `list-style: none`.
</details>
