# Assignment 17 — Debug: CSS That Isn't Working

**Type:** Debug · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 3 §4–6, §11 (cascade & specificity), §13 (troubleshooting)
**Build in:** `work/17-debug-css/` — one folder per case (`a/`, `b/`, …)

---

## Goal

Each case below is broken or behaving unexpectedly. Reproduce it, **fix it**, and write one sentence explaining the cause in your own words. Try before opening the answer.

---

## (a) The stylesheet has no effect at all

```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```
…and the file on disk is named `style.css`.

<details><summary>Show answer</summary>

Filename mismatch: `styles.css` vs `style.css`. A missing stylesheet fails silently — check dev tools → **Network** for a 404. Rename one so they match.
</details>

---

## (b) `margin` isn't applying

```css
p {
  margin 20px;
}
```

<details><summary>Show answer</summary>

Missing colon — must be `margin: 20px;`. A malformed declaration is dropped, and a missing `:` or `;` can break the **next** declaration too.
</details>

---

## (c) The heading is red; this rule says blue and you expected blue to win

```css
h1 { color: blue; }
#title { color: red; }
```
```html
<h1 id="title">Hello</h1>
```

<details><summary>Show answer</summary>

Not a bug — **specificity**. `#id` beats an element selector, so `red` wins. To make blue win, raise its specificity to match, e.g. `#title { color: blue; }`, or use `h1#title`.
</details>

---

## (d) The box is wider than its container and causes a horizontal scrollbar

```css
.card { width: 100%; padding: 30px; border: 2px solid; }
```

<details><summary>Show answer</summary>

Default `content-box`: `width: 100%` + 60px padding + 4px border > 100% of the parent. Add `box-sizing: border-box` (usually globally: `*, *::before, *::after { box-sizing: border-box; }`).
</details>

---

## (e) A descendant selector recolours more than intended

```css
nav a { color: white; }
```
…and it's also recolouring the links inside the `<footer>`'s `<nav>`.

<details><summary>Show answer</summary>

`nav a` matches links in **every** `<nav>`. Scope it: give the header nav an `id` and target `#main-nav a`, or give the footer nav its own rule that overrides the colour back.
</details>

---

## (f) `text-align: center` won't centre the image

```css
.figure { text-align: center; }
.figure img { width: 200px; }
```
…the image stays on the left.

<details><summary>Show answer</summary>

`text-align` centres **inline** content, and an `<img>` is inline — so this *should* work **if** `.figure` is the parent of the `<img>` and is a block that's wider than 200px. If the image was set to `display: block`, `text-align` no longer applies to it — centre it with `margin: 0 auto` instead. (Check which case you're in via dev tools.)
</details>

---

## Requirements

- [ ] All 6 cases reproduced, fixed, and verified in the browser
- [ ] A one-sentence cause for each, in your own words (not copied)
- [ ] For (c): note that it's a specificity *rule*, not a bug

## Acceptance criteria

- Every fixed case renders as intended: stylesheet loads, `margin` applies, the colour you want wins, no overflow scrollbar, only the header nav is recoloured, the image is centred.
