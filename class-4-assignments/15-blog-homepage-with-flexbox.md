# Assignment 15 — Rebuild the Blog Homepage With Flexbox

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1 hr · 🧵 keep this file
**Prereqs:** Class 3 Assignment 15 (styled blog homepage) done
**Build in:** `work/15-blog-homepage-with-flexbox/index.html` + `style.css`

---

## Goal

Take your Class 3 blog homepage — styled with box-model layout only — and rebuild its layout with Flexbox, end to end.

## What you'll practice

- Replacing `inline-block` nav links with a real flex row
- A two-column page layout: flexible main content + a fixed-width sidebar
- Turning each article preview into a flex row (thumbnail + text), like the media object pattern

## Instructions

1. Copy your Class 3 blog homepage into `work/15-blog-homepage-with-flexbox/`. Keep the HTML structure; you're changing the CSS.
2. Convert these three things to Flexbox:
   - **Nav:** `.nav-links` becomes `display: flex` with `gap`, replacing any `inline-block` spacing hacks.
   - **Page layout:** wrap `<main>` and `<aside>` in a flex row — `main { flex: 1 }`, `aside { flex: 0 0 280px }`.
   - **Article previews:** each `<article>` becomes a flex row — a thumbnail image (`flex: 0 0 <width>`) beside a text block (`flex: 1`), using the media-object pattern from Assignment 09.
3. Keep the page readable at a normal desktop width — you're not adding responsiveness yet (that's Class 5).

## Requirements

- [ ] Nav links laid out with `display: flex` + `gap` (no `inline-block` remaining)
- [ ] `<main>` and `<aside>` sit side by side, main flexible, aside a fixed width
- [ ] Every article preview is a flex row: thumbnail + text
- [ ] HTML structure is unchanged from the Class 3 version — only layout CSS changed

## Acceptance criteria

- The page looks at least as good as the Class 3 version, and the layout code is noticeably simpler.
- The sidebar stays a fixed width while the main column absorbs any extra window width.
- Every article preview aligns its thumbnail and text consistently, regardless of excerpt length.

## Hints

<details><summary>Show hint</summary>

Do the three conversions **one at a time** and check the page after each — nav first, then the two-column split, then the article previews. Converting everything at once makes it much harder to spot which change broke what.
</details>
