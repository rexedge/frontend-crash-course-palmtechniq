# Assignment 05 — Perfect Centring

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 4 §11 (everyday patterns)
**Build in:** `work/05-perfect-centring/index.html` + `style.css`

---

## Goal

Centre a box both horizontally and vertically inside a larger container using exactly three declarations. Memorise this pattern — you will use it in almost every project from now on.

## What you'll practice

- The `display: flex; justify-content: center; align-items: center;` combo
- That this works regardless of the sizes of either box

## Instructions

1. Build `index.html`: an outer `<section class="stage">` (give it `width: 400px; height: 300px;` and a `border` so you can see its edges), containing one inner `<p class="box">` (`width: 100px; height: 100px;` with a `background-color`).
2. Without Flexbox, the inner box would sit in the top-left corner. Confirm that first.
3. Add exactly **three** declarations to `.stage`: `display: flex`, `justify-content: center`, `align-items: center`.
4. Resize `.stage` and `.box` to different sizes and confirm the inner box stays perfectly centred no matter what.

## Requirements

- [ ] Outer container has a visible border so the centring is easy to judge
- [ ] Centring is achieved with exactly the three declarations named above (no `margin: auto`, no `position`)
- [ ] Verified with at least two different sets of outer/inner sizes

## Acceptance criteria

- The inner box sits dead centre, both horizontally and vertically, at every size you try.
- You can type this three-line pattern from memory without hesitation.

## Hints

<details><summary>Show hint</summary>

This is the same "container controls its children" idea as every other Flexbox property — the three declarations go on the **outer** `.stage`, never on `.box`.
</details>
