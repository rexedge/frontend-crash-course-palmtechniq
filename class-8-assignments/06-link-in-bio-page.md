# Assignment 06 — Link-in-Bio Page

**Type:** Variant · **Difficulty:** ⭐⭐ · **Time:** ~1 hr
**Prereqs:** Class 4 §5–§6 (centring); Class 5 §10–§11; Class 7 §6–§7; Class 8
**Build in:** `work/06-link-in-bio-page/index.html` + `style.css` + `app.js`

---

## Goal

Build the single-screen page people link to from a social profile: a picture, a name, one line of bio, and a stack of big buttons that lead to everything else. It's small enough to finish in one sitting — a good choice if you're short on time, and a useful page to actually have.

## What you'll practice

- Centring a column in the middle of the screen, both ways
- Links styled as large, easy-to-tap buttons
- A theme toggle, and a show / hide button whose text keeps up

## Instructions

1. **The HTML.** A `<main class="card">` holding: an avatar `<img>`, your name in an `<h1>`, a one-line bio, a `<div class="links">` with at least four links, a `<button type="button" id="email-toggle">Show my email</button>`, and a hidden paragraph with your email address in it. Add a theme toggle button too.
2. **Centre it.** Make the `<body>` at least as tall as the screen with `min-height: 100vh`, turn it into a flex container, and centre its content on both axes. Give the card `width: 100%` and a `max-width` of about `24rem`.
3. **The avatar.** A fixed `width`, `aspect-ratio: 1 / 1`, and `object-fit: cover`, centred with `margin: 0 auto`.
4. **The links.** Stack them in a flex column with a `gap`. Each link is `display: block` with generous padding, a border, and no underline — a big target for a thumb.
5. **The theme toggle.** A `dark` class on `<body>`, with both themes in the CSS.
6. **Show my email.** Clicking the button shows the paragraph and changes the button's text to `Hide my email`. Clicking again reverses both.

## Requirements

- [ ] The whole card sits in the middle of the screen, and still fits at 320px wide
- [ ] At least four links, each one saying where it goes
- [ ] Every link is big enough to tap comfortably: aim for at least 44px tall
- [ ] The theme toggle restyles the page, the links, and the buttons
- [ ] The email is hidden as the page loads, and the button's text always says what clicking it will do
- [ ] The avatar has an `alt`
- [ ] No red in the Console

## Acceptance criteria

- At 375px and at 1280px, the card is centred left-to-right **and** top-to-bottom.
- At 320px nothing is cut off, and there's no horizontal scrollbar.
- Click `Show my email`: the address appears, and the button reads `Hide my email`. Click again: it's gone, and the button reads `Show my email`.
- In dark mode, every link is still easy to read.
- Make the window very short: the card is never cut off at the top — the page scrolls instead.

## Hints

<details><summary>Show hint</summary>

The centring is the "perfect centring" pattern from Class 4, on the `<body>` itself:

```css
body {
    margin: 0;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 24px 16px;
}
```

It's `min-height`, not `height`, on purpose. With a fixed `height`, a card taller than the screen would be cut off. With `min-height`, the body simply grows.

The email button is the "Read more" toggle from the Class 7 homework: toggle `hidden` on the paragraph, then ask the paragraph which state it's in — `classList.contains("hidden")` — and set the button's text to match.
</details>

## Stretch (optional)

- *(stretch — beyond this course)* A **"Copy my email"** button that puts the address on the clipboard, and briefly says `Copied!`. Look up `navigator.clipboard.writeText` — and timers, for changing the text back.
- *(stretch — beyond this course)* A round avatar. Look up `border-radius`.
- Put it online ([Assignment 07](07-deploy-it.md)), and use it as the link in your real profiles.
