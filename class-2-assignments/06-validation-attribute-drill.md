# Assignment 06 — Validation Attribute Drill

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 2 §10 (validation attributes)
**Build in:** `work/06-validation-attribute-drill/index.html`

---

## Goal

Build a handful of inputs with validation attributes and deliberately try to break every rule so you learn what each browser message looks like.

## What you'll practice

- `required`, `minlength`, `maxlength`, `min`, `max`, `pattern`, `placeholder`
- That `required` is a boolean attribute (present = true)
- That `placeholder` is a hint, **not** a label and **not** validation

## Instructions

1. Make a `<form>` with a submit button and these fields (each with a real `<label>`):
   - **Username** — `type="text"`, `required`, `minlength="3"`, `maxlength="12"`
   - **Quantity** — `type="number"`, `min="1"`, `max="10"`, `required`
   - **Phone** — `type="tel"`, `pattern="[0-9]{11}"`, `placeholder="08012345678"`
   - **Bio** — `<textarea>`, `maxlength="150"`
2. Now try to submit with each of these and **write down the exact message the browser shows**:
   - Username empty
   - Username = `ab` (too short)
   - Quantity = `0`, then `50`
   - Quantity = `abc`
   - Phone = `12345` (doesn't match the pattern)
3. Finally, add `required="false"` to the Bio field, submit it empty, and confirm it's **still not** treated as optional the way you'd expect — then remove the attribute entirely.

## Requirements

- [ ] All fields present with the attributes listed
- [ ] Every field has a linked `<label>`
- [ ] A short written list of the 6 messages you saw
- [ ] A one-line note on what `required="false"` actually means

## Acceptance criteria

- You can state, from memory, which attribute produced each error message.
- You understand that removing `required` (not setting it to `"false"`) is how you make a field optional.

## Hints

<details><summary>Show hint</summary>

`pattern="[0-9]{11}"` means "exactly 11 characters, each a digit 0–9". The browser only checks `pattern` when the field is non-empty — combine it with `required` if the field must be filled.
</details>
