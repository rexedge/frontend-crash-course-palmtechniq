# Assignment 18 — Debug: Broken HTML

**Type:** Debug · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 1 §3–5; §7 (Troubleshooting)
**Build in:** `work/18-debug-broken-html/` — one file per snippet (`a.html`, `b.html`, …)

---

## Goal

Each snippet below has one or more bugs. For each: put it in a file, open it in the browser, spot the problem, **fix it**, and write one sentence explaining the cause in your own words. Try before opening the answer.

---

## (a) The title never closes

```html
<!DOCTYPE html>
<html>
<head>
  <title>Broken One
</head>
<body>
  <h1>Hello</h1>
</body>
</html>
```

<details><summary>Show answer</summary>

`<title>` is opened but never closed. Everything after it gets swallowed into the title. Add `</title>`:
```html
<title>Broken One</title>
```
</details>

---

## (b) A list item isn't closed

```html
<body>
  <h1>My List</h1>
  <ul>
    <li>One</li>
    <li>Two
    <li>Three</li>
  </ul>
</body>
```

<details><summary>Show answer</summary>

The second `<li>Two` has no `</li>`. Add it: `<li>Two</li>`.
</details>

---

## (c) Unquoted attribute and a missing `alt`

```html
<body>
  <h1>Visit my favourite site</h1>
  <a href=https://example.com>Example</a>
  <img src="https://picsum.photos/200">
</body>
```

<details><summary>Show answer</summary>

Two issues: the `href` value isn't quoted — always quote attribute values: `href="https://example.com"`. And the `<img>` has no `alt` — add a written description: `<img src="https://picsum.photos/200" alt="A random placeholder photo">`.
</details>

---

## (d) A paragraph that isn't closed, and a list opened with `<ol>` but closed with `</ul>`

```html
<html>
<body>
  <h1>Photos</h1>
  <p>Here are my photos.
  <ol>
    <li>Beach trip</li>
    <li>Mountain hike</li>
  </ul>
</body>
</html>
```

<details><summary>Show answer</summary>

Two issues: `<p>Here are my photos.` is never closed — add `</p>`. And the list opens with `<ol>` but closes with `</ul>` — make them match (`<ol>`…`</ol>` or `<ul>`…`</ul>`).
</details>

---

## (e) Title in the body, and a mismatched heading tag

```html
<!DOCTYPE html>
<html>
<body>
  <title>About Me</title>
  <h1>About Me</h2>
  <p>I like <a href="">links</a> that go nowhere.</p>
</body>
</html>
```

<details><summary>Show answer</summary>

Three issues:
1. `<title>` is in `<body>` — it belongs in `<head>` (add a `<head>` and move it there).
2. `<h1>` is closed with `</h2>` — fix to `</h1>`.
3. `<a href="">` has an empty destination — give it a real URL.
</details>

---

## (f) Tags closed in the wrong order

```html
<ul>
  <li><a href="https://example.com">Example</li></a>
</ul>
```

<details><summary>Show answer</summary>

The `</li>` and `</a>` are in the wrong order. You must close the **last tag you opened first**. Correct: `<li><a href="https://example.com">Example</a></li>`.
</details>

---

## Requirements

- [ ] All 6 snippets fixed in separate files and verified in the browser
- [ ] A one-sentence cause written for each, in your own words (not copied from the answer)

## Acceptance criteria

- Every fixed page renders correctly: title in the tab (not on the page), lists and paragraphs properly separated, images with `alt`, links with real destinations, no tags closed out of order.
- You can explain each bug without re-reading the answer.
