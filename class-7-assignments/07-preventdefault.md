# Assignment 07 — preventDefault

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 7 §10 (forms, `submit`, `preventDefault`)
**Build in:** `work/07-preventdefault/index.html` + `app.js`

---

## Goal

Stop a form from reloading the page — and prove to yourself that it really has stopped.

## What you'll practice

- The `submit` event, on the form
- `event.preventDefault()`
- Two ways to tell whether a page reloaded

## Instructions

1. Build a page with a `<form>` holding one labelled text input (give it a `name` attribute) and a submit button.
2. Make the first line of `app.js`: `console.log("app.js loaded");`.
3. **Before** you write any other JavaScript, type something and submit the form. Watch two things: the Console, and the address bar.
4. Now listen for `submit` on the form. In the function, call `event.preventDefault()` and then `console.log("would have submitted")`.
5. Submit again. Compare the Console and the address bar with step 3.
6. Click into the text box and press **Enter** instead of clicking the button. Does your function still run?

## Requirements

- [ ] The listener is on the `<form>`, for the `submit` event
- [ ] The function takes the `event` parameter
- [ ] `event.preventDefault()` is the first line inside the function
- [ ] Both submits compared — before and after — in a short comment

## Acceptance criteria

- Without `preventDefault`: `app.js loaded` appears again on every submit, and the address gains a `?…=…` on the end.
- With it: `app.js loaded` appears only once, `would have submitted` is added on each submit, and the address doesn't change.
- Pressing Enter in the box runs your function too.

## Hints

<details><summary>Show hint</summary>

If the page still reloads, check three things: is the listener on the form (not the button)? Is the event name `"submit"`? Does the function have `(event)` in its brackets — and do you call `event.preventDefault()` with its own brackets?
</details>
