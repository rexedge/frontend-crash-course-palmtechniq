# Assignment 02 — Section vs Article

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 2 §4 (the section-vs-article quick test)
**Build in:** `work/02-section-vs-article/index.html`

---

## Goal

Practise the judgement call between `<section>` and `<article>` by building a page that correctly uses both, then justifying every choice in writing.

## What you'll practice

- `<article>` = self-contained, could stand alone (a blog post, a news item, a product card)
- `<section>` = a labelled thematic part of a bigger whole
- Every `<section>` / `<article>` should contain its own heading

## Instructions

1. Build a page for a small personal blog.
2. Inside `<main>`, add **two `<article>` elements** — two separate short "posts", each with its own `<h2>` title and 1–2 `<p>` of body text. Each should read fine if you pulled it out of the page on its own.
3. Also inside `<main>`, add **one `<section>`** titled "About this blog" with an `<h2>` and a `<p>`. This is a labelled part of the page, not something you'd syndicate alone.
4. At the bottom of the page, add a `<section>` titled "My reasoning" containing a `<ul>` with one `<li>` per decision: for each block above, one sentence saying why it's an `article` or a `section`.

## Requirements

- [ ] Full semantic skeleton (`header`, `main`, `footer`)
- [ ] Exactly 2 `<article>` and 2 `<section>` inside `<main>`
- [ ] Every `<article>` and `<section>` has its own heading
- [ ] The "My reasoning" list explains all 4 choices in plain language

## Acceptance criteria

- Read each `<article>` out loud on its own. It makes sense with no surrounding context.
- Read the "About this blog" `<section>` on its own. It feels like a fragment of a bigger page — that's why it's a section.
- Your reasoning list references the real content, not just the definitions.

## Hints

<details><summary>Show hint</summary>

The test: *Could this be published on its own, as-is, somewhere else?* Yes → `article`. It's a named chunk of this page → `section`. If you're stuck between them for a block, it's usually fine either way — say so in your reasoning.
</details>

## Stretch (optional)

Add a `<header>` **inside** one of the `<article>` elements holding that post's title (`<h2>`) and a `<p>` date line. Landmarks can nest — an article can have its own header and footer.
