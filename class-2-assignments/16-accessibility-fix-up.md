# Assignment 16 — Accessibility Fix-up

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 2 §3–10
**Build in:** `work/16-accessibility-fix-up/index.html`

---

## Goal

Take a page that "works" visually but is structurally poor, and rewrite it with proper landmarks, real labels, correct input types, and an accessible table.

## What you'll practice

- Spotting non-semantic "it renders fine" HTML
- Replacing `<p>`-as-heading and `<p>`-as-nav with real elements
- Fixing unlabelled form controls and wrong input types
- Adding `scope` and a `<caption>` to a bare table

## The starting page (copy this into your file, then fix it)

```html
<!DOCTYPE html>
<html>
<head><title>Super Store</title></head>
<body>
  <p>SUPER STORE</p>
  <p>Home | Shop | Contact</p>

  <p>Our Products</p>
  <table>
    <tr><td>Name</td><td>Price</td></tr>
    <tr><td>Mug</td><td>$8</td></tr>
    <tr><td>Cap</td><td>$15</td></tr>
    <tr><td>Tote bag</td><td>$12</td></tr>
  </table>

  <p>Join our newsletter</p>
  Email: <input>
  <input type="button" value="Go">

  <p>&copy; Super Store</p>
</body>
</html>
```

## Instructions

Rewrite the page so that:

1. The skeleton is upgraded (`lang`, `<meta charset>`).
2. "SUPER STORE" is the site name in a `<header>`, with the three nav items in a real `<nav>` + `<ul>` of `<a>` links.
3. "Our Products" is a real heading inside `<main>`.
4. The product table has a `<caption>`, a `<thead>` with `<th scope="col">`, a `<tbody>`, and each product name is a `<th scope="row">`.
5. The newsletter area is a `<form>` with:
   - a real `<label for>` linked to the email `<input type="email" required>`
   - a proper `<button type="submit">` (not `type="button"`)
6. The copyright line is in a `<footer>`.

## Requirements

- [ ] Zero `<p>` elements used as headings or navigation
- [ ] One `<main>`, with `<header>` and `<footer>` outside it
- [ ] Table has caption, `thead`/`tbody`, and correct `scope` on all header cells
- [ ] Email input is labelled, typed `email`, and `required`
- [ ] Submit button actually submits (inside the form, `type="submit"`)
- [ ] No CSS

## Acceptance criteria

- Every piece of text now sits in the element that matches its meaning.
- Clicking the "Email" label focuses the input.
- The table reads correctly cell-by-cell (item name → price) for a screen reader.

## Hints

<details><summary>Show hint</summary>

Ask of each line: *what is this, really?* "SUPER STORE" is a site title → `<h1>` in `<header>`. "Home | Shop | Contact" is navigation → `<nav>` with links. "Our Products" introduces a section → `<h2>` (or `<h1>` if it's the page's main heading).
</details>
