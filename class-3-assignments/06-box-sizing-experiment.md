# Assignment 06 — box-sizing Experiment

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 3 §6 (the box model — `box-sizing`)
**Build in:** `work/06-box-sizing-experiment/index.html` + `style.css`

---

## Goal

Prove to yourself exactly what `box-sizing: border-box` changes, by measuring two otherwise-identical boxes.

## What you'll practice

- `content-box` (default) vs `border-box`
- That `width` + `padding` + `border` overflow with `content-box`
- Measuring elements in dev tools

## Instructions

1. Build `index.html` with two `<section>` elements, each containing a line of text.
2. In `style.css`, give **both** the same rules:
   ```css
   section { width: 300px; padding: 40px; border: 10px solid black; margin-bottom: 20px; }
   ```
3. Add **one** extra rule that gives only the second section `box-sizing: border-box` (use a class or `section:last-of-type`).
4. Open dev tools, select each section, read its **rendered width** on screen (the box-model diagram, or Computed → width including the "box" total).
5. In the HTML, add a `<p>` recording: the total on-screen width of box 1, the total of box 2, and one sentence explaining the difference.

## Requirements

- [ ] Both sections share identical `width` / `padding` / `border`
- [ ] Only the second has `box-sizing: border-box`
- [ ] Written record of both rendered widths + a one-sentence explanation

## Acceptance criteria

- Box 1 (`content-box`) renders **400px** wide (300 + 40 + 40 + 10 + 10).
- Box 2 (`border-box`) renders **300px** wide — the padding and border eat inward, the content area shrinks.
- Your explanation says `border-box` makes `width` include padding + border.

## Hints

<details><summary>Show hint</summary>

This is why most stylesheets start with `*, *::before, *::after { box-sizing: border-box; }` — so `width` means what you expect everywhere. Try adding that rule and watch box 1 snap to 300px too.
</details>
