# Assignment 13 — Survey Form

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 2 §7–11
**Build in:** `work/13-survey-form/index.html`

---

## Goal

Build a feedback survey that exercises every "choice" control: a rating radio group, a multi-select checkbox group, and a dropdown.

## What you'll practice

- Radio group for "pick exactly one" (a 1–5 rating)
- Checkbox group for "pick any that apply"
- `<select>` for a compact single choice
- `<fieldset>` + `<legend>` around each group
- `<textarea>` for open feedback

## Instructions

Build a survey inside a semantic page. Include:

1. **Overall rating** — a `<fieldset>` with `<legend>` "How would you rate us?" and 5 radio buttons (values `1`–`5`), all sharing `name="rating"`, `required`.
2. **Which features do you use?** — a `<fieldset>` with `<legend>` and 4+ checkboxes (share `name="features"`), each with its own `<label>`.
3. **How often do you visit?** — a `<select>` with a placeholder option + options like Daily / Weekly / Monthly / Rarely.
4. **Anything else?** — a `<textarea>`, `maxlength="300"`.
5. **Email (optional, if you want a reply)** — `type="email"`.
6. A `button type="submit">Submit survey</button>`.

## Requirements

- [ ] Each group wrapped in `<fieldset>` with a `<legend>`
- [ ] Rating radios share one `name` and are `required`
- [ ] Every checkbox and radio has its own `id` + linked `<label>`
- [ ] `<select>` has a disabled+selected placeholder first
- [ ] No CSS

## Acceptance criteria

- You can pick only one rating, but any number of features.
- Submitting without a rating is blocked.
- Clicking any option's label toggles that option.

## Hints

<details><summary>Show hint</summary>

Putting `required` on **one** radio in a group makes the whole group required — the browser won't submit until one is chosen. You don't need it on all five.
</details>
