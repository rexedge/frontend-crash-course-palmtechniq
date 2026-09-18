# Assignment 10 — Button / Toolbar Group

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~20 min
**Prereqs:** Class 4 §11 (push-to-the-end pattern)
**Build in:** `work/10-button-toolbar-group/index.html` + `style.css`

---

## Goal

Build a toolbar of buttons, left-aligned, with one "danger" button pushed to the far right using `margin-left: auto`.

## What you'll practice

- `align-items: center` for a row of differently-sized elements
- The `margin-left: auto` push-to-the-end trick, applied to a **real** sibling rather than a spacer

## Instructions

1. Build `index.html`: a `<div class="toolbar">` with 5 `<button>` elements — "Bold", "Italic", "Underline", "Link", and "Delete" — the first four left-aligned as a group, "Delete" needing to end up on the far right.
2. In `style.css`:
   - `.toolbar`: `display: flex`, `align-items: center`, `gap`, `padding`, a `background-color`
   - The **Delete** button: `margin-left: auto`
   - Give every button consistent `padding` so they all look the same size (before the push)

## Requirements

- [ ] 5 real `<button>` elements, no empty spacer elements
- [ ] First four sit together on the left with even `gap`
- [ ] "Delete" sits pinned to the far right edge of the toolbar
- [ ] All buttons vertically centred and consistently padded

## Acceptance criteria

- Resizing the toolbar wider keeps "Delete" glued to the right edge; the other four stay together on the left.
- Removing `margin-left: auto` from Delete (try it) makes it sit right after "Link" instead — showing exactly what that declaration does.

## Hints

<details><summary>Show hint</summary>

`margin-left: auto` on **one** flex item eats all the leftover space to its left. Every item after it (if there were more) would be pushed along with it — there's nothing special about it being the *last* item, just that it's the one with the `auto` margin.
</details>
