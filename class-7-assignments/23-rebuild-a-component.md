# Assignment 23 — Rebuild a Component You've Used

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1.5 hr
**Prereqs:** all of Class 7
**Build in:** `work/23-rebuild-a-component/index.html` + `style.css` + `app.js`

---

## Goal

Pick **one** component you've used on real websites, and build it yourself in plain JavaScript — no libraries. Each of the three options below comes down to one number in a variable, and a function that redraws the page to match it.

## What you'll practice

- Planning before typing: what's the data, what are the events, what changes?
- One `let` variable as the single source of truth
- One function that makes the page match that variable

## The options — choose one

**A. Image carousel**

One photo at a time, with `Previous` and `Next` buttons and a counter such as `2 / 5`.

- Keep the photo addresses in an array, and the current position in `let current = 0;`.
- Write `showSlide()`: set the image's `src` and `alt` from the array, and update the counter.
- `Next` adds 1; `Previous` subtracts 1. Both **wrap around**: after the last photo comes the first, and before the first comes the last.

**B. Star rating**

Five star buttons (`★`). Clicking the third star fills stars one to three, and a line underneath reads `You rated this 3 out of 5.`

- Write a `.filled` class in your CSS (a gold colour).
- On click, loop over **all** the stars. Each star at or before the clicked position gets `filled`; each one after it loses `filled`.
- Clicking a lower star afterwards must reduce the rating.

**C. Multi-step form**

A form split into three `<fieldset>` steps, with `Back` and `Next` buttons and a line that reads `Step 2 of 3`. Only one step shows at a time.

- Keep the position in `let step = 0;`.
- Write `showStep()`: hide every fieldset, show `steps[step]`, update the progress line, and disable `Back` on the first step.
- On the last step, `Next` is replaced by a `Submit` button. On submit, show a thank-you message without reloading.

## Requirements

- [ ] One of the three components, fully working
- [ ] A short plan in a comment at the top of `app.js`: the variable, the events, and what changes
- [ ] One `let` variable holds the position or rating; the page is always redrawn from it by one function
- [ ] Every control is a real `<button>`, usable with the keyboard
- [ ] Only what Class 7 covers: no timers, no libraries, no `position`, no transitions

## Acceptance criteria

- **A:** with five photos, `Previous` on the first photo goes to `5 / 5`, and `Next` on the last goes to `1 / 5`. The image's `alt` changes along with its `src`.
- **B:** clicking star 3 fills exactly three stars. Clicking star 1 afterwards leaves exactly one filled. The line of text always matches.
- **C:** `Back` is disabled on step 1. The progress line is right on every step. The page never reloads.

## Hints

<details><summary>Show hint</summary>

- **A** — wrapping forwards is the `%` operator from Class 6: `current = (current + 1) % sources.length;`. Wrapping backwards has a catch: in JavaScript `-1 % 5` is `-1`, not `4`. Add the length first: `current = (current - 1 + sources.length) % sources.length;`.
- **B** — `forEach` can give the inner loop its own index: `stars.forEach((other, j) => { ... })`. Compare `j` with the clicked star's index, `i`.
- **C** — moving between steps doesn't submit anything, so `Back` and `Next` must be `type="button"`. Only the last button is `type="submit"`. And leave `required` off the fields in this one: the browser can't show its error bubble on a field inside a hidden step, so the form would refuse to submit — with nothing on the page to say why, only a note in the Console that a form control "is not focusable".
</details>

## Stretch (optional)

For **B** *(this reaches ahead of Class 7)*: preview the rating as the mouse moves over the stars. Look up the `mouseover` and `mouseout` events — and make sure that moving the mouse away restores the rating that was actually clicked.
