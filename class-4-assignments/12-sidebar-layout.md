# Assignment 12 — Sidebar Layout

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 4 §9, §11 (sidebar + main pattern)
**Build in:** `work/12-sidebar-layout/index.html` + `style.css`

---

## Goal

Build a page split into a fixed-width sidebar and a flexible main content area that fills the rest of the screen.

## What you'll practice

- `flex: 0 0 <width>` for a sidebar that never grows or shrinks
- `flex: 1` for the area that takes up everything else
- `min-height: 100vh` so the layout fills the full browser window
- A nested `flex-direction: column` nav inside the sidebar

## Instructions

1. Build `index.html`:
   ```html
   <div class="layout">
       <nav class="sidebar">
           <a href="#">Dashboard</a>
           <a href="#">Projects</a>
           <a href="#">Settings</a>
       </nav>
       <main class="main">
           <h1>Dashboard</h1>
           <p>Main content goes here.</p>
       </main>
   </div>
   ```
2. In `style.css`:
   - `.layout`: `display: flex`, `min-height: 100vh`
   - `.sidebar`: `flex: 0 0 240px`, `display: flex`, `flex-direction: column`, `gap`, `padding`, a `background-color`
   - `.main`: `flex: 1`, `padding`

## Requirements

- [ ] Sidebar is exactly 240px wide at any window size and never shrinks below it
- [ ] Main area fills all remaining width
- [ ] The whole layout is at least the full height of the browser window
- [ ] Sidebar links are stacked vertically with consistent `gap`

## Acceptance criteria

- Resize the window: the sidebar width never changes; only the main area's width changes.
- Scroll down (if content is short, temporarily add a tall `<p>`): the sidebar's background still runs the full height.
- No `float`, `position`, or Grid used.

## Hints

<details><summary>Show hint</summary>

If the sidebar shrinks on a narrow window, its `flex-shrink` is still `1` (the default) even though you set `flex: 0 0 240px`... check you used the shorthand correctly — `flex: 0 0 240px` sets grow, shrink, **and** basis in one go.
</details>
