# Assignment 04 — Read an Input

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 7 §8 (form values, `.trim()`)
**Build in:** `work/04-read-an-input/index.html` + `app.js`

---

## Goal

Read what a person has typed into a box, at the moment they click a button.

## What you'll practice

- `.value`
- Reading a value **inside** the function, not at the top of the file
- `.trim()` and `.length` on what was typed

## Instructions

1. Build a page with a `<label>`, a text `<input>`, and a `<button type="button">`.
2. On click, `console.log` whatever is in the box right now.
3. Type something, click, type something else, click again. Each click should log the new text.
4. Log two more things on each click: the `typeof` the value, and the length of the value after `.trim()`.
5. Type only spaces and click. What is the trimmed length?
6. One experiment: move the line that reads `.value` to the **top** of the file, outside the function, and log that variable on click instead. Type something and click. What's logged — and why?

## Requirements

- [ ] The input has a `<label>` linked with `for` and `id`
- [ ] The value is read inside the click function
- [ ] The type and the trimmed length are logged too
- [ ] The "read it at the top" experiment done, and explained in a one-line comment

## Acceptance criteria

- Each click logs exactly what's in the box at that moment.
- The type is always `string` — even if you type digits.
- A box of spaces has a trimmed length of `0`.
- Your comment says that a value read at the top of the file is read **once**, when the page loads and the box is still empty.

## Hints

<details><summary>Show hint</summary>

Find the **input** at the top of the file — that's fine, the element itself doesn't change. Read its **`.value`** inside the function, because that's the part that changes.
</details>
