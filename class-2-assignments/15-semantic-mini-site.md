# Assignment 15 — Rebuild the Mini-Site, Semantically

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1 hr · 🧵 keep this folder
**Prereqs:** Class 1 three-page mini-site; Assignments 07 and 11
**Build in:** `work/15-semantic-mini-site/` (multiple files)

---

## Goal

Rebuild your Class 1 three-page mini-site so all three pages share a consistent semantic structure, and the contact page holds the full form from Assignment 11.

## What you'll practice

- Repeating a consistent `<header>` + `<nav>` + `<footer>` across pages
- Linking local pages with relative links (`href="about.html"`)
- Putting a real form inside a multi-page site

## Instructions

1. Create three files in the folder: `index.html`, `about.html`, `contact.html`.
2. Every page has the **same** `<header>` (site name + `<nav>` linking all three pages) and the **same** `<footer>`. Type them out on each page — consistency is the exercise.
3. Each page has exactly one `<main>` with content unique to that page:
   - `index.html` — a welcome `<section>`, and a `<section>` with a `<ul>` of "what's on this site"
   - `about.html` — 2–3 `<section>`s about you or the site's subject
   - `contact.html` — a `<section>` intro + the complete contact `<form>` from Assignment 11
4. In the `<nav>`, mark the current page somehow with plain HTML (e.g. its link is plain text, not an `<a>` — since you're already on it).
5. Click through all three pages in the browser using only the nav.

## Requirements

- [ ] 3 pages, each with the upgraded skeleton and exactly one `<main>`
- [ ] Identical `<header>`/`<nav>`/`<footer>` on all three (same links, same order)
- [ ] Relative links between pages work (no `http`, just file names)
- [ ] `contact.html` contains the full validated form from Assignment 11
- [ ] The current page is visually distinguishable in the nav (without CSS — e.g. not a link)
- [ ] No CSS anywhere

## Acceptance criteria

- Starting from `index.html` in Live Server, you can reach every page and come back, using only nav links.
- Every page passes the Assignment 07 structure checks.
- The contact form passes the Assignment 11 acceptance criteria.

## Hints

<details><summary>Show hint</summary>

A link to a file in the same folder is just the file name: `<a href="about.html">About</a>`. No slashes, no `http`. If it 404s, check the file name matches exactly, including `.html`.
</details>

## Stretch (optional)

Add a fourth page `projects.html` with 3 `<article>` project cards, and add it to the nav on every page.
