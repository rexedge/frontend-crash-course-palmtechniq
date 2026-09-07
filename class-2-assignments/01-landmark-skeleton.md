# Assignment 01 — Landmark Skeleton

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min (do it 3 times)
**Prereqs:** Class 2 §2 (skeleton upgrade) and §4 (semantic layout tags)
**Build in:** `work/01-landmark-skeleton/index.html`

---

## Goal

Type a complete, correctly-nested semantic page skeleton **from memory**, three times, in three separate files.

## What you'll practice

- The upgraded skeleton: `<html lang>`, `<meta charset>`, `<title>`
- The four core landmarks and their order: `header` → `main` → `footer`, with `nav` inside `header`
- Keeping `<header>`, `<nav>`, and `<footer>` **outside** `<main>`

## Instructions

1. In `work/01-landmark-skeleton/index.html`, type the skeleton below **without copying it** — read it once, then close this file and type it out.
2. Inside `<body>`, include exactly: one `<header>` (with an `<h1>` and a `<nav>` holding a `<ul>` of 3 links), one `<main>` (with one `<h2>` and one `<p>`), one `<footer>` (with one `<p>`).
3. Open with Live Server. Confirm it renders as a plain vertical stack of text.
4. Delete the file's contents and do it again from memory. Then a third time in a fresh file (`.../index-2.html`, `.../index-3.html`).

## Target structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Landmark Skeleton</title>
</head>
<body>

    <header>
        <h1>Site Name</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <h2>Page Heading</h2>
        <p>The unique content of this page.</p>
    </main>

    <footer>
        <p>Made by me, 2025.</p>
    </footer>

</body>
</html>
```

## Requirements

- [ ] `<html lang="en">` and `<meta charset="UTF-8">` present
- [ ] Exactly **one** `<main>`
- [ ] `<nav>` is inside `<header>`; `<footer>` is a sibling of `<header>` and `<main>`, not inside them
- [ ] All tags close in the reverse order they opened
- [ ] Done 3 times, the third with no reference

## Acceptance criteria

- Open the browser dev tools "Elements" panel. The tree shows `header > (h1, nav > ul > li > a)`, then `main`, then `footer` — all direct children of `body`.
- By the third attempt you did not need to look at any notes.

## Hints

<details><summary>Show hint</summary>

If you keep forgetting a piece, write the skeleton once with each line labelled by a `<!-- comment -->` explaining what it does, then do your 3 memory reps.
</details>
