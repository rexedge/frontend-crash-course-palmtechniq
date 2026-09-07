# Assignment 07 — Nesting By Hand

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 1 §5 (Understanding "Nesting")
**Build in:** `work/07-nesting-by-hand/index.html`

---

## Goal

Reproduce a three-level nested list exactly, with correct indentation, then build one of your own.

## What you'll practice

- Putting a `<ul>` **inside** an `<li>` to make sub-lists
- Indenting each level so the structure is readable
- Closing tags in the reverse order they opened

## Instructions

1. Build a valid skeleton with an `<h1>` like `Nesting Practice`.
2. Reproduce this outline as nested `<ul>` / `<li>` — a list inside a list inside a list. Indent every level by 4 spaces:

```
Africa
    Nigeria
        Lagos
        Abuja
    Kenya
        Nairobi
Europe
    France
        Paris
```

3. Below it, build a **second** nested list of your own: your family (you → your siblings → their kids or pets), or a folder structure on your computer, or a menu (Starters / Mains / Desserts, each with dishes).

## Requirements

- [ ] The Africa/Europe list matches the outline exactly (same items, same nesting depth)
- [ ] Sub-lists are placed **inside** an `<li>`, not between `<li>`s
- [ ] Every level is indented one step further than its parent
- [ ] Every `<ul>` and `<li>` is closed, in the correct order
- [ ] A second, original nested list of your own
- [ ] Valid skeleton

## Acceptance criteria

- In the browser, the sub-items are visibly indented under their parents, forming a tree.
- The dev tools "Elements" panel shows `ul > li > ul > li > ul > li` for the deepest branch.
- No tags are closed out of order.

## Hints

<details><summary>Show hint</summary>

A sub-list goes *inside* the `<li>` it belongs to, before that `<li>` closes:

```html
<li>Nigeria
    <ul>
        <li>Lagos</li>
        <li>Abuja</li>
    </ul>
</li>
```

The last tag you opened is the first one you close.
</details>
