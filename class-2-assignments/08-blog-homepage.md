# Assignment 08 — Blog Homepage

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min · 🧵 keep this file
**Prereqs:** Class 2 §4–5
**Build in:** `work/08-blog-homepage/index.html`

---

## Goal

Build the front page of a fake blog using every layout landmark, with `<article>` used correctly for the post previews.

## What you'll practice

- `<article>` for self-contained post previews
- `<aside>` for content that's related but not essential
- A page-level `<header>` + `<nav>` and `<footer>`

## Instructions

Build a blog homepage with:

1. `<header>` — the blog's title in `<h1>` and a `<nav>` with a `<ul>` of 4 links (Home, Posts, About, Contact).
2. `<main>` containing **three `<article>` previews**, each with:
   - `<h2>` — the post title
   - `<p>` — a date line (e.g. "Posted 3 September 2025")
   - `<p>` — a 2–3 sentence excerpt
   - `<a>` — "Read more →" (can point to `#`)
3. An `<aside>` (inside `<main>` or as its sibling — your call, note which you chose and why) with:
   - `<h2>` "About the author"
   - a short `<p>`
   - a `<ul>` of 3 "Popular posts" links
4. `<footer>` — a copyright `<p>` and 2 links.

## Requirements

- [ ] Upgraded skeleton
- [ ] Exactly one `<main>`
- [ ] 3 `<article>` elements, each with heading + date + excerpt + link
- [ ] One `<aside>` with a heading, paragraph, and link list
- [ ] `<nav>` with 4 links; `<footer>` with 2 links
- [ ] A comment or note explaining your `<aside>` placement choice
- [ ] No CSS

## Acceptance criteria

- Each `<article>` reads sensibly on its own if you delete everything around it.
- The page has one, and only one, `<main>`.
- A screen-reader user could jump straight to navigation, main content, or the aside.

## Hints

<details><summary>Show hint</summary>

Post previews are the classic example of `<article>` — each one could appear on its own on a "single post" page later. The author bio is `<aside>` because the page still makes sense without it.
</details>

## Stretch (optional)

Give each `<article>` its own nested `<header>` (title + date) and `<footer>` (the "Read more" link + a fake "3 comments" line).
