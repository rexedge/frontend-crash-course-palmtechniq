# Assignment 10 — Accessibility Pass

**Type:** Stretch · **Difficulty:** ⭐⭐⭐ · **Time:** ~1.5 hr
**Prereqs:** a finished portfolio ([Assignment 01](01-personal-portfolio.md)); Class 2 §3–§4, §8
**Build in:** `work/01-personal-portfolio/` — make a save point first

---

## Goal

Make sure your portfolio works for people who don't use it the way you do: with a keyboard instead of a mouse, with a screen reader instead of a screen, or with eyesight that needs stronger contrast. Most of what's needed is HTML you already know. This assignment is about checking that you really used it.

## What you'll practice

- Using a page with the keyboard only
- Measuring colour contrast, instead of guessing
- Checking headings, labels, and `alt` text the way assistive software reads them
- Reporting problems in words, not in colour alone

## Instructions

Work through the six checks in order. Write down what you find before you fix anything.

**1. Keyboard only.** Put the mouse out of reach. Reload the page, and use only `Tab`, `Shift + Tab`, `Enter`, and `Space`.
- Can you reach every link, every button, and every form field?
- Can you always **see** where you are? The browser draws a focus ring around the current element.
- Is the order sensible: top to bottom, in the order things appear?
- Can you switch the theme, use your third interaction, and send the form?

**2. Clickable things are real controls.** Anything that isn't a link, a button, or a form field can't be reached with `Tab`. If you put a click listener on an `<img>`, a `<div>`, or a `<p>`, wrap it in a `<button type="button">`, or turn it into one.

**3. Contrast.** In dev tools, select a piece of text, and click the small coloured square beside its `color` in the Styles panel. The colour picker shows a **contrast ratio**. Aim for at least **4.5 : 1** for ordinary text, and **3 : 1** for large headings. Check, in **both** themes: body text, links, button text, and any small or grey text.

**4. Headings.** Read only the headings, in order. There should be exactly one `<h1>`, and no skipped levels: an `<h3>` only ever sits under an `<h2>`.

**5. Forms.** Every field has a `<label>` whose `for` matches the field's `id`. Click each label: the cursor should jump into its field. If you show your own error or success messages, they must say what happened **in words** — a red border on its own tells some people nothing.

**6. Images and links.** Read every `alt` aloud: does it describe the picture? Read every link's text on its own: does it say where the link goes? "Click here" and "Read more" don't.

## Requirements

- [ ] Every interactive thing can be reached and used with the keyboard alone
- [ ] The focus ring is visible everywhere — you have not removed it
- [ ] All text meets 4.5 : 1 (3 : 1 for large headings), in both themes
- [ ] One `<h1>`; no heading levels skipped
- [ ] Every form field has a linked label
- [ ] No message relies on colour alone
- [ ] Every image has a meaningful `alt`, and every link's text makes sense by itself
- [ ] `<html lang="en">` (or your page's real language) is set

## Acceptance criteria

- With the mouse unplugged, you can read the page, change the theme, use the third interaction, and send the form.
- You have a short written list: each problem you found, and what you changed to fix it.
- The lowest contrast ratio on the page, in either theme, is 4.5 : 1 or better. Write the number down.

## Hints

<details><summary>Show hint</summary>

- **Typical findings on this page:** small grey text that fails contrast; a link colour that passes on the page background but fails on a card; a dark theme where one colour was never checked; a clickable `<img>`; two elements sharing an `id`, so a label points at the wrong one.
- **Light grey is the usual culprit.** `#999999` on white is under 3 : 1. `#555555` on white is over 7 : 1 and still looks grey.
- **A bug you may already have met:** in dark mode, a pale link colour on a blue button is under 3 : 1. That's why the lesson's stylesheet has `.dark .button`.
- **Reading the colour picker.** In Chrome and Edge, the ratio has ticks beside it: one tick means the colour passes the main standard (4.5 : 1), and two mean it passes the stricter one as well. A warning sign instead of a tick means change it.
- **Empty `alt`.** A picture that is pure decoration should have `alt=""` — present, but empty — so that a screen reader skips it. Leaving the attribute out altogether is the mistake.
</details>

## Stretch (optional)

- Turn on your computer's screen reader — Narrator on Windows, VoiceOver on a Mac — and listen to your page from top to bottom with your eyes shut.
- Add a "Skip to content" link as the very first thing in the `<body>`: `<a href="#main">Skip to content</a>`, with `id="main"` on `<main>`. It's an in-page link, so you know how.
- *(stretch — beyond this course)* Design your own focus style. Look up the `:focus-visible` selector, and `outline`.
