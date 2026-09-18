# Assignment 09 — Media Object

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~25 min
**Prereqs:** Class 4 §9 (flex-basis/flex-grow)
**Build in:** `work/09-media-object/index.html` + `style.css`

---

## Goal

Build the classic "fixed-width image, flexible text beside it" pattern — the basis of comment lists, reviews, and article previews everywhere.

## What you'll practice

- A fixed-size item (`flex: 0 0 <width>`) next to a flexible one (`flex: 1`)
- Top-aligning items instead of centring them
- Repeating a component three times consistently

## Instructions

1. Build `index.html` with **three** stacked "media objects" (think: a mini reviews list), each:
   ```html
   <article class="media">
       <img src="https://picsum.photos/80" alt="Reviewer avatar" class="media-img">
       <div class="media-body">
           <h3>Reviewer Name</h3>
           <p>Their review text — make each one a different length.</p>
       </div>
   </article>
   ```
2. In `style.css`:
   - `.media`: `display: flex`, `gap`, `align-items: flex-start` (top-aligned, not centred — that's what makes it read like a comment list)
   - `.media-img`: a fixed size (e.g. `flex: 0 0 80px`, `width: 80px`, matching `height`)
   - `.media-body`: `flex: 1` to take the rest of the space

## Requirements

- [ ] Three media objects stacked vertically, each its own flex row
- [ ] Each image is a fixed size and never shrinks or grows
- [ ] Each text block fills the remaining width and top-aligns with the image
- [ ] Review text lengths differ across the three, and the layout still looks correct for all of them

## Acceptance criteria

- All three images are exactly the same size regardless of surrounding text length.
- Text starts at the same vertical position as the top of its image (not vertically centred against it).
- Text never overlaps or squeezes the image.

## Hints

<details><summary>Show hint</summary>

`flex: 0 0 80px` means "never grow, never shrink, always 80px" — the safest way to guarantee an image never gets crushed by its flexible sibling.
</details>
