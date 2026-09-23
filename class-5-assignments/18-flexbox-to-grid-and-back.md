# Assignment 18 — Convert Flexbox to Grid (and Back)

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1 hr
**Prereqs:** Class 5 §7; Class 4 Assignment 11 (pricing table) and Class 5 Assignment 08 (gallery) done
**Build in:** `work/18-flexbox-to-grid-and-back/pricing-grid/` and `.../gallery-flex/` (each `index.html` + `style.css`)

---

## Goal

Rebuild a Flexbox layout with Grid, and a Grid layout with Flexbox. Feeling where each tool fights you is the fastest way to learn which one to reach for.

## What you'll practice

- Translating a layout between the two systems
- Spotting which one needs less CSS for which job

## Instructions

**Part A — Pricing table: Flexbox → Grid**
1. Copy your Class 4 pricing table in (see [work/README.md](work/README.md)).
2. Replace the Flexbox on the plans' container with Grid: three equal columns and a `gap`. Keep the middle plan visually "featured".
3. Keep each plan's button pinned to the bottom. Each plan can stay a Flexbox column with `margin-top: auto` on the button — Grid on the outside, Flexbox on the inside is perfectly normal.
4. Make it responsive, mobile-first: one column on phones, three from a breakpoint you choose.

**Part B — Gallery: Grid → Flexbox**
1. Copy your Assignment 08 gallery in.
2. Rebuild `.gallery` with `display: flex`, `flex-wrap: wrap`, and `gap` — no Grid anywhere.
3. Try to get the same behaviour: tiles at least 220px wide that fill each row, and one column on a phone. (Hint: `flex: 1 1 220px` on each image.)
4. Look closely at the **last row** and at the featured photo. What happened?

## Requirements

- [ ] Part A uses Grid for the three plans; plans are equal height, and their buttons line up
- [ ] Part A is one column on phones (mobile-first)
- [ ] Part B uses no Grid at all
- [ ] Three sentences in a `notes.md` (or a comment): which conversion felt natural, which fought you, and why

## Acceptance criteria

- Part A: at desktop width it looks the same as your Class 4 version, or better.
- Part B: you can point at exactly what Flexbox couldn't do as neatly — lining up the last row with the rows above, and covering two rows at once.

## Hints

<details><summary>Show hint</summary>

Grid plans are equal height for free: by default every item in a grid row stretches to the height of that row — just like Flexbox's `align-items: stretch`.
</details>
