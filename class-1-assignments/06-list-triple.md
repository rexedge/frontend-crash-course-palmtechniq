# Assignment 06 — List Triple

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 1 §4 (Lists)
**Build in:** `work/06-list-triple/index.html`

---

## Goal

Build one page with three lists — one unordered and two ordered — and choose the right list type for each based on whether order matters.

## What you'll practice

- `<ul>` vs `<ol>`, and `<li>` for every item
- Deciding when sequence matters (`<ol>`) and when it doesn't (`<ul>`)
- Each list gets its own `<h2>`

## Instructions

1. Build a valid skeleton with an `<h1>`.
2. Add three sections, each introduced by its own `<h2>`:
   - **"Foods I Like"** — a `<ul>` with 5 `<li>` items (order doesn't matter → unordered)
   - **"My Morning Routine"** — an `<ol>` with 5 `<li>` steps in the real order you do them (order matters → ordered)
   - **"My Top 3 Movies"** — an `<ol>` with 3 `<li>` items, best first (a ranking → ordered)
3. Save and view. Confirm the `<ul>` shows bullets and the `<ol>`s show numbers.

## Requirements

- [ ] Exactly three lists: one `<ul>`, two `<ol>`
- [ ] Every list item is wrapped in `<li>`
- [ ] Each list has its own `<h2>` above it
- [ ] `<li>` tags are nested **inside** their `<ul>`/`<ol>`, nothing else between them
- [ ] Valid skeleton

## Acceptance criteria

- Bullets on the foods list; numbers on the routine and movies lists.
- Your list-type choices match the rule: sequence/ranking → `<ol>`, no sequence → `<ul>`.

## Hints

<details><summary>Show hint</summary>

The only things allowed directly inside `<ul>` or `<ol>` are `<li>` elements. Put your text inside the `<li>`, not between the `<li>`s.
</details>
