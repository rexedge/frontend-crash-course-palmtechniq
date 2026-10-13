# Assignment 01 — Select and Log

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 7 §3–5, §11 (where the script goes, `querySelector`, `textContent`, `querySelectorAll`)
**Build in:** `work/01-select-and-log/index.html` + `app.js`

---

## Goal

Find elements on a page and log what you found. Nothing on the page changes yet — this is only the "find" step.

## What you'll practice

- `document.querySelector` with a tag name
- `document.querySelectorAll`, `.length`, and an index
- Reading `.textContent`
- What `null` looks like when nothing matches

## Instructions

1. Build a page with an `<h1>`, three `<p>`s, and a `<ul>` of four `<li>`s. Put the `<script>` tag at the end of `<body>`.
2. In `app.js`:
   - log the `<h1>`'s `textContent`
   - log **how many** `<p>`s `querySelectorAll` finds
   - log the **second** paragraph's text
   - log how many `<li>`s there are, and the text of the last one — found with `length - 1`, not with a number you counted
3. Log `document.querySelector("h2")`. There's no `<h2>` on the page. What do you get?
4. Log one of the elements itself (not its text), and hover over it in the Console.

## Requirements

- [ ] The script is at the end of `<body>`
- [ ] The heading found with `querySelector`; the paragraphs and list items found with `querySelectorAll`
- [ ] The second paragraph reached with an index
- [ ] The last list item reached with `length - 1`
- [ ] The missing `<h2>` logged

## Acceptance criteria

- The Console shows your heading's text, then `3`, then your second paragraph's text, then `4` and your last list item's text.
- The missing `<h2>` logs as `null`, with no error — the error only comes if you try to **use** it.
- Hovering over a logged element highlights it on the page.

## Hints

<details><summary>Show hint</summary>

The second paragraph is at index `1`, because the list starts counting at 0 — exactly like an array in Class 6: `paragraphs[1].textContent`.
</details>
