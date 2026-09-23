# Assignment 02 — fr vs px vs auto

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 5 §3 (sizing tracks)
**Build in:** `work/02-fr-vs-px-vs-auto/index.html` + `style.css`

---

## Goal

See, one under another, how fixed (`px`), flexible (`fr`), and content-sized (`auto`) columns behave — especially when you resize the window.

## What you'll practice

- Reading `fr` as "a share of the free space"
- The difference between tracks that stay put and tracks that stretch
- Mixing units in one template

## Instructions

1. Build five grids, one under another. Each is a `<section>` with three `<p>` children of **different text lengths** — e.g. "Hi", "A medium bit of text", and a whole sentence. Put an `<h2>` naming the template **above** each section (not inside it — anything inside would become a grid item).
2. Give every section two classes, e.g. `<section class="grid t1">`. Put the shared styles in one rule and the templates in their own rules:
   ```css
   .grid {
       display: grid;
       gap: 12px;
   }
   ```
   - `.t1` → `grid-template-columns: 200px 200px 200px;`
   - `.t2` → `grid-template-columns: 1fr 1fr 1fr;`
   - `.t3` → `grid-template-columns: 1fr 2fr 1fr;`
   - `.t4` → `grid-template-columns: 200px 1fr;` (three items, only two columns — watch where the third goes)
   - `.t5` → `grid-template-columns: auto 1fr auto;`
3. Give the `<p>`s a `background-color` and `margin: 0` so you can see the columns.
4. Drag the browser window wide and narrow. Watch which columns change size and which don't.
5. Under each grid, add a `<p>` describing what you saw, in one sentence.

## Requirements

- [ ] All five templates built, each labelled with a heading above it
- [ ] `display: grid` and `gap` in one shared `.grid` rule; each template in its own class
- [ ] One sentence per template, based on what you actually saw while resizing

## Acceptance criteria

- Your notes say that `200px 200px 200px` never changes size, that the `fr` templates always fill the width, and that in `auto 1fr auto` the outer columns hug their content while the middle one takes the rest.
- You can explain why `.t4`'s third item went onto a new row.

## Hints

<details><summary>Show hint</summary>

`1fr 2fr 1fr` splits the free space into 4 shares (1 + 2 + 1). The middle column gets 2 of them — half the free space — and each side column gets a quarter.
</details>

## Stretch (optional)

Add a sixth grid with `grid-template-columns: 33% 33% 33%` and `gap: 16px`. Look for a horizontal scrollbar. Then explain in one sentence why `1fr 1fr 1fr` doesn't have that problem.
