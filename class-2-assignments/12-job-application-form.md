# Assignment 12 — Job Application Form

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min
**Prereqs:** Class 2 §7–11
**Build in:** `work/12-job-application-form/index.html`

---

## Goal

Build a longer form broken into logical groups with `<fieldset>` / `<legend>`, using a wide range of input types and validation rules.

## What you'll practice

- Organising many fields into `<fieldset>` groups
- `type="tel"` + `pattern`, `type="url"`, `type="number"` + `min`/`max`, `type="date"`
- Radio groups and checkbox groups in the same form
- `<select>` for a single choice from a list

## Instructions

Build a form inside a semantic page (`header` / `main` / `footer`). Split the form into **three `<fieldset>`s**, each with a `<legend>`:

**1. Personal details**
- Full name — `text`, `required`, `minlength="2"`
- Email — `email`, `required`
- Phone — `tel`, `pattern="[0-9]{11}"`, `placeholder="08012345678"`
- Portfolio URL — `url`

**2. Experience**
- Years of experience — `number`, `min="0"`, `max="50"`, `required`
- Highest role held — `select` with a placeholder option + 4 real options
- Describe a project you're proud of — `textarea`, `maxlength="500"`

**3. Availability**
- Earliest start date — `date`, `required`
- Employment type — `fieldset`-style radio group (`full-time` / `part-time` / `contract`), shared `name`
- Days available — checkbox group (Mon–Fri), you may share one `name`

Finish with a `button type="submit">Submit application</button>`.

## Requirements

- [ ] 3 `<fieldset>`s each with a `<legend>`
- [ ] Every control has a linked `<label>`
- [ ] All validation attributes above are present
- [ ] Radio group shares one `name`; each radio has a `value`
- [ ] No CSS

## Acceptance criteria

- Submitting with any `required` field empty is blocked.
- `Years of experience` rejects `-1`, `51`, and letters.
- `Phone` rejects a value that isn't 11 digits (when filled).
- Only one employment type can be selected.

## Hints

<details><summary>Show hint</summary>

A checkbox group can all share `name="days"` — on a real submit that sends multiple `days=` values. Each checkbox still needs its own `id` and matching `<label for>`.
</details>
