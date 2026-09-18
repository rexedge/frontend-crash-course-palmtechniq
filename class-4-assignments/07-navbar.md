# Assignment 07 — Navbar

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min · 🧵 keep this file
**Prereqs:** Class 4 §5, §6, §8, §12 (guided practice)
**Build in:** `work/07-navbar/index.html` + `style.css`

---

## Goal

Build the classic site navbar — brand on the left, links on the right, everything vertically centred — using Flexbox. This is half of the Class 4 hands-on.

## What you'll practice

- `justify-content: space-between` to push two groups to opposite ends
- Nesting flex containers (the link list is its own flex row, inside the bar)
- `align-items: center` for vertical centring in a bar that's shorter than its content's natural line height

## Instructions

1. Build `index.html`:
   ```html
   <header class="navbar">
       <p class="brand">My Site</p>
       <nav class="nav-links">
           <a href="#">Home</a>
           <a href="#">About</a>
           <a href="#">Work</a>
           <a href="#">Contact</a>
       </nav>
   </header>
   ```
2. In `style.css`:
   - `.navbar`: `display: flex`, `justify-content: space-between`, `align-items: center`, `padding`, a `background-color`
   - `.nav-links`: also `display: flex`, with `gap` between the links
   - Style the brand text and the links (colour, remove link underline) so it reads like a real header

## Requirements

- [ ] `.navbar` is a flex container with `justify-content: space-between`
- [ ] Brand sits at the far left, the link group at the far right
- [ ] `.nav-links` is its **own** nested flex row with `gap` between the 4 links
- [ ] Everything vertically centred via `align-items: center`
- [ ] `padding` and a `background-color` on the bar

## Acceptance criteria

- Resize the browser window — brand stays left, links stay right, at any reasonable width.
- The brand and the links are vertically aligned with each other, not offset.
- No `float`, no `position`, no Grid.

## Hints

<details><summary>Show hint</summary>

You're nesting two flex containers: the outer `.navbar` splits into two groups (brand, nav-links), and the inner `.nav-links` arranges the 4 links among themselves. Each flex container only cares about its own direct children.
</details>

## Stretch (optional)

Give a link a `.active` class and style it differently (e.g. a different `color` or a `border-bottom`) to show which page you're "on".
