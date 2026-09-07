# Assignment 01 — Wire Up a Stylesheet

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min (do it twice)
**Prereqs:** Class 3 §3 (anatomy of a rule), §4 (connecting CSS)
**Build in:** `work/01-wire-up-a-stylesheet/index.html` + `style.css`

---

## Goal

Connect an external stylesheet to an HTML page **from memory**, twice, and prove the connection works.

## What you'll practice

- The `<link rel="stylesheet" href="style.css">` line and where it goes
- One `.css` file living next to the `.html` file
- The shape of a CSS rule: `selector { property: value; }`

## Instructions

1. In `work/01-wire-up-a-stylesheet/`, create `index.html` (a valid skeleton with an `<h1>` and two `<p>`s) and an empty `style.css` beside it.
2. In the HTML `<head>`, add the `<link>` line **from memory**.
3. In `style.css`, prove it's connected:
   ```css
   body {
       background-color: lightyellow;
   }
   ```
4. Save both, open `index.html` with Live Server. Page turns pale yellow → wired up.
5. Add two more rules: make the `<h1>` a colour of your choice, and give every `<p>` a different text `color`.
6. Delete the whole folder and do the entire thing again in a fresh folder — the `<link>` line with nothing to copy from.

## Requirements

- [ ] `style.css` sits in the same folder as `index.html`
- [ ] `<link rel="stylesheet" href="style.css">` is inside `<head>`
- [ ] At least 3 working rules (`body`, `h1`, `p`)
- [ ] No `style=""` attributes and no `<style>` block anywhere
- [ ] Done twice; the second time the `<link>` line was typed from memory

## Acceptance criteria

- The page shows all three style changes.
- Opening dev tools → **Network** tab shows `style.css` loading with status 200 (not 404).

## Hints

<details><summary>Show hint</summary>

If nothing changes: check the file is really named `style.css` (not `styles.css` or `style.css.txt`), the `<link>` is in `<head>` not `<body>`, and `rel="stylesheet"` is spelled correctly. The Network tab will show a red 404 line if the path is wrong.
</details>
