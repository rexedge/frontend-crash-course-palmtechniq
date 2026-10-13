# Assignment 16 — Live Form Validation

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 7 §8–10 (form values, `.disabled`, the `input` and `submit` events)
**Build in:** `work/16-live-form-validation/index.html` + `style.css` + `app.js`

---

## Goal

Build a sign-up form that checks each field **while the user types**, shows a message under any field that isn't right yet, and keeps the submit button switched off until everything passes.

## What you'll practice

- Small functions that return `true` or `false` (Class 6), fed by the DOM
- The `input` event on several fields
- Switching a button on and off with `.disabled`
- Combining conditions with `&&` and `!`

## Instructions

1. Build the form: name, email, and password — each with a `<label>`, an `<input>`, and an empty `<p class="field-message">` underneath for its message. Add a submit button with the `disabled` attribute, and an empty, hidden paragraph after the form for the success message.
2. The rules:

   | Field | Passes when… | Message when it doesn't |
   |---|---|---|
   | Name | it has 2 or more characters, after trimming | `Your name needs at least 2 characters.` |
   | Email | it contains an `@` **and** a `.` | `An email address needs an @ and a dot.` |
   | Password | it has 8 or more characters | `Your password needs at least 8 characters.` |

3. Write three functions that each **return** `true` or `false`: `nameIsValid()`, `emailIsValid()`, `passwordIsValid()`. Each one reads its own input's `.value`.
4. Write `updateButton()`, which sets the submit button's `.disabled` — off only when **all three** functions return `true`.
5. Give each input an `input` listener that does two things: show or clear **its own** message, then call `updateButton()`.
6. On `submit`: `preventDefault`, hide the form, and show `Welcome, {name}!`.

## Requirements

- [ ] Three validity functions that return booleans, and do nothing else
- [ ] A field's message appears only once the user has typed in **that** field
- [ ] A message disappears as soon as its field becomes valid
- [ ] The submit button is disabled whenever any of the three rules fails
- [ ] The messages have a colour from a CSS class — there's no `.style` in `app.js`
- [ ] The success message is written with `textContent`

## Acceptance criteria

- On page load: no messages, and the button is greyed out.
- Type `A` as the name: the name message appears. Type `Ada`: it goes.
- Type `ada@example` as the email: the email message appears. Add `.com`: it goes.
- Type 7 characters as the password: the message shows, and the button is still off. Type an 8th: the button comes on.
- Now delete the name. The button switches **off** again.
- Submit: the form is replaced by `Welcome, Ada!`, and the page doesn't reload.

## Hints

<details><summary>Show hint</summary>

Each validity function is one line. For example:

```js
function emailIsValid() {
    return emailInput.value.includes("@") && emailInput.value.includes(".");
}
```

`.disabled` wants `true` to switch the button **off**, so it's the opposite of "everything is valid":

```js
submitButton.disabled = !(nameIsValid() && emailIsValid() && passwordIsValid());
```
</details>

## Stretch (optional)

Connect your Class 6 `passwordScore` function (Assignment 18): show `weak`, `ok`, or `strong` beside the password box as the user types.
