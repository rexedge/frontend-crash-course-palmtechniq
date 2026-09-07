# Assignment 08 — Style the Contact Form

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min · 🧵 keep this file
**Prereqs:** Class 2 Assignment 11 (contact form) done; Class 3 §5–13
**Build in:** `work/08-style-contact-form/index.html` + `style.css`

---

## Goal

Style the Class 2 contact form into something that looks like a real form — this is the Class 3 **homework**.

## What you'll practice

- `display: block` on labels; full-width inputs with `box-sizing`
- Styling a `<button>` from scratch
- Consistent vertical rhythm in a form

## Instructions

1. Copy your Class 2 contact form into `work/08-style-contact-form/index.html`. Add the `<link rel="stylesheet" href="style.css">` — the only HTML change.
2. Create `style.css` and meet every requirement.

## Requirements

- [ ] `box-sizing` reset; `body` gets a `font-family`, `color`, and `background-color`
- [ ] The `<form>`: `max-width: 480px`, centred with `margin: 0 auto`, `padding`, and a subtle `border` or `background-color`
- [ ] `label { display: block; }` with a small `margin-bottom`
- [ ] `input`, `textarea`, `select`: `width: 100%`, `padding: 10px`, a `border` (the reset stops them overflowing)
- [ ] Even spacing between fields (e.g. `margin-bottom` on each wrapping `<p>`, one value)
- [ ] The submit `<button>`: `padding`, a `background-color`, a text `color`, `border: none`, `cursor: pointer`
- [ ] `<fieldset>` given some `padding`; the `<legend>` styled (weight, size, or colour)
- [ ] Surrounding `<header>` / `<footer>` styled to match your About Me page

## Acceptance criteria

- Every field is full width and lines up in a single tidy column.
- Labels sit above their fields, not beside them.
- The button looks clickable (colour, padding, pointer cursor) and has no default browser chrome.
- Fields are evenly spaced — no one gap bigger than the others.
- The form still validates on submit exactly as it did in Class 2 (styling didn't break it).

## Hints

<details><summary>Show hint</summary>

`width: 100%` + `padding` on an input overflows the form under the default `content-box`. The `box-sizing: border-box` reset fixes it — if inputs poke outside the form edge, that reset is missing or not reaching them.
</details>

## Stretch (optional)

Give the submit button a slightly different `background-color` on `:hover` (a *pseudo-class* — `button:hover { … }`). It's a small addition to what the lesson covered; you'll meet pseudo-classes properly later.
