# Assignment 09 — Long-form Article Page

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min
**Prereqs:** Class 2 §4–6
**Build in:** `work/09-article-page/index.html`

---

## Goal

Build a single article page laid out with proper landmarks, a nested article `<header>`, a `<figure>`, and a related-links `<aside>`.

## What you'll practice

- One `<article>` as the page's main content, with sub-sections
- A nested `<header>` inside the article for the headline + byline
- `<figure>` + `<figcaption>` for an image with a caption
- Keeping the heading hierarchy in order (`h1` → `h2` → `h3`)

## Instructions

Pick a topic you know well. Build:

1. Page `<header>` — site name + `<nav>`.
2. `<main>` → one `<article>` containing:
   - a nested `<header>` with `<h1>` headline and a `<p>` byline/date
   - an intro `<p>`
   - **at least three** `<h2>` sub-sections, each with 1–2 `<p>` of body text; at least one `<h2>` should have an `<h3>` under it
   - one `<figure>` with an `<img>` (real `src`, written `alt`) and a `<figcaption>`
   - a nested `<footer>` inside the article with a `<p>` ("Written by …") 
3. An `<aside>` with `<h2>` "Related reading" and a `<ul>` of 3 links.
4. Page `<footer>`.

## Requirements

- [ ] Exactly one `<main>`, one page-level `<h1>` (inside the article header)
- [ ] `<article>` contains its own `<header>` and `<footer>`
- [ ] Headings never skip a level (no `h2` straight to `h4`)
- [ ] `<figure>` wraps the image **and** its `<figcaption>`
- [ ] `<aside>` with a heading and a link list
- [ ] No CSS

## Acceptance criteria

- The dev tools tree shows `main > article > (header, p, h2…, figure > (img + figcaption), footer)`.
- Reading only the headings top to bottom gives a sensible outline of the article.

## Hints

<details><summary>Show hint</summary>

An `<article>` can contain `<section>`s if the sub-parts are substantial. For a short piece, `<h2>` headings with paragraphs are enough — don't over-nest.
</details>
