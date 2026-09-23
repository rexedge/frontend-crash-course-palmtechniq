# Assignment 15 — Grid vs Flexbox: Choose and Justify

**Type:** Challenge · **Difficulty:** ⭐⭐ · **Time:** ~20 min
**Prereqs:** Class 5 §7 (Grid or Flexbox?)
**Answer in:** `work/15-grid-vs-flexbox-choose-and-justify/answers.md` (or any text file)

---

## Goal

For each scenario, decide whether you'd reach for Grid or Flexbox, and justify it in one line. Often more than one answer can be defended — the reasoning is what counts.

## What you'll practice

- The test: one direction, or two?
- The question: who's in charge — the items' content, or the container?

## The scenarios

1. A horizontal navbar with the logo on the left and the links on the right.
2. An image gallery that fits in as many columns as the screen allows.
3. A page-level layout: header, sidebar, content, footer.
4. A row of tags ("HTML", "CSS", "Accessibility"…) of different widths that wrap onto new lines.
5. A form where all the labels line up in one column and all the inputs line up in another.
6. Centring a single box in the middle of the screen.
7. A dashboard where specific cards must take specific cells and sizes.
8. A toolbar of buttons, with one button pushed to the far end.

## Requirements

- [ ] All 8 answered — Grid, Flexbox, or "either" — with one line of reasoning each
- [ ] At least two answers name the exact property you'd use (e.g. `space-between`, `auto-fit`)

## Acceptance criteria

- Your reasons use the ideas from Class 5 §7: one direction vs two; content-sized vs container-defined.
- Only **after** answering, compare with the suggested answers below, and note any you'd still defend differently.

<details><summary>Show suggested answers</summary>

1. **Flexbox** — it's one row; `justify-content: space-between` pushes the logo and the links to opposite ends.
2. **Grid** — `repeat(auto-fit, minmax(...))` lines the photos up in both directions and picks the column count for you.
3. **Grid** — it's two-dimensional; `grid-template-areas` lets you draw it as a map.
4. **Flexbox** — each tag is as wide as its text, and `flex-wrap: wrap` lets them flow like words. Grid would force them into equal columns.
5. **Grid** — two tracks, so every label and every input line up down the page. Flexbox per row only lines up if you give every label the same fixed width.
6. **Either** — Grid's `display: grid; place-items: center` is the shortest; Flexbox's three-line version is just as good.
7. **Grid** — you decide exactly which cells each card covers, with spans or named areas.
8. **Flexbox** — it's one row; `margin-left: auto` on the odd one out pushes it to the end.
</details>
