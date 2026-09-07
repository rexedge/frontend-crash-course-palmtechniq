# Assignment 05 — Type Scale

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 3 §8 (typography)
**Build in:** `work/05-type-scale/index.html` + `style.css`

---

## Goal

Set a small, deliberate set of text sizes on `body`, `h1`, `h2`, `h3`, `p`, and a `.small` class, and tune it until it looks balanced.

## What you'll practice

- Setting `font-family`, `font-size`, `line-height` once on `body` and letting it inherit
- A **type scale** — stepped sizes that look designed, not random
- `rem` units for font sizes

## Instructions

1. Build `index.html` with an `<h1>`, a couple of `<h2>` and `<h3>`, several real paragraphs of text, and one `<p class="small">` (a caption or footnote).
2. In `style.css`:
   ```css
   body { font-family: system-ui, Arial, sans-serif; font-size: 16px; line-height: 1.6; color: #222; }
   h1 { font-size: 2.5rem; }
   h2 { font-size: 2rem; }
   h3 { font-size: 1.5rem; }
   p  { font-size: 1rem; }
   .small { font-size: 0.85rem; }
   ```
3. Look at it in the browser. Adjust the numbers until the steps *feel* right — headings clearly ranked, body comfortable to read, `.small` clearly secondary. Note what you changed and why.

## Requirements

- [ ] `body` sets `font-family`, `font-size`, and `line-height`
- [ ] `h1`/`h2`/`h3`/`p`/`.small` each have a `font-size` in `rem`
- [ ] The sizes form a clear ladder (each heading noticeably different from the next)
- [ ] A short written note on any adjustments you made

## Acceptance criteria

- Nothing inherits a random size — every text element's size is intentional.
- `1rem` = 16px (your `body` base), `2rem` = 32px, etc. Confirm one in dev tools → Computed.
- The page reads as a coherent document, not a ransom note.

## Hints

<details><summary>Show hint</summary>

`line-height` with **no unit** (`1.6`, not `1.6px` or `160%`) is best — it multiplies each element's own font size, so headings and body both get proportional spacing.
</details>
