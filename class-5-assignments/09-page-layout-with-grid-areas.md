# Assignment 09 — Page Layout With grid-template-areas

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min · 🧵 keep this file
**Prereqs:** Class 5 §5, §13–14 (named areas, media queries, mobile-first)
**Build in:** `work/09-page-layout-with-grid-areas/index.html` + `style.css`

---

## Goal

Build a complete page skeleton — header, sidebar nav, main content, footer — with named grid areas, mobile-first: stacked on a phone, sidebar beside the content from 768px up.

## What you'll practice

- `grid-template-areas` for a whole page
- Redrawing the map inside a media query, instead of changing the HTML
- Writing the phone layout first, then adding the wide layout with `min-width`
- Flexbox inside a Grid area: the nav links

## Instructions

1. Build `index.html` with a wrapper `<div class="page">` containing:
   - `<header class="header">` — your site name in an `<h1>`
   - `<nav class="sidebar">` — 4–5 links
   - `<main class="content">` — an `<h2>` and at least three paragraphs
   - `<footer class="footer">` — a short line of text
2. In `style.css`, write the **phone layout first**, with no media query:
   - `.page`: `display: grid`, a `gap`, and a one-column map:
     ```css
     grid-template-areas:
         "header"
         "sidebar"
         "content"
         "footer";
     ```
   - `grid-area` on each of the four landmarks
   - `.sidebar`: `display: flex`, `flex-wrap: wrap`, and a `gap` — so on a phone the links sit in a row across the top and wrap if they need to
3. Then add **one** query, `@media (min-width: 768px)`, that:
   - gives `.page` `grid-template-columns: 220px 1fr`
   - redraws the map as `"header header"`, `"sidebar content"`, `"footer footer"`
   - turns `.sidebar` into a column with `flex-direction: column`
4. Give each area a `background-color` and `padding` so the layout is easy to see. Test at 375px, 768px, and 1280px.

## Requirements

- [ ] The base (phone) styles use **no** media query; the wide layout lives in one `min-width: 768px` query
- [ ] The HTML is the same at every width — only the map changes
- [ ] Phone: all four areas stacked, nav links in a wrapping row
- [ ] 768px and up: header and footer full width, a 220px sidebar beside the content, nav links stacked
- [ ] The viewport tag is in the `<head>`

## Acceptance criteria

- Drag the window across 768px: the sidebar jumps from above the content to beside it, and nothing else changes.
- No horizontal scrollbar at 375px.
- No `max-width` queries anywhere in this file.

## Hints

<details><summary>Show hint</summary>

The phone layout doesn't need `grid-template-columns` at all — with a one-column map, the grid has a single column that fills the width. The media query adds the second column and redraws the map in the same rule.
</details>

## Stretch (optional)

Keep the footer at the bottom of the window on short pages. Inside the 768px query, give `.page` `min-height: 100vh` and `grid-template-rows: auto 1fr auto`, so the middle row takes all the spare height.
