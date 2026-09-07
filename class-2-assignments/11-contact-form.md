# Assignment 11 — Contact Form Page

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~45 min · 🧵 keep this file
**Prereqs:** Class 2 §7–11 (the whole forms half)
**Build in:** `work/11-contact-form/index.html`

---

## Goal

Build a complete contact page: a **semantic page structure** with a **working, validated form** inside it. This is the main build for Class 2 and you reuse it in Classes 3, 4, 5, and 7.

## What you'll practice

- Every form control from the lesson: `input`, `textarea`, `select`, radio group, checkbox, submit `button`
- `<label for>` ↔ `id` on every control
- `<fieldset>` + `<legend>` for a radio group
- Validation attributes: `required`, `minlength`
- Placing a form inside a proper semantic layout

## Instructions

Build `index.html` with:

**Structure**
- Upgraded skeleton (`lang`, `<meta charset>`, `<title>`)
- `<header>` — a site name (`<h1>`) + `<nav>` with a `<ul>` of 3 links
- `<main>` containing:
  - a `<section>` with `<h2>` "Get in touch" and a short intro `<p>`
  - the `<form>` (no `action`)
- `<footer>` outside `<main>` — a `<p>` and one link

**The form**
| Field | Control | Rules |
|---|---|---|
| Full name | `input type="text"` | `required` |
| Email | `input type="email"` | `required` |
| Subject | `input type="text"` | optional |
| Message | `textarea` `rows="6"` | `required`, `minlength="10"` |
| How did you hear about us? | `select` | a disabled+selected placeholder `<option>` first, then 3 real options |
| Preferred contact method | `fieldset` + `legend` + 2–3 `radio` | all radios share one `name` |
| Consent | `input type="checkbox"` | `required` |
| — | `button type="submit"` | text: "Send message" |

Every control gets a `<label>` linked with `for`/`id`. Wrap each field in a `<p>` so it sits on its own line (no CSS yet).

## Requirements

- [ ] `<header>` / `<main>` / `<footer>` structure, one `<main>`
- [ ] All 8 rows above present
- [ ] **Every** input/textarea/select has a `<label>` whose `for` matches its `id`
- [ ] Radio buttons share a single `name`; each has a distinct `value`
- [ ] `<select>` first option is `disabled selected` with an empty `value`
- [ ] `<textarea>` uses content between the tags, not a `value` attribute
- [ ] Submit button is `type="submit"` and inside the `<form>`
- [ ] No CSS

## Acceptance criteria

- Clicking **any** label text focuses/toggles its control (test all of them).
- Submitting with Name, Email, Message, or Consent empty is blocked by the browser with a visible message.
- You cannot select more than one "Preferred contact method" radio.
- The dropdown shows "Choose one" (or similar) before any selection.
- Pressing submit with everything valid just reloads the page (expected — real handling is Class 7).

## Hints

<details><summary>Show hint</summary>

If the label click does nothing, the `for` and `id` don't match exactly — check spelling and capitalisation. If both radios can be ticked, their `name`s differ.
</details>

## Stretch (optional)

Add a `type="tel"` phone field with `pattern="[0-9]{11}"` and a `placeholder` showing the format, only `required` when "Phone" is the chosen contact method (note: you can't wire that conditional logic without JS yet — just add the field and pattern).
