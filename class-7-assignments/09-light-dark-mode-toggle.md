# Assignment 09 — Light / Dark Mode Toggle

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min · 🧵 keep this file
**Prereqs:** Class 7 §7, §14 Part A (guided practice)
**Build in:** `work/09-light-dark-mode-toggle/index.html` + `style.css` + `app.js`

---

## Goal

Add a button that switches a whole page between a light theme and a dark theme. This is half of the Class 7 hands-on — and it goes straight into your capstone.

## What you'll practice

- Toggling one class on `<body>`
- Writing a second theme with descendant selectors
- Updating a button's own text with `classList.contains`

## Instructions

1. Follow Part A of the lesson's guided practice (Class 7 §14). Then do it again on **one of your own pages** — a copy of your About Me page is ideal.
2. In the HTML: add a `<button type="button" id="theme-toggle">🌙 Dark</button>` to the header.
3. In the CSS: your existing styles are the light theme. Underneath them, write the dark theme as a set of `.dark` rules:
   - `.dark { ... }` for the page's own text and background colours
   - `.dark header { ... }`, `.dark a { ... }`, and so on, for every part that has its own colours
4. In the JavaScript: on click, toggle `dark` on `document.body`. Then set the button's text to `☀️ Light` if the page is now dark, or `🌙 Dark` if it isn't.
5. Look over the page in dark mode, slowly. Find anything you missed: links, borders, form fields, the footer.

## Requirements

- [ ] One class, `dark`, toggled on `<body>`
- [ ] Both themes live entirely in `style.css` — there are no colour values in `app.js`
- [ ] Every coloured part of the page has a dark version: text, backgrounds, links, borders
- [ ] The button's text always names the theme you'd switch **to**
- [ ] The button is a real `<button>` with `type="button"`

## Acceptance criteria

- The first click turns the page dark, and the button reads `☀️ Light`. The second click turns it back.
- In dark mode, every piece of text is easy to read. Nothing is dark-on-dark or light-on-light.
- In the Elements panel, `<body>` gains and loses `class="dark"` as you click.
- The page still works at 375px, 768px, and 1280px.

## Hints

<details><summary>Show hint</summary>

If part of the page ignores dark mode, that part has its own colour set by a rule that the `.dark` rule isn't beating. Inspect it, look at which rule wins in the Styles panel, and write a `.dark …` rule for that exact element. `.dark .card` (two classes) beats `.card` (one), so the dark rules usually win as long as you write them.
</details>

## Stretch (optional)

Reload the page in dark mode, and it's light again. That's expected — nothing is being saved. Write one sentence in a comment on why. (Saving a setting between visits needs something this course hasn't covered.)
