# Assignment 17 — Form Spec From a Screenshot

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 2 §7–11
**Build in:** `work/17-form-from-a-screenshot/index.html`

---

## Goal

Reverse-engineer a real signup or checkout form: recreate its fields, types, grouping, and which fields are required — using only HTML you know — then compare against the original.

## What you'll practice

- Reading a UI and mapping each control to the right HTML element + `type`
- Deciding which validation attributes a field implies
- Grouping related fields with `<fieldset>`

## Instructions

1. Find a real form online: a website signup, a checkout page, an event registration, a "contact sales" form. **Take a screenshot** (or just keep the tab open). Do **not** view its page source yet.
2. From what you can see, list every field: its label, what kind of control it is, whether it looks required (asterisks, "required" text), and any format hints (placeholder text like "MM/YY").
3. Build your HTML version inside a semantic page:
   - group fields into `<fieldset>`s where the original visually groups them
   - pick the best `type` for each (`email`, `tel`, `number`, `date`, `password`, `checkbox`, `radio`, `select`…)
   - add `required` where the original marks it
   - add `pattern` / `min` / `max` / `maxlength` where a format is implied
   - every control gets a linked `<label>`
4. Now open the real form's dev tools (Inspect a field) and compare: did you pick the same `type`? The same required fields? Note 3 differences and whether yours or theirs is better.

## Requirements

- [ ] A saved screenshot or a note of the URL in the folder
- [ ] Your recreated form inside a semantic page, no CSS
- [ ] Every visible field from the original is represented
- [ ] A short written comparison: 3+ differences you found

## Acceptance criteria

- Someone could look at your form and the screenshot and see they're asking for the same information in the same order.
- Your `type` choices are defensible (you can say why each one).

## Hints

<details><summary>Show hint</summary>

Common mappings: "Card number" → `text` with `inputmode`/`pattern` (just `text` + `pattern` is fine for you); "Expiry MM/YY" → `text` with a `pattern` and `placeholder`; "Country" → `select`; "Remember me" → `checkbox`; "Card type" (Visa/Mastercard) → `radio` group.
</details>
