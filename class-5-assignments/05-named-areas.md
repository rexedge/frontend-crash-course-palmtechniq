# Assignment 05 — Named Areas

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 5 §5 (`grid-template-areas`)
**Build in:** `work/05-named-areas/index.html` + `style.css`

---

## Goal

Draw a page layout as a map of named areas, then rearrange the page by redrawing the map — without touching the HTML.

## What you'll practice

- `grid-template-areas` — one string per row, one word per cell
- `grid-area` to send each element to its area
- The rules: the same number of cells in every row, rectangles only

## Instructions

1. Build `index.html`:
   ```html
   <div class="page">
       <header class="header">
           <h1>My Site</h1>
       </header>
       <nav class="sidebar">
           <a href="#">Home</a>
           <a href="#">About</a>
           <a href="#">Contact</a>
       </nav>
       <main class="content">
           <h2>Welcome</h2>
           <p>Some main content.</p>
       </main>
       <footer class="footer">
           <p>Made by me</p>
       </footer>
   </div>
   ```
2. In `style.css`:
   - `.page`: `display: grid`, `grid-template-columns: 220px 1fr`, a `gap`, and this map:
     ```css
     grid-template-areas:
         "header  header"
         "sidebar content"
         "footer  footer";
     ```
   - `.header { grid-area: header; }` — and the same for `.sidebar`, `.content`, and `.footer`
   - A different `background-color` and some `padding` on each area so you can see it
3. Now rearrange the page three times, one at a time, changing **only** the `grid-template-columns` and `grid-template-areas` lines:
   - the sidebar on the **right**
   - the sidebar running the **full height** of the page, beside the header and the footer too
   - an empty cell (`.`) to the left of the footer, so the footer only sits under the content
4. Break a rule on purpose: delete one word from the last row of the map so it has fewer cells than the others. Save and watch the layout fall apart. Put it back.

## Requirements

- [ ] Four areas placed with `grid-area`, each a different colour
- [ ] All three rearrangements done without editing the HTML
- [ ] You saw what happens when one row has the wrong number of cells

## Acceptance criteria

- In the starting layout, the header and footer cover the full width.
- Each rearrangement changed only the two grid lines on `.page`.
- You can state the two rules the map must follow.

## Hints

<details><summary>Show hint</summary>

For a full-height sidebar, the word `sidebar` appears in the first cell of **every** row: `"sidebar header"`, `"sidebar content"`, `"sidebar footer"`. That's still a rectangle — one column wide, three rows tall.
</details>
