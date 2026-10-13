# Assignment 03 — Small-Business Landing Page

**Type:** Variant · **Difficulty:** ⭐⭐⭐ · **Time:** ~3 hr
**Prereqs:** Class 2 §6 (tables); Class 4; Class 5 §13–§14; Class 7 §7, §11; Class 8
**Build in:** `work/03-small-business-landing-page/index.html` + `style.css` + `app.js`

---

## Goal

Build a one-page site for a made-up local business — a café, a gym, a salon, a repair shop. It's the kind of page a real client would ask you for: what we do, when we're open, where we are, how to reach us.

## What you'll practice

- A navigation menu that folds away behind a `Menu` button on a phone
- A table used for what tables are for: opening hours
- A row of testimonials with Flexbox, and a grid of services
- Two JavaScript features on one page, without them getting in each other's way

## Instructions

1. **The header.** The business name, a `<button type="button" id="menu-toggle">☰ Menu</button>`, and a `<nav class="site-nav">` with in-page links to each section.
2. **The sections**, each with an `id`:
   - a hero with a headline and a call-to-action link
   - **services** — at least four, in a Grid
   - **hours** — a `<table>` with a `<caption>`, and `<th scope="col">` headers for `Day` and `Hours`
   - **testimonials** — three short quotes in a Flexbox row that wraps
   - **find us** — an address, and a plain box where a map would go
   - **questions** — an FAQ of at least four questions
   - **contact** — a form with a thank-you message
3. **The mobile menu, in CSS.** Mobile-first: the nav is `display: none`, and the header gets a rule that shows it when the header has the class `nav-open`. Inside a `min-width` media query, the nav is always shown and the `Menu` button is hidden.
4. **The mobile menu, in JavaScript.** Clicking `Menu` adds or removes `nav-open` on the header, and the button's text switches between `☰ Menu` and `✕ Close`. Choosing a link closes the menu again.
5. **The FAQ.** Each question is a button that shows and hides its own answer — the accordion from [Class 7, Assignment 12](../class-7-assignments/12-show-hide-accordion.md).

## Requirements

- [ ] Every nav link jumps to its section
- [ ] Below your breakpoint: the links are hidden until `Menu` is clicked
- [ ] From your breakpoint up: the links are always showing, and there is no `Menu` button
- [ ] The button's text always says what clicking it will do
- [ ] Choosing a link on a phone closes the menu
- [ ] The opening hours are a real `<table>`, with a caption and header cells
- [ ] Every FAQ question opens its own answer
- [ ] The contact form says thank you without reloading
- [ ] No red in the Console, and no horizontal scrollbar from 320px to 1440px

## Acceptance criteria

- At 375px: only the name and `☰ Menu` show in the header. Click it: the links appear in a column underneath, and the button reads `✕ Close`. Click a link: the page jumps there, and the menu is closed again.
- At 1024px: the links sit in a row beside the name, and the `Menu` button is nowhere to be seen.
- Open the menu at 375px, then widen the window past your breakpoint: the links are in a row, as normal.
- The hours table has a caption that names it, and `Day` and `Hours` are header cells — so a screen reader can announce what each cell belongs to.

## Hints

<details><summary>Show hint — the menu's CSS</summary>

Why not just toggle `.hidden` on the nav? Because `.hidden` is the last rule in your stylesheet, so it would hide the links on a wide screen too. The menu needs a class that only means something on a phone:

```css
/* Phones: the links stay hidden until the header has the nav-open class */
.site-nav {
    display: none;
    width: 100%;
    flex-direction: column;
    gap: 8px;
}

.nav-open .site-nav {
    display: flex;
}

/* From 700px: the links are always showing, and the Menu button is not needed */
@media (min-width: 700px) {
    .site-nav {
        display: flex;
        width: auto;
        flex-direction: row;
        gap: 16px;
    }

    #menu-toggle {
        display: none;
    }
}
```

The header itself is `display: flex` with `flex-wrap: wrap`, so a nav that's `width: 100%` drops onto a line of its own.
</details>

<details><summary>Show hint — the menu's JavaScript</summary>

Closing the menu happens in two places — the button, and every link — so give it a function of its own:

```js
const siteHeader = document.querySelector(".site-header");
const menuToggle = document.querySelector("#menu-toggle");
const navLinks = document.querySelectorAll(".site-nav a");

function closeMenu() {
    siteHeader.classList.remove("nav-open");
    menuToggle.textContent = "☰ Menu";
}

menuToggle.addEventListener("click", () => {
    if (siteHeader.classList.contains("nav-open")) {
        closeMenu();
    } else {
        siteHeader.classList.add("nav-open");
        menuToggle.textContent = "✕ Close";
    }
});

navLinks.forEach((link) => {
    link.addEventListener("click", closeMenu);
});
```

Notice `closeMenu` with no brackets in the last listener: you're handing the function over, not calling it.
</details>

## Stretch (optional)

- Make the FAQ a true accordion: opening one answer closes the others.
- Mark today's row in the hours table. *(stretch — beyond this course)* Look up `new Date().getDay()`.
- *(stretch — beyond this course)* A real map. Look up how to embed one with an `<iframe>`.
