# Assignment 03 — Label + Input Pairs

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 2 §8 (inputs and labels)
**Build in:** `work/03-label-input-pairs/index.html`

---

## Goal

Type eight correctly-linked `<label>` + `<input>` pairs and confirm the link works by clicking labels.

## What you'll practice

- `for` on the label must **exactly match** `id` on the input
- Choosing the right `type` for each field
- Adding a `name` to every control out of habit

## Instructions

1. Inside `<main>`, create eight label + input pairs (no `<form>` wrapper needed for this drill). Put each pair inside its own `<p>` so they stack on separate lines.
2. Use these fields and types:

   | Label text | `type` |
   |---|---|
   | Full name | `text` |
   | Email address | `email` |
   | Password | `password` |
   | Age | `number` |
   | Date of birth | `date` |
   | Phone number | `tel` |
   | Website | `url` |
   | Subscribe to updates | `checkbox` |

3. Give every input a unique `id` and a `name`. Link each label with `for`.
4. Open in the browser. **Click the label text** of each field and confirm the matching input gets focus (cursor appears / checkbox toggles).

## Requirements

- [ ] 8 pairs, each in its own `<p>`
- [ ] Every `for` matches its input's `id` exactly (watch capitalisation)
- [ ] Every input has a `name`
- [ ] Correct `type` for all 8

## Acceptance criteria

- Clicking any label focuses (or toggles) its field — all 8.
- No two inputs share an `id`.

## Hints

<details><summary>Show hint</summary>

A clean pattern: `id` and `name` can be the same word. `<label for="email">Email</label><input type="email" id="email" name="email">`.
</details>

## Stretch (optional)

Rewrite two of the pairs using the **wrapping** style instead: `<label>Full name <input type="text" name="name"></label>`. This also links them, with no `for`/`id` needed. Note which style you find easier to read.
