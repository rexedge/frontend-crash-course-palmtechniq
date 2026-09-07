# Assignment 04 — Input Type Tour

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 2 §8 (common input types, checkboxes vs radios)
**Build in:** `work/04-input-type-tour/index.html`

---

## Goal

Build one field of every common input type in a single `<form>`, submit it, and observe how the browser treats each type differently.

## What you'll practice

- The behaviour differences between `text`, `email`, `password`, `number`, `tel`, `url`, `date`, `checkbox`, `radio`
- How a radio **group** works (shared `name`, one selectable)
- What `type="submit"` does

## Instructions

1. Make a `<form>` (no `action`).
2. Add one labelled field for each type: `text`, `email`, `password`, `number`, `tel`, `url`, `date`, one `checkbox`, and a **group of two `radio` buttons** sharing `name="size"` with `value="s"` and `value="m"`.
3. Add a `<button type="submit">Submit</button>`.
4. Open in the browser and experiment:
   - Type letters into the `number` field — what happens on submit?
   - Type `hello` into the `email` field and submit — what does the browser say?
   - Click the `date` field — what UI appears?
   - Try to select **both** radio buttons — can you?
   - In the `password` field, are the characters visible?

## Requirements

- [ ] One labelled field per type listed above
- [ ] The two radios share one `name` and have different `value`s
- [ ] A working submit button inside the form
- [ ] You've written a one-line note next to (or below) each field saying what you observed

## Acceptance criteria

- Only one radio button can be active at a time.
- The `email` and `url` fields reject obviously-wrong values on submit.
- You can describe, from memory, what `type="submit"` did.

## Hints

<details><summary>Show hint</summary>

If both radios can be selected at once, their `name` attributes differ. They must be **identical** to form a group.
</details>
