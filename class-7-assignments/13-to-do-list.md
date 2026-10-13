# Assignment 13 — To-Do List

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~45 min · 🧵 keep this file
**Prereqs:** Class 7 §8, §10, §12 (form values, `submit`, creating and removing elements)
**Build in:** `work/13-to-do-list/index.html` + `style.css` + `app.js`

---

## Goal

Build the classic: type a task, add it to a list, tick it off, delete it. It uses almost everything from this class in about 30 lines.

## What you'll practice

- Handling a form with `submit` and `preventDefault`
- `.value`, `.trim()`, and emptying a box
- `createElement`, `append`, and `remove`
- Giving a brand-new element its own listener

## Instructions

1. Build the page: a `<form>` with a labelled text input and an `Add` button, and an empty `<ul>` underneath.
2. In the CSS: a `.done` class (`text-decoration: line-through`, and a paler colour), plus whatever makes the list pleasant to use.
3. Write `addTodo(text)`. It builds one list item out of three elements:
   - an `<li>`
   - inside it, a `<span>` holding the text — clicking the span toggles `done` on it
   - inside it, a `<button type="button">` showing `×` — clicking it removes the whole `<li>`

   Then it appends the `<li>` to the list.
4. Listen for `submit` on the form. In the function:
   - `preventDefault`
   - read the box, and `.trim()` it
   - if there's anything left, call `addTodo` and empty the box
5. Test: add three tasks, tick one off, delete a different one, and try to add an empty one.

## Requirements

- [ ] Tasks are added with the `Add` button **and** by pressing Enter (the form gives you both)
- [ ] An empty box, or a box of spaces, adds nothing
- [ ] The box is emptied after each task is added
- [ ] Each task's text goes in with `textContent`
- [ ] Clicking a task's text toggles `done`; clicking its `×` removes that task only
- [ ] No `innerHTML` anywhere

## Acceptance criteria

- Add `Buy milk`, `Call home`, and `Revise Class 6`. Click `Call home`: it gets a line through it. Click the `×` beside `Buy milk`: only that one goes.
- Submitting spaces adds nothing, and there's no error.
- Type `<b>hello</b>` as a task. It appears as those exact characters.
- Reloading the page empties the list. That's expected — nothing is saved in this class.

## Hints

<details><summary>Show hint</summary>

The delete button needs to know *which* `<li>` to remove. It already does: the button, the span, and the `<li>` are all created inside the same run of `addTodo`, so the button's click function can use the `item` variable directly — `item.remove();`.

Why a `<span>` for the text? If the text sat straight in the `<li>`, a click on it would be hard to tell apart from a click on the `×`.

Give the `×` button its type with `deleteButton.setAttribute("type", "button");`.
</details>

## Stretch (optional)

Add a line under the list that reads `3 tasks`, and keep it up to date as tasks are added and removed. Keep the number in a `let` variable, and write one small function that shows it.
