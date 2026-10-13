# Assignment 06 — querySelectorAll Loop

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 7 §11 (`querySelectorAll`, `forEach`, `event.target`)
**Build in:** `work/06-queryselectorall-loop/index.html` + `app.js`

---

## Goal

Give five buttons a click listener each, with one loop — and use `event.target` to tell which one was clicked.

## What you'll practice

- `querySelectorAll` and the list it gives back
- `forEach`
- One shared function, and `event.target`

## Instructions

1. Build a page with five `<button type="button">`s, each with different text and the same class.
2. Find all five with `querySelectorAll`, and log the list's `.length`.
3. First, try to add a listener to the **list itself**: `buttons.addEventListener("click", ...)`. Read the error, then delete that line.
4. Write a named function, `showLabel(event)`, that logs `event.target.textContent`.
5. Use `forEach` to add `showLabel` as a click listener to every button.
6. Add a sixth button to the HTML. Does it work without any change to `app.js`?

## Requirements

- [ ] All the buttons found with one `querySelectorAll`
- [ ] The listeners added inside a `forEach`
- [ ] One named function shared by every button, using `event.target`
- [ ] The error from step 3 written in a comment, in your own words

## Acceptance criteria

- Clicking any button logs that button's own text.
- The sixth button works as soon as it's added to the HTML.
- Your comment says that `querySelectorAll` gives back a **list**, and a list isn't an element — so it has no `addEventListener`.

## Hints

<details><summary>Show hint</summary>

Inside the `forEach`, you pass the function by name, with no brackets: `button.addEventListener("click", showLabel);`. The browser supplies the `event` when it calls the function.
</details>

## Stretch (optional)

Write the loop a second time with the `for` loop from Class 6 (`for (let i = 0; i < buttons.length; i++)`). Both work. Which do you find easier to read?
