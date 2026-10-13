# Assignment 02 — Change Text on Click

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min (do it 3 times)
**Prereqs:** Class 7 §4–6 (`querySelector`, `textContent`, events)
**Build in:** `work/02-change-text-on-click/index.html` + `app.js`

---

## Goal

Make a button change a heading — the smallest complete "find, listen, change" there is. Do it three times, the last one from memory.

## What you'll practice

- `addEventListener("click", ...)`
- Passing a function by name, without brackets
- The same thing as an arrow function

## Instructions

1. Build a page with an `<h1>` that says `Not clicked yet` and a `<button type="button">`. Give each an `id`.
2. **First time — a named function.** Find both elements. Write `function showClicked()` that sets the heading's text to `Clicked!`. Pass it to `addEventListener`.
3. **Second time — an arrow function.** Turn the first version into a comment, and write it again with the function written inside the `addEventListener` call.
4. **Third time — from memory.** In a brand-new folder, with nothing to look at.
5. One experiment: in the named-function version, add brackets — `showClicked()` — and reload. What does the heading say before you've clicked anything?

## Requirements

- [ ] Both elements found by `id`, each stored in a `const`
- [ ] A named-function version and an arrow-function version
- [ ] A third version typed from memory
- [ ] The brackets experiment done, and explained in a one-line comment

## Acceptance criteria

- The heading says `Not clicked yet` when the page loads, and `Clicked!` after one click.
- Your comment says that `showClicked()` with brackets **runs the function straight away**, while the page is loading, instead of handing it over to be run on a click.
- No red in the Console.

## Hints

<details><summary>Show hint</summary>

Count the brackets at the end of the arrow-function version: `});`. The `}` closes the function, and the `)` closes `addEventListener(`.
</details>
