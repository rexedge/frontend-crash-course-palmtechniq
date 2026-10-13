# Assignment 01 — Personal Portfolio

**Type:** Core · **Difficulty:** ⭐⭐⭐ · **Time:** ~5–6 hr, spread over the week · 🧵 the course deliverable
**Prereqs:** all of Classes 1–7; Class 8 §2–§10
**Build in:** `work/01-personal-portfolio/` — `index.html` + `style.css` + `app.js`, with `images/` and `projects/` folders

---

## Goal

Build **your own** portfolio: one responsive, interactive page that says who you are, shows what you've made, and lets someone get in touch. It uses everything from the course, and it's the page you'll point to and say "I built this".

The lesson builds an example for a made-up student. Use it to learn the method. Then build yours from an empty folder: your words, your colours, your projects, your third interaction.

## What you'll practice

- Planning a page before you type it
- Working in milestones: structure, then look, then layout, then behaviour
- Keeping three files tidy as a page grows
- Testing properly: every width, both themes, a clean Console

## Instructions

Work through the five milestones in order. Don't start one until the one before it is finished. After each, make a save point: copy the whole folder and add the milestone to the copy's name.

**Before you start.** Write your content in a text file: your name, a one-line pitch, a short bio, six to eight skills, and at least three projects with a sentence about each. Sketch the page on paper, as a phone and as a wide screen. Copy your finished projects into `projects/` — [work/README.md](work/README.md) lists where to find them.

**Milestone 1 — Content first, no CSS**

1. Write the whole page in HTML: a `<header>` with your name and a `<nav>`; a `<main>` with a hero, then `#about`, `#skills`, `#projects`, and `#contact`; a `<footer>`.
2. Make every nav link an in-page link, and give each section the matching `id`.
3. Use your real words. Placeholder *pictures* are fine for now.
4. Add `<script src="app.js"></script>` at the end of `<body>`, and put `console.log("app.js loaded");` in the file.

*Done when:* with no CSS at all, the page reads sensibly from top to bottom, every nav link jumps to its section, and the Console shows `app.js loaded` with no red.

**Milestone 2 — Base styles**

1. Choose a type scale, a spacing scale, and a palette. Write them in a comment at the top of `style.css`.
2. Add the `box-sizing` reset and the `img` reset.
3. Style what applies everywhere: `body`, the headings, paragraphs, links, form fields, buttons, and the centred column.

*Done when:* at 375px the page is one tidy column, no image is wider than the screen, and every size you used is on your scales.

**Milestone 3 — Layout and responsive**

1. Lay out the header with Flexbox, and the project cards with Grid.
2. Lay out anything else that needs it: the skills, the About section, the footer.
3. Add media queries only where the layout has to change shape: `min-width`, smallest first, after the base rules.

*Done when:* nothing overlaps or overflows from 320px to 1440px, and both the nav and the project cards are arranged differently on a phone and on a wide screen.

**Milestone 4 — JavaScript**

1. Write the classes in the CSS first: the dark theme, and `.hidden` as the very last rule.
2. Build the theme toggle. Test it, and check **every** part of the page in the dark.
3. Build the contact form's thank-you message. Test it.
4. Build your third interaction. Test it.

*Done when:* all three work, in both themes, and `app.js loaded` appears only once however much you click.

**Milestone 5 — Polish and test**

Go down the checklist in Section 9 of the lesson: every width, every click, the headings, the `alt` text, the leftover code. Then hand your phone to someone who hasn't seen the page, say nothing, and watch.

## Requirements

**Structure**
- [ ] A `<header>` with your name or logo, and a `<nav>` of in-page links (at least `#about`, `#projects`, `#contact`)
- [ ] A `<main>` that contains:
  - [ ] a hero `<section>` with the page's one `<h1>`, a one-line pitch, and a call-to-action link
  - [ ] `#about` — a short bio and a photo
  - [ ] `#skills` — a list or a grid of skills
  - [ ] `#projects` — **at least three** project cards: a title, a picture, a description, and a link
  - [ ] `#contact` — a contact form with a `<label>` on every field, and validation attributes
- [ ] A `<footer>` with a copyright line and two or three links

