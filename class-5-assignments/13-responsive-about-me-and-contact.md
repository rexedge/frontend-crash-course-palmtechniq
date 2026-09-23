# Assignment 13 — Make About Me + Contact Responsive

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~1 hr · 🧵 keep this file
**Prereqs:** Class 3 Assignment 07 and Class 4 Assignment 13 done; Class 5 §9–14
**Build in:** `work/13-responsive-about-me-and-contact/about-me/` and `.../contact/` (each `index.html` + `style.css`)

---

## Goal

Take the two pages you've been building since Class 1 and make them work properly from a phone up to a desktop. This is the **Class 5 homework**.

## What you'll practice

- Adding responsiveness to a page that already exists
- The viewport tag, the `img` reset, and fluid padding with `clamp()`
- Mobile-first media queries for a 2-column section and a 2-column form

## Instructions

1. Copy both pages in — [work/README.md](work/README.md) lists the exact folders.
2. **Both pages:**
   - Add the viewport tag to the `<head>`.
   - Add the `img` reset near the top of the stylesheet: `img { max-width: 100%; height: auto; display: block; }`.
   - Give the main content column a `max-width` (you probably have one from Class 3) and fluid side padding: `padding: 0 clamp(16px, 5vw, 48px)`.
3. **About Me:** pick two content sections (e.g. "Things I Like" and "Goals"). Wrap them in one `<div class="two-col">` — the only HTML change allowed besides the viewport tag. Then, mobile-first:
   - base: `.two-col` is `display: grid` with a `gap` (one column, so they stack)
   - `@media (min-width: 640px)`: `.two-col` gets `grid-template-columns: 1fr 1fr`
   - If your `<main>` is narrow (e.g. `max-width: 700px`), consider widening it so the two columns have room.
4. **Contact:** your fields are laid out with Flexbox from Class 4. Make them one column on phones and two from 640px. Choose **one** approach:
   - **Keep Flexbox.** In the base styles, every field is full width (`.field-half { flex: 1 1 100%; }`). Inside `@media (min-width: 640px)`, `.field-half` goes back to `flex: 1 1 45%`.
   - **Switch to Grid.** The fields' container becomes `display: grid` with a `gap` (one column). Inside `@media (min-width: 640px)`, it gets `grid-template-columns: 1fr 1fr`, and the full-width fields get `grid-column: 1 / -1`.
5. Test both pages at 375px, 768px, and 1280px.

## Requirements

- [ ] The viewport tag on both pages
- [ ] The `img` reset on both pages — no image is ever wider than the screen
- [ ] Fluid side padding with `clamp()` on both pages
- [ ] About Me: the two sections stack on phones and sit side by side from 640px
- [ ] Contact: one column of fields on phones; Name and Email side by side from 640px; Subject and Message always full width
- [ ] Every media query is `min-width` (mobile-first)
- [ ] The form's fields, labels, and validation attributes are unchanged

## Acceptance criteria

- 375px: both pages are a single, readable column with normal-sized text and no horizontal scrollbar.
- 768px and 1280px: the two-column parts appear, and nothing overlaps.
- The contact form still validates exactly as before — try submitting it empty.

## Hints

<details><summary>Show hint</summary>

If a page still scrolls sideways on a phone, find the culprit: in the Elements panel, hover over elements until you find the one that sticks out past the right edge. It's usually an image without `max-width: 100%`, or a fixed `width` in `px` left over from Class 3.
</details>

## Stretch (optional)

Make the headings on both pages fluid with `clamp()` (Class 5 §10), so they scale smoothly between phone and desktop.
