# Assignment 08 — Multi-Page

**Type:** Stretch · **Difficulty:** ⭐⭐⭐ · **Time:** ~2 hr
**Prereqs:** a finished portfolio ([Assignment 01](01-personal-portfolio.md)); Class 1 (linking pages)
**Build in:** `work/08-multi-page/` — a **copy** of your finished portfolio

---

## Goal

Turn your one-page portfolio into a small site of four pages that look and behave like one site: the same header and footer everywhere, one stylesheet, and JavaScript that works on every page.

## What you'll practice

- Splitting one page into several without the design drifting apart
- Links between pages, and links to a place on **another** page
- Showing the visitor which page they're on
- JavaScript shared between pages that don't all have the same elements

## Instructions

1. Copy your finished portfolio into `work/08-multi-page/`. Keep the original as it is.
2. Make four pages:
   - `index.html` — the header, the hero, About, and Skills
   - `projects.html` — the project cards and your third interaction
   - `project-detail.html` — a full write-up of **one** project: what it is, a screenshot, what you learned, and a link to the project itself
   - `contact.html` — the form
3. Give every page the **same** `<header>` and `<footer>`. With plain HTML there's no way to share them, so copy them — carefully, and identically.
4. Change the nav. The links now go to pages: `index.html`, `projects.html`, `contact.html`. A link to a section on a different page uses both parts: `index.html#about`.
5. Mark the current page. On each page, add `class="current"` to that page's own nav link, and style `.current` so it stands out.
6. Every page uses the one `style.css`.
7. Link at least one project card to `project-detail.html`, and give that page a link back to `projects.html`.
8. Sort out the JavaScript — see the hint. Then open **every** page with the Console showing.

## Requirements

- [ ] Four pages, each with its own `<title>` and exactly one `<h1>`
- [ ] The header and the footer are identical on every page, apart from which link is `current`
- [ ] Every page links to every other page, and no link is broken
- [ ] One shared stylesheet; no page has styles of its own
- [ ] The theme toggle works on **every** page
- [ ] The form's thank-you message and your third interaction still work on their pages
- [ ] **No red in the Console on any page**
- [ ] Every page works from 320px to 1440px

## Acceptance criteria

- You can reach every page from every other page in one click.
- On each page, one nav link — the right one — is marked as current.
- `index.html#about`, typed into the address bar or followed from another page, opens the home page already scrolled to About.
- Open each of the four pages and look at the Console: `app.js loaded`, and nothing red.
- Change one colour in `style.css`: all four pages change.

## Hints

<details><summary>Show hint — why your JavaScript breaks, and two ways to fix it</summary>

Your `app.js` was written for a page that had everything on it. Now the contact form exists on only one page. On the other three, `document.querySelector("#contact-form")` gives back `null`, the next line throws `Cannot read properties of null (reading 'addEventListener')` — and, as you know, one red error stops everything below it. If the theme code comes after the form code, the theme toggle dies on three pages out of four.

**Fix 1: one small file per feature.** Split `app.js` into `theme.js`, `contact.js`, and `projects.js`. Each page loads only the scripts it has the elements for:

```html
<!-- on contact.html -->
<script src="theme.js"></script>
<script src="contact.js"></script>
```

**Fix 2: check before you use it.** Keep one file, and wrap each feature in an `if`:

```js
const contactForm = document.querySelector("#contact-form");

if (contactForm !== null) {
    contactForm.addEventListener("submit", (event) => {
        event.preventDefault();
        // ...
    });
}
```

Either is fine. The first keeps each file short; the second keeps one file to look after.
</details>

<details><summary>Show hint — two things that will surprise you</summary>

- **The theme resets every time you change page.** Each page load starts again from the HTML, and nothing is remembered. That's expected with what this course taught. Remembering it needs `localStorage` *(stretch — beyond this course)*.
- **You'll fix a typo in the header on one page and forget the other three.** Every multi-page site built by hand has this problem. It's one of the real reasons the tools you'll meet later exist.
</details>

## Stretch (optional)

- Write a detail page for every project.
- *(stretch — beyond this course)* Make the theme survive a change of page. Look up `localStorage.setItem` and `localStorage.getItem`.
