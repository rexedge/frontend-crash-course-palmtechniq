# Assignment 11 — Pricing Table

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min · 🧵 keep this file
**Prereqs:** Assignment 08 (three-card feature row) done
**Build in:** `work/11-pricing-table/index.html` + `style.css`

---

## Goal

Build a 3-plan pricing table, equal height, with the middle plan visually "featured" — a very common real-world layout built entirely from what you now know.

## What you'll practice

- Reusing the equal-width-cards + pinned-bottom-button pattern from Assignment 08
- Making one flex child look different from its siblings without breaking the row

## Instructions

1. Build `index.html` with three `<article class="plan">` elements inside a `<section class="pricing">`. Each plan: a title (`<h3>`), a big price (`<p class="price">`), a `<ul>` of 4–5 features, and a call-to-action `<button>` or `<a>`.
2. Mark the middle plan with an extra class: `<article class="plan plan-featured">`.
3. In `style.css`:
   - `.pricing`: `display: flex`, `gap`, `align-items: stretch` (or leave it — that's the default)
   - `.plan`: `flex: 1`, `display: flex`, `flex-direction: column`, `padding`, `border`
   - the CTA button/link: `margin-top: auto`
   - `.plan-featured`: a different `background-color` and/or extra `padding` (making it visually "lifted"), maybe a slightly larger `flex` value

## Requirements

- [ ] 3 plans, all equal height regardless of feature-list length
- [ ] Middle plan visually distinct (colour, size, or elevation — your choice)
- [ ] Every plan's CTA lines up at the same vertical position
- [ ] `<ul>` used correctly for the feature list

## Acceptance criteria

- All three plans start and end at the same vertical position (same total height).
- The middle plan is unmistakably the "recommended" one at a glance.
- The layout survives adding or removing a feature from one plan's list without breaking alignment.

## Hints

<details><summary>Show hint</summary>

This is Assignment 08's exact recipe (`flex: 1` + `flex-direction: column` + `margin-top: auto`) with pricing content and one card singled out with an extra class. If you're stuck, revisit 08 first.
</details>
