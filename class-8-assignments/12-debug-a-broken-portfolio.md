# Assignment 12 — Debug: A Broken Portfolio

**Type:** Debug · **Difficulty:** ⭐⭐⭐ · **Time:** ~1 hr
**Prereqs:** Class 8 §8 (the three "break it" experiments) and §13 (troubleshooting)
**Build in:** `work/12-debug-a-broken-portfolio/notes.md` — and a copy of your own portfolio to try things in

---

## Goal

Each case is the finished portfolio from the lesson with **one** thing wrong. Work out the cause, **fix it**, and write one sentence explaining it in your own words. Try before opening the answer.

These are capstone bugs. In most of them no single file is wrong: two files **disagree with each other**. So for each case, ask: which two things are supposed to match?

Start in the Console. Only **two** of the eight give a red error. For the other six, open the Elements panel and look at what is really on the element: its classes, and which CSS rules are winning.

---

## (a) The "Projects" link in the nav does nothing

```html
<nav class="site-nav">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#project">Projects</a>
    <a href="#contact">Contact</a>
</nav>

<!-- ...further down... -->

<section id="projects">
    <h2>Projects</h2>
```

<details><summary>Show answer</summary>

The `href` says `#project`. The `id` is `projects`. They have to match exactly — every letter, capitals included. The address bar does gain `#project`, but nothing on the page has that `id`, so the page stays where it is.

There's no error, because nothing is broken as far as the browser is concerned: a link to a place that doesn't exist is allowed. Change the `href` to `#projects`.
</details>

---

## (b) Click "CSS": the line says "Showing 2 of 6 projects" — but all six cards are still there

```css
.hidden {
    display: none;
}

/* ...further down the file... */

.project {
    display: flex;
    flex-direction: column;
    padding: 16px;
}
```

<details><summary>Show answer</summary>

The JavaScript is doing its job. Look in the Elements panel: four of the cards really do have the class `hidden`, and the count is right.

The problem is the order of the stylesheet. `.hidden` and `.project` are both a single class, so they're equally strong, and when two equal rules disagree the **later** one wins. `.project` says `display: flex`, it comes later, and so it beats `display: none`.

