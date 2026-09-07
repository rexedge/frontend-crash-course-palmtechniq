# Assignment 03 — Ten Paragraphs

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 1 §4 (Paragraphs)
**Build in:** `work/03-ten-paragraphs/index.html`

---

## Goal

Write a page with one `<h1>` and exactly ten `<p>` elements — one sentence each — and see how the browser separates paragraphs automatically.

## What you'll practice

- `<p>` for normal body text
- That each `<p>` is its own block with space around it (no `<br>` needed)
- Opening and closing the same tag ten times without a slip

## Instructions

1. Build a valid skeleton.
2. Add an `<h1>` that says `My Day`.
3. Add **ten** separate `<p>` elements, each a single sentence, describing your day in order from waking up to going to bed.
4. Do **not** use a list — this is paragraph practice.
5. Save and view. Notice the gap the browser puts between each paragraph on its own.

## Requirements

- [ ] Exactly one `<h1>` and exactly ten `<p>` elements
- [ ] Each `<p>` is opened and closed properly
- [ ] One sentence per paragraph, in chronological order
- [ ] No `<ul>`, `<ol>`, or `<br>`
- [ ] Valid skeleton

## Acceptance criteria

- The browser shows ten visually separated blocks of text under the heading.
- Viewing the page source (or dev tools) shows ten `<p>...</p>` pairs, none nested inside another.

## Hints

<details><summary>Show hint</summary>

If two of your sentences run together with no gap, you probably forgot a `</p>` or an opening `<p>` somewhere. Count your opening tags and your closing tags — they must match.
</details>
