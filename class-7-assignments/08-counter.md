# Assignment 08 — Counter

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~25 min
**Prereqs:** Class 7 §6–7 (events, remembering things between clicks, `classList`)
**Build in:** `work/08-counter/index.html` + `style.css` + `app.js`

---

## Goal

Build a counter with three buttons: minus, reset, and plus. It's a small build, but it has the shape of every interactive feature: a **variable** holds the truth, and the **page** shows it.

## What you'll practice

- A `let` variable that lives outside the functions, so it survives between clicks
- Three listeners that change the same variable
- One function whose only job is to update the page

## Instructions

1. Build the page: three `<button type="button">`s — `−`, `reset`, `+` — and a `<p>` that shows the number, starting at `0`.
2. In `app.js`, declare `let count = 0;` at the top.
3. Write one function, `showCount()`, that puts `count` into the paragraph.
4. Add a click listener to each button. Each one changes `count`, and then calls `showCount()`:
   - `+` adds 1
   - `−` subtracts 1
   - `reset` sets it back to 0
5. Style it: a big number, and buttons you'd actually want to press.

## Requirements

- [ ] `count` is declared once, outside every function
- [ ] The paragraph is only ever updated inside `showCount()`
- [ ] Each button's function does two things: change the variable, then call `showCount()`
- [ ] The buttons are real `<button>` elements with `type="button"`

## Acceptance criteria

- `+` three times shows `3`. `reset` shows `0`. `−` twice shows `-2`.
- The number on the page always matches `count`. Log `count` in the Console to check.
- No red in the Console.

## Hints

<details><summary>Show hint</summary>

If the display jumps straight back to the same number on every click, `let count = 0;` is inside a function, so it starts again from 0 each time. Move it to the top of the file.

`paragraph.textContent = count;` works even though `count` is a number — it's turned into text for you.
</details>

## Stretch (optional)

Make the number turn red when it's below zero. Add a `.negative` class to your CSS, and extend `showCount()`: add the class when `count < 0`, and remove it otherwise.
