# Assignment 17 — Fluid Type With clamp()

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1 hr
**Prereqs:** Class 5 §10 (relative units and `clamp()`)
**Build in:** `work/17-fluid-type-with-clamp/index.html` + `style.css`

---

## Goal

Build a page whose type scale grows smoothly with the screen — with **zero** media queries for typography — and document the choices you made.

## What you'll practice

- `clamp(MIN, PREFERRED, MAX)` with a `rem + vw` preferred value
- Working out the window width where a clamp stops growing
- Keeping a type scale in order at every width

## Instructions

1. Build an article page: an `<h1>`, a few `<h2>`s and `<h3>`s, several paragraphs, and a `<table>` at the end (Class 2).
2. Give `h1`, `h2`, `h3`, and `p` each a `font-size` with `clamp()`. A starting point:
   ```css
   h1 {
       font-size: clamp(1.75rem, 1rem + 4vw, 3.5rem);
   }
   ```
3. Check every element at 375px, 768px, and 1280px (Elements → Computed → `font-size`). Adjust until the sizes feel right at all three, and `h1` > `h2` > `h3` > `p` holds at every width.
4. For each clamp, work out the window width where it **stops growing** — where the preferred value reaches the max. For the example above: `1rem + 4vw = 3.5rem` → `16px + 4vw = 56px` → `4vw = 40px` → `1vw = 10px` → a window 1000px wide.
5. Fill in the `<table>`: one row per element; columns for min, preferred, max, "stops growing at", and a short "why".
6. One experiment: temporarily set one heading to plain `font-size: 5vw`, then zoom the page to 200% (`Ctrl` and `+`). Does that heading get bigger? Compare with a clamped heading. Then change it back.

## Requirements

- [ ] At least 4 elements sized with `clamp()`
- [ ] Every preferred value includes a `rem` part — never `vw` on its own
- [ ] No media queries for font sizes anywhere in the file
- [ ] A `<table>` in the page with proper `<th>` headers and one row per element
- [ ] The heading order holds at every width from 320px to 1440px

## Acceptance criteria

- Drag the window from narrow to wide: the headings grow smoothly, with no sudden jumps.
- The "stops growing at" widths in your table match what you see in dev tools.
- You can explain why the plain `5vw` heading stayed the same size when you zoomed, while the clamped headings grew.

## Hints

<details><summary>Show hint</summary>

To find where a clamp stops growing, set the preferred value equal to the max and solve for `vw`.

About the zoom test: zooming to 200% draws every CSS pixel twice as big — but it also makes the window half as wide *in CSS pixels*, so `1vw` is half as many pixels. For a size made only of `vw`, the two effects cancel out and the text stays the same size on screen. A `rem` part doesn't shrink like that, so clamped text still grows.
</details>
