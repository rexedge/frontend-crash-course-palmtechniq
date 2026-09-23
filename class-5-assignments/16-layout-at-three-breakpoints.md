# Assignment 16 — Reproduce a Layout at Three Breakpoints

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1.5 hr · 🧵 keep this file
**Prereqs:** all of Class 5; Class 4 Assignments 07 (navbar) and 08 (feature cards)
**Build in:** `work/16-layout-at-three-breakpoints/index.html` + `style.css`

---

## Goal

Build a simple landing page that deliberately changes its layout at three sizes — phone, tablet, desktop — using Grid, Flexbox, and mobile-first media queries together.

## What you'll practice

- Planning breakpoints on paper before writing CSS
- A Flexbox navbar and a Grid feature section on the same page
- Stacking two `min-width` queries

## The page

Make up a product, a club, or a small business. The page has:
- a `<header>` with a brand name and a `<nav>` of 4 links
- a hero `<section>`: a heading, a sentence, a call-to-action link styled as a button, and an image
- a features `<section>` with 6 feature cards (an emoji "icon", an `<h3>`, a `<p>`)
- a `<footer>`

## The three layouts

Sketch all three on paper first.

| Size | Nav | Hero | Features |
|---|---|---|---|
| **Phone** — base styles, no query | brand on top; links stacked in a vertical list underneath | one column; text centred; image below the text | 1 column |
| **Tablet** — `@media (min-width: 640px)` | brand left, links in a row on the right | still one column | 2 columns |
| **Desktop** — `@media (min-width: 1024px)` | same as tablet | text and image **side by side** | 3 columns |

On desktop, the whole page sits inside a centred container with a `max-width` (e.g. `72rem`).

## Requirements

- [ ] The viewport tag, the `box-sizing` reset, and the `img` reset
- [ ] Base styles = the phone layout, with no media query
- [ ] Exactly two queries: `min-width: 640px`, then `min-width: 1024px`
- [ ] Nav: Flexbox — a column on phones, a row from 640px
- [ ] Features: Grid, with an explicit column count at each size (1 → 2 → 3)
- [ ] Hero: Grid or Flexbox, your choice — one column until 1024px, two after
- [ ] Headings sized with `clamp()`

## Acceptance criteria

- Drag the window from 320px to 1440px: the layout changes exactly twice, at 640px and 1024px, and looks intentional at every width in between.
- No horizontal scrollbar at any width.
- A comment at the top of `style.css` lists your two breakpoints and what changes at each.

## Hints

<details><summary>Show hint</summary>

Finish the phone layout completely first — colours, type, spacing — before you type `@media`. Most of the page needs no changes at bigger sizes; only the nav, the hero, and the features grid do.
</details>

## Stretch (optional)

Replace the features' three explicit column counts with one `repeat(auto-fit, minmax(...))` line. Can you pick a minimum that gives 1, 2, and 3 columns at roughly the right widths? What do you gain, and what do you lose?