Move `.hidden` to the very end of the stylesheet. (The contact form still hides properly in this broken version, because no other rule sets its `display`. That's what makes this bug confusing.)
</details>

---

## (c) Dark mode: the page goes dark, but the project cards stay white — and their text almost vanishes

```css
.dark {
    color: #eeeeee;
    background-color: #121212;
}

.project .dark {
    background-color: #1e1e1e;
    border: 1px solid #333333;
}
```

<details><summary>Show answer</summary>

The second selector is backwards. `.project .dark` means "an element with the class `dark`, **inside** a `.project`". But `dark` is on the `<body>`, which is *outside* the cards, so the rule matches nothing.

Read a descendant selector from left to right as "inside": `.dark .project` is "a project card inside a dark page". That's the one you want.

The text fades because the cards still inherit the pale text colour from `<body>`. Pale grey text on a white card is close to invisible.
</details>

---

## (d) The theme button is dead — and so are the filter and the form, which reloads the page

The Console says `Uncaught TypeError: Cannot read properties of null (reading 'addEventListener')`.

```html
<button type="button" id="theme-toggle">🌙 Dark</button>
```

```js
console.log("app.js loaded");

const themeToggle = document.querySelector("#themeToggle");

themeToggle.addEventListener("click", () => {
    document.body.classList.toggle("dark");
});

// ...the contact form and the projects filter are below...
```

<details><summary>Show answer</summary>

The `id` in the HTML is `theme-toggle`. The selector asks for `themeToggle`. Nothing matches, so `querySelector` gives back `null`, and the next line tries to call `addEventListener` on nothing.

The important part is what happens next: **the script stops at that line.** Everything below it never runs. No filter. No listener on the form — which means no `preventDefault`, which is why the form goes back to reloading the page. One typo, three dead features.

The variable is called `themeToggle`, in camelCase, because that's how JavaScript names are written. The string inside `querySelector` is a CSS selector, and it has to match the HTML: `"#theme-toggle"`.

Whenever several things break at once, fix the **first** red error first.
</details>

---

## (e) The "JavaScript" filter says "Showing 0 of 6 projects"

```html
<button type="button" class="filter">JavaScript</button>

<!-- ...and in two of the cards... -->

<p class="tag">Javascript</p>
```

<details><summary>Show answer</summary>

Look at the capital `S`. The filter keeps a card when its tag `===` the button's text, and `===` compares strings exactly: `"Javascript"` is not `"JavaScript"`.

There's no error, because the code is correct. It's the **data** that doesn't match. Make the text of each tag identical to the text of its button.

If you'd like the filter to be more forgiving, compare lower-case copies of both sides: `tags[i].textContent.trim().toLowerCase() === wanted.toLowerCase()`.
</details>

---

## (f) Fine at 375px — but at 320px the whole page scrolls sideways

```css
main {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 clamp(16px, 5vw, 48px);
}

.projects {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(330px, 1fr));
    gap: 24px;
}
```

<details><summary>Show answer</summary>

`minmax(330px, 1fr)` is a promise that no column will ever be narrower than 330px. On a 320px phone, with 16px of padding on each side, there is only 288px of room. The column keeps its promise, sticks out past the edge of the screen, and the page scrolls sideways.

At 375px there happens to be just enough room — about 337px — which is why it looked fine.

Use a smaller minimum. 260px fits a 320px screen with room to spare. And always test at **320px**, not just 375px: some small phones are that narrow.
</details>

---

## (g) Sending the form does nothing

The Console says `Uncaught TypeError: Cannot read properties of undefined (reading 'trim')`.

```html
<header class="site-header" id="top">
    <p class="brand" id="name">Ada Lovelace</p>

<!-- ...further down... -->

<label for="name">Full name</label>
<input type="text" id="name" name="name" required>
```

```js
const nameInput = document.querySelector("#name");

contactForm.addEventListener("submit", (event) => {
    event.preventDefault();

    const visitorName = nameInput.value.trim();
```

<details><summary>Show answer</summary>

Two elements have `id="name"`. `querySelector` returns the **first** match, and the first one is the `<p>` in the header, not the input.

A paragraph has no `.value`, so `nameInput.value` is `undefined` — and `undefined` has no `.trim()`. That's the error. The page doesn't reload, because `preventDefault` ran before the line that failed.

An `id` must be unique on the page. Take the `id` off the paragraph (it has a class already), or give it a different one.

The same duplicate breaks the label too: `for="name"` now points at the paragraph, so clicking `Full name` no longer puts the cursor in the box.
</details>

---

## (h) In dark mode, the hero button's text turns pale blue — on a blue button

```html
<a href="#projects" class="button">See my projects</a>
```

```css
.button {
    color: #ffffff;
    background-color: #1a56db;
}

.dark a {
    color: #8ab4f8;
}
```

<details><summary>Show answer</summary>

The hero button is a link, so `.dark a` applies to it. And `.dark a` — a class plus an element — is **more specific** than `.button`, which is one class. The more specific rule wins, whatever order the two are in. So in dark mode the button's white text is replaced with the pale blue meant for ordinary links.

Add a rule that's stronger again, after the others:

```css
.dark .button {
    color: #ffffff;
}
```

Two classes beat a class plus an element. In the Elements panel you can watch this happen: the losing `color` is shown crossed out.
</details>

---

## Acceptance criteria

- For each of the eight cases, your notes have one sentence, in your own words, that names the cause.
- For each case, you can say which **two things** were supposed to match.
- You have reproduced at least three of the bugs in a copy of your own portfolio, seen the symptom yourself, and fixed it.
- You can name the two cases that give a red error, and explain why the other six don't.
