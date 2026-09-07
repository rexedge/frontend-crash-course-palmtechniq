# Assignment 07 — Semantic Rewrite of "About Me"

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~35 min · 🧵 keep this file
**Prereqs:** Class 1 "About Me" page finished; Class 2 §4–5
**Build in:** `work/07-semantic-about-me/index.html`

---

## Goal

Take the plain "About Me" page you built in Class 1 and rebuild it with **meaningful structure**. The content stays the same — only the skeleton changes.

## What you'll practice

- Wrapping existing content in the right landmarks
- One `<main>`, with `<header>`/`<footer>` outside it
- Splitting content into `<section>`s, each with its own heading

## Instructions

1. Open your Class 1 About Me page beside a new file.
2. Rebuild it with this structure:
   - `<header>` — your name in `<h1>`, plus a `<nav>` with a `<ul>` of 3 links (they can point to `#` for now)
   - `<main>` containing three `<section>` blocks:
     - "About" — your intro paragraph(s)
     - "Things I Like" — your `<ul>`
     - "Goals" — an `<ol>` in priority order
   - `<footer>` — one `<p>` about yourself and one `<a>` link
3. Keep your `<img>` (with its `alt`) somewhere sensible inside `<main>`.
4. Do **not** add any CSS.

## Requirements

- [ ] Upgraded skeleton (`lang`, `<meta charset>`, `<title>` with your name)
- [ ] Exactly one `<main>`; `<header>` and `<footer>` are its siblings, not children
- [ ] 3 `<section>` elements, each with its own `<h2>`
- [ ] `<nav>` contains a `<ul>` of links
- [ ] The image still has a written `alt`
- [ ] Same content as the Class 1 version — this is a re-structure, not a rewrite

## Acceptance criteria

- Open both versions side by side. They read identically in the browser (still plain text).
- The dev tools "Elements" tree of the new version clearly shows the page regions without you reading any content.
- Nothing lives directly in `<body>` except `<header>`, `<main>`, `<footer>`.

## Hints

<details><summary>Show hint</summary>

If a chunk of content has its own heading and belongs to the page (not shareable on its own), it's a `<section>`. Your whole About Me page isn't a blog post, so you won't need `<article>` here.
</details>

## Stretch (optional)

Add an `<aside>` inside `<main>` with a short "Currently learning" note or a list of links you find useful.
