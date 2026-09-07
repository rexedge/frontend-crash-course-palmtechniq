# Assignment 01 — Skeleton From Memory

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min (do it 3 times)
**Prereqs:** Class 1 §3 (the HTML document skeleton)
**Build in:** `work/01-skeleton-from-memory/index.html` (plus `index-2.html`, `index-3.html`)

---

## Goal

Type the complete HTML skeleton — `<!DOCTYPE html>` down to `</html>` — **from memory**, three times, in three separate files. By the third time you should not need to look at anything.

## What you'll practice

- The five parts of every page: `<!DOCTYPE html>`, `<html>`, `<head>`, `<title>`, `<body>`
- What goes in `<head>` vs `<body>`
- Closing tags in the reverse order they opened

## Instructions

1. Open `work/01-skeleton-from-memory/index.html`.
2. Read the target below **once**, then look away from it and type the whole thing yourself.
3. Inside `<body>`, put a single `<h1>` with your name.
4. Save, open with Live Server, confirm your name shows in the browser **and** the `<title>` text shows in the browser tab.
5. Delete everything and do it again in `index-2.html`. Then a third time in `index-3.html` — this time with **nothing** to refer to.

## Target

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First Website</title>
</head>
<body>

    <h1>Your Name Here</h1>

</body>
</html>
```

## Requirements

- [ ] `<!DOCTYPE html>` is the very first line
- [ ] `<html>` wraps everything; `<head>` and `<body>` are inside it
- [ ] `<title>` is inside `<head>` (not `<body>`)
- [ ] The `<h1>` is inside `<body>`
- [ ] Every tag that opens is closed, in the right order
- [ ] Done 3 times; the third with no reference

## Acceptance criteria

- The browser tab shows your `<title>` text.
- The page shows your name as a large heading.
- On attempt 3 you typed the whole skeleton without looking at the target or the lesson.

## Hints

<details><summary>Show hint</summary>

Think of it as a set of nested boxes: `html` is the outer box; inside it, `head` (info about the page) sits above `body` (what you see). If you put `<h1>` in `<head>` by mistake, nothing shows on the page.
</details>

## Stretch (optional)

In `index-3.html`, add `<meta charset="UTF-8">` inside `<head>` (above `<title>`). You'll use it every page from Class 2 on — it makes characters like `é`, `₦`, and `—` display correctly.
