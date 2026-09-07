# Assignment 14 — Event Registration Form

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~35 min
**Prereqs:** Class 2 §10 (validation attributes)
**Build in:** `work/14-event-registration-form/index.html`

---

## Goal

Build a registration form where **every field has a real validation rule**, then test each rule by trying to break it.

## What you'll practice

- Choosing the right validation attribute for each kind of field
- Combining `type`, `required`, `min`/`max`, `pattern`, `maxlength`
- Reading and understanding the browser's built-in error messages

## Instructions

Build "Register for the Workshop" inside a semantic page. Fields:

| Field | Control + rules |
|---|---|
| Full name | `text`, `required`, `minlength="2"` |
| Email | `email`, `required` |
| Number of guests | `number`, `min="1"`, `max="4"`, `required` |
| T-shirt size | `select`, placeholder option `disabled selected`, then XS–XL |
| Dietary notes | `textarea`, `maxlength="200"` |
| Phone | `tel`, `pattern="[0-9]{11}"`, `placeholder="08012345678"`, `required` |
| Code of conduct | `checkbox`, `required`, label "I agree to the code of conduct" |
| — | `button type="submit">Register</button>` |

After building, **test every rule** and write a short list of what happened:
- name empty / name = `x`
- guests = `0` / `5` / `two`
- phone = `0801` / `080123456789` (12 digits) / `abcdefghijk`
- submit without ticking the checkbox
- submit with the dropdown untouched

## Requirements

- [ ] Every field present with the exact rules above
- [ ] Every control has a linked `<label>`
- [ ] A written list of the results of your break-tests
- [ ] No CSS

## Acceptance criteria

- The form cannot be submitted until name, email, guests, phone, and the checkbox are all valid.
- `guests` accepts only whole numbers 1–4.
- `phone` accepts only exactly 11 digits.

## Hints

<details><summary>Show hint</summary>

`maxlength` silently stops you typing past the limit — there's no error message, the field just won't accept more characters. `minlength` **does** show a message on submit.
</details>