**CSS**
- [ ] One external `style.css`; no `style="…"` attributes
- [ ] A type scale and a spacing scale, written in a comment at the top and used consistently
- [ ] `box-sizing: border-box` on everything
- [ ] The nav laid out with **Flexbox**
- [ ] The project cards laid out with **Grid**
- [ ] Responsive: sensible on a phone (400px and under), a tablet (about 768px), and a desktop (1200px and over). The nav and the projects grid both adapt
- [ ] The viewport `<meta>` tag is there, and there's no horizontal scrollbar at any width
- [ ] No image ever overflows its container

**JavaScript** (`app.js`, at the end of `<body>` or with `defer`)
- [ ] A light / dark theme toggle: a class on `<body>` that restyles **every** part of the page
- [ ] The contact form: on `submit`, `preventDefault`, then show a thank-you message that includes the visitor's name
- [ ] **One more** interaction of your choice: a projects filter, a "more details" toggle on each card, a mobile menu, or a screenshot gallery
- [ ] No colours or sizes in the JavaScript — it only switches classes

## Acceptance criteria

- It opens with Live Server with **zero** Console errors.
- Every nav link jumps to the right section.
- Drag the window from 320px to 1440px: nothing breaks, overlaps, or overflows — in both themes.
- A stranger could read it and know who you are and what you can do.
- No sentence, colour, or project is left over from the lesson's example.
- Every line is your own, typed by hand, and you can explain any of them if asked.

## Hints

<details><summary>Show hint — choosing and building your third interaction</summary>

You've built all four of these before. Pick the one that suits your content.

**A projects filter** — buttons that show one category of card. The lesson builds it in Section 8. It suits you if you have six or more projects that fall into clear groups.

**"More details" on each card** — a button that shows and hides an extra paragraph: what the project taught you. It's the accordion from [Class 7, Assignment 12](../class-7-assignments/12-show-hide-accordion.md), with one addition: the button's text changes too.

```js
const detailToggles = document.querySelectorAll(".details-toggle");
const details = document.querySelectorAll(".details");

detailToggles.forEach((toggle, i) => {
    toggle.addEventListener("click", () => {
        details[i].classList.toggle("hidden");

        if (details[i].classList.contains("hidden")) {
            toggle.textContent = "More details";
        } else {
            toggle.textContent = "Hide details";
        }
    });
});
```

**A mobile menu** — a `Menu` button that shows and hides the nav on a phone. [Assignment 03](03-small-business-landing-page.md) has the recipe. The catch: you can't use `.hidden` for this one, because the links must always show on a wide screen.

**A screenshot gallery** — one large picture of a project, and a row of thumbnails that swap it. That's [Class 7, Assignment 15](../class-7-assignments/15-image-gallery.md), dropped into a section of your page.
</details>

<details><summary>Show hint — if something isn't working</summary>

- **Nothing interactive works at all.** Look at the Console. One red error stops the whole of `app.js`, so everything below that line is dead too. Fix the first error first.
- **The dark theme misses a box.** Every part of the page that has its own `background-color` needs its own `.dark …` rule.
- **A card won't hide.** `.hidden` has to be the last rule in the stylesheet, or the card's own `display` beats it.
- **A nav link does nothing.** The `href` and the `id` don't match exactly. Check the capitals.

[Assignment 12](12-debug-a-broken-portfolio.md) has all of these, and four more, with full answers.
</details>

## Stretch (optional)

These are popular on portfolios, but each one needs something this course never taught. Finish the page first, then look them up:

- *(stretch)* **A theme that's still dark after a reload** — look up `localStorage`.
- *(stretch)* **A "back to top" button that appears as you scroll** — look up the `scroll` event, `window.scrollY`, and `position: fixed`.
- *(stretch)* **A pop-up viewer that covers the page** — look up `position: fixed`.
- *(stretch)* **A typing or count-up animation in the hero** — look up `setInterval`.

For more to do after that, see the stretch goals: [07](07-deploy-it.md), [08](08-multi-page.md), [09](09-real-content-pass.md), [10](10-accessibility-pass.md), and [11](11-performance-and-polish.md).
