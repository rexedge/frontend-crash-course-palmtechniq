# Assignment 15 — Three-Page Mini-Site

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1 hr · 🧵 keep this folder
**Prereqs:** Assignment 08 (About Me) done
**Build in:** `work/15-three-page-mini-site/` — `index.html`, `hobbies.html`, `contact.html`

---

## Goal

Build a small site of three separate HTML pages that link to each other, so you can click around without touching the address bar.

## What you'll practice

- Multiple `.html` files in one folder
- **Relative links** between local pages (`href="hobbies.html"` — just the file name, no `https://`)
- Keeping a repeated block (the nav links) consistent across pages

## Instructions

1. In the folder, create three files: `index.html`, `hobbies.html`, `contact.html`.
2. Each page has its own `<h1>` and content built from **Class 1 tags only**:
   - `index.html` — a short welcome: `<h1>`, a couple of `<p>`, and a `<ul>` of "what's on this site"
   - `hobbies.html` — `<h1>`, and 2–3 hobbies each with an `<h2>`, a `<p>`, and an `<img>` (with `alt`)
   - `contact.html` — `<h1>`, a `<p>`, and a `<ul>` of ways to reach you, each `<li>` containing an `<a>` (to real sites standing in for email/social)
3. At the **top of every page**, put the same set of three links pointing at the other pages:

```html
<p>
    <a href="index.html">Home</a>
    <a href="hobbies.html">Hobbies</a>
    <a href="contact.html">Contact</a>
</p>
```

4. Open `index.html` with Live Server and navigate the whole site using only those links.

## Requirements

- [ ] 3 files, each a valid standalone HTML page with its own `<title>` and `<h1>`
- [ ] The same 3-link nav block at the top of all 3 pages (same links, same order)
- [ ] Links between pages use **just the file name** (no `http`, no slashes)
- [ ] Each page's content uses only Class 1 tags
- [ ] Every `<img>` has a written `alt`

## Acceptance criteria

- From `index.html`, you can reach both other pages and get back, using only the nav links.
- No link 404s (the browser doesn't show "Cannot GET" or a broken page).
- Each page stands on its own if opened directly.

## Hints

<details><summary>Show hint</summary>

A link to a file sitting in the same folder is just its name: `<a href="contact.html">Contact</a>`. If a link fails, check the file name matches **exactly**, including the `.html` and the capitalisation.
</details>

## Stretch (optional)

Add a fourth page `favourites.html` (favourite films/books/music as three `<ol>` rankings) and add it to the nav block on all four pages. Notice how updating the nav everywhere by hand is tedious — later classes and tools solve that.
