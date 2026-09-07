# Assignment 09 — Recipe Page

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 1 §4 (all core tags)
**Build in:** `work/09-recipe-page/index.html`

---

## Goal

Build a recipe page that uses the *right* list type for each part: an unordered list for ingredients, an ordered list for steps.

## What you'll practice

- Choosing `<ul>` vs `<ol>` based on meaning
- Mixing headings, paragraphs, lists, a link, and an image on a real-world page
- Keeping a longer document tidy with indentation

## Instructions

Pick a dish you can actually make. Build `index.html` with:

- `<h1>` — the dish name
- one or two `<p>` — a short description (what it is, when you eat it, why you like it)
- `<h2>` `Ingredients` + a `<ul>` — list every ingredient with a rough amount as plain text, e.g. `2 cups rice`, `1 tsp salt` (order doesn't matter → unordered)
- `<h2>` `Steps` + an `<ol>` — the method, one step per `<li>`, in order (order is everything → ordered)
- `<h2>` `Source` + an `<a>` — a link to a recipe site, with descriptive link text
- one `<img>` of the finished dish, with a written `alt`

## Requirements

- [ ] `<h1>` dish name + description paragraph(s)
- [ ] `Ingredients` as a `<ul>` (amounts included as text)
- [ ] `Steps` as an `<ol>`
- [ ] `Source` with a real `<a>` link
- [ ] One `<img>` with `src` and a specific `alt`
- [ ] Valid skeleton; all tags closed in order; no CSS or non–Class-1 tags

## Acceptance criteria

- Ingredients show as bullets; steps show as numbers.
- Someone could follow the page and cook the dish.
- Swapping the two list types would look obviously wrong — that's how you know you chose correctly.

## Hints

<details><summary>Show hint</summary>

Amounts go *in the text* of the `<li>` (`<li>2 cups rice</li>`) — there's no special "amount" tag in Class 1. Keep each ingredient to one `<li>`.
</details>
