# Assignment 09 — Business Card (Exact Spec)

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 3 §6 (box model), §8 (typography)
**Build in:** `work/09-business-card/index.html` + `style.css`

---

## Goal

Build one "business card" component to an exact numeric spec — box-model precision practice.

## What you'll practice

- Hitting precise `width` / `padding` / `border` / `margin` values
- `text-transform`, a `.muted` helper class, a divider made from `border-top`
- Confirming a rendered size in dev tools

## Instructions

Build a single card. Match these numbers exactly:

**Outer card**
- `width: 350px`
- `padding: 24px`
- `border: 1px solid #ddd`
- `margin: 40px auto` (centres it on the page)
- `background: #fff`
- (page `background-color`: something not white, so the card stands out)

**Inside the card**
- a name — `<h2>`, `font-size: 1.4rem`, `margin-top: 0` (kill the default)
- a role — `<p class="muted">`, a grey `color`, `text-transform: uppercase`, small `letter-spacing`
- a divider — an empty element or a `<p>` with `border-top: 1px solid #eee` and `margin` above and below
- three contact lines — `<p>` each (email, phone, website)

## Requirements

- [ ] Every value above matches exactly
- [ ] `.muted` is a reusable class (grey, used on the role line)
- [ ] The divider is a real horizontal line drawn with `border-top`, not a dash of text
- [ ] `<h2>` has no space above it inside the card

## Acceptance criteria

- Inspect the card in dev tools: its **total rendered width is exactly 350px** (so `box-sizing: border-box` is in play — 350 including the 24px padding and 1px border).
- The card is horizontally centred on the page.
- The role line is uppercase and visibly lighter than the name.

## Hints

<details><summary>Show hint</summary>

`margin: 40px auto` = 40px top and bottom, `auto` left and right. `auto` side margins only centre an element that has a set `width` — which this card does (350px).
</details>
