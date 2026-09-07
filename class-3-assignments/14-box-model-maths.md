# Assignment 14 — Box-Model Maths

**Type:** Challenge · **Difficulty:** ⭐⭐ · **Time:** ~20 min
**Prereqs:** Class 3 §6 (the box model)
**Build in:** `work/14-box-model-maths/answers.md` + `index.html` (to verify)

---

## Goal

Do the box-model arithmetic **on paper first**, then confirm each answer in the browser.

## What you'll practice

- Computing rendered width under `content-box` vs `border-box`
- Working backwards from a target size to the `width` you must set

## The problems

Write your answers in `answers.md` before touching a browser.

**1.** An element has `width: 200px; padding: 20px; border: 5px solid; margin: 10px`, default `box-sizing`.
   - (a) What is the width of the visible box (content + padding + border)?
   - (b) How much horizontal space does it occupy in total, including margin?

**2.** Same values, but `box-sizing: border-box`.
   - (a) Visible box width?
   - (b) Total horizontal space including margin?

**3.** You want a visible box **exactly 300px wide** with `24px` padding and a `3px` border, using `content-box`. What `width` do you set?

## Verify

Build `index.html` + `style.css` with the three elements described. Inspect each in dev tools and check your paper answers against the box-model diagram.

## Requirements

- [ ] `answers.md` written **before** building anything
- [ ] All three elements built and inspected
- [ ] Any wrong answers corrected in `answers.md` with a note on what you missed

<details><summary>Show answers</summary>

1. `content-box`: visible box = 200 + 20 + 20 + 5 + 5 = **250px**; total with margin = 250 + 10 + 10 = **270px**.
2. `border-box`: visible box = **200px** (padding + border eat inward); total with margin = **220px**.
3. `width` = 300 − 24 − 24 − 3 − 3 = **246px**.
</details>

## Acceptance criteria

- Your paper answers match the browser (or the mismatches are understood and noted).
- You can explain *why* `border-box` gives a different number without re-deriving it.
