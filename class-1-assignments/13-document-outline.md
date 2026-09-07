# Assignment 13 — Document Outline

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~25 min
**Prereqs:** Class 1 §4 (headings), §5 (nesting)
**Build in:** `work/13-document-outline/index.html`

---

## Goal

Build a page that is **only headings and short paragraphs**, arranged in a clean, ordered hierarchy — no lists, no images. This trains you to use heading levels for structure.

## What you'll practice

- Using `<h1>` → `<h2>` → `<h3>` to express *rank*, never skipping a level
- Keeping a multi-section document organised
- Seeing the "outline" your headings create

## Instructions

1. Choose a topic you know well (a sport, a game, a place, a hobby, a subject).
2. Build `index.html`:
   - one `<h1>` — the topic
   - **at least three** `<h2>` sections
   - under **each** `<h2>`, at least two `<h3>` sub-sections
   - after **each** `<h3>`, a 1–2 sentence `<p>`
3. No `<ul>`, `<ol>`, `<img>`, or `<a>` — headings and paragraphs only.

## Requirements

- [ ] Exactly one `<h1>`
- [ ] 3+ `<h2>`, each with 2+ `<h3>` under it
- [ ] A `<p>` after every `<h3>`
- [ ] Heading levels never skip (no `<h2>` straight to `<h4>`) and never go out of order
- [ ] No lists, images, or links
- [ ] Valid skeleton; nested headings indented for readability

## Acceptance criteria

- Reading **only the headings** top to bottom gives a sensible table of contents for the topic.
- Every `<h3>` clearly belongs under the `<h2>` above it.
- No heading level is skipped anywhere.

## Hints

<details><summary>Show hint</summary>

Think of it like a book: `<h1>` is the book title, `<h2>` are chapters, `<h3>` are sections within a chapter. You'd never jump from "Chapter" straight to "Sub-sub-section".
</details>
