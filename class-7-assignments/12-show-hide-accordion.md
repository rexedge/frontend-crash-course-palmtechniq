# Assignment 12 — Show / Hide (Accordion)

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~35 min · 🧵 keep this file
**Prereqs:** Class 7 §7, §11 (`classList`, partners by index)
**Build in:** `work/12-show-hide-accordion/index.html` + `style.css` + `app.js`

---

## Goal

Build an FAQ list where each question is a button that shows and hides its answer. It's a pattern you can reuse in your capstone for project details.

## What you'll practice

- Two lists that line up by index: questions and answers
- `forEach` with the index as a second parameter
- `classList.toggle` with a `.hidden` class

## Instructions

1. Build the page: five questions, each one a `<button type="button" class="question">`, and each followed by its answer in a `<div class="answer hidden">`.
2. In the CSS: make the question buttons full-width and left-aligned, give the answers some padding, and put `.hidden { display: none; }` last.
3. In `app.js`, find all the questions and all the answers with two `querySelectorAll` calls.
4. Loop over the questions with `forEach((question, i) => { ... })`. On click, toggle `hidden` on `answers[i]`.
5. Test every question. Open two at once. Close them again.

## Requirements

- [ ] Five question buttons and five answers, in matching order
- [ ] Every answer starts hidden — the class is in the HTML
- [ ] One `forEach` adds all the listeners; nothing is written out five times
- [ ] Each question opens its **own** answer
- [ ] The questions are real `<button>` elements

## Acceptance criteria

- Clicking a question shows its answer; clicking it again hides it.
- Add a sixth question and answer to the HTML. They work with no change to `app.js`.
- You can reach every question with the `Tab` key, and open it with `Enter` or `Space`.

## Hints

<details><summary>Show hint</summary>

The whole idea is that question number `i` and answer number `i` belong together. Inside the `forEach`, `i` is that number, so `answers[i]` is the partner of the question that was clicked.

If the wrong answer opens, your questions and answers aren't in the same order in the HTML — or there's an extra element with one of those classes.
</details>

## Stretch (optional)

Make it a true accordion: opening one answer closes the others. Careful — "hide them all, then show this one" breaks the ability to close an answer by clicking it again. Before you hide them all, remember whether this one was already open:

```js
const wasOpen = !answers[i].classList.contains("hidden");
```

Then, after hiding everything, show it again only if it **wasn't** open.
