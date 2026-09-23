# Assignment 19 — Debug: Grid & Responsive Bugs

**Type:** Debug · **Difficulty:** ⭐⭐ · **Time:** ~40 min
**Prereqs:** Class 5 §16 (troubleshooting)
**Build in:** `work/19-debug-grid-and-responsive/` — one folder per case (`a/`, `b/`, …)

---

## Goal

Each case is broken or behaving unexpectedly. Reproduce it, **fix it**, and write one sentence explaining the cause in your own words. Try before opening the answer.

---

## (a) The grid has only one column, no matter what

```css
.grid {
    display: grid;
    grid-template-columns: 1fr, 1fr, 1fr;
}
```

<details><summary>Show answer</summary>

Track sizes are separated by **spaces**, not commas. With commas the value is invalid, so the browser throws the whole declaration away (dev tools shows it struck through with a ⚠ warning icon) and the grid falls back to one column. Write `1fr 1fr 1fr` or `repeat(3, 1fr)`. (`repeat()` does use a comma — between the count and the size.)
</details>

---

## (b) The banner covers two columns, not three

```css
.grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
}
.banner {
    grid-column: 1 / 3;
}
```
…the author wanted the banner to cover the first **three** columns.

<details><summary>Show answer</summary>

Line numbers, not column counts. `1 / 3` runs from line 1 to line 3 — that's two columns. For three, use `1 / 4`, or `span 3`.
</details>

---

## (c) Stuck at two columns on a wide desktop

```css
.gallery {
    display: grid;
    grid-template-columns: 1fr;
}

@media (min-width: 900px) {
    .gallery {
        grid-template-columns: repeat(3, 1fr);
    }
}

@media (min-width: 600px) {
    .gallery {
        grid-template-columns: repeat(2, 1fr);
    }
}
```

<details><summary>Show answer</summary>

At 1000px **both** queries match. The rules have equal specificity, so the one later in the file — the 600px one — wins. Put `min-width` queries in ascending order: 600px first, then 900px.
</details>

---

## (d) Fine on desktop; tiny, zoomed-out, and ignoring every media query on a phone

```html
<head>
    <meta charset="UTF-8">
    <title>My Page</title>
    <link rel="stylesheet" href="style.css">
</head>
```
(To reproduce this one, use the device toolbar with a **phone** preset.)

<details><summary>Show answer</summary>

The viewport meta tag is missing. Without it, a phone browser lays the page out about 980px wide and shrinks it to fit, so your media queries see a 980px screen. Add `<meta name="viewport" content="width=device-width, initial-scale=1">` to the `<head>`.
</details>

---

## (e) Two cards stretch into huge slabs on a wide screen

```css
.cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```
…and there are only two cards.

<details><summary>Show answer</summary>

`auto-fit` collapses the empty columns, so the two cards share the whole row between them. To keep them card-sized, use `auto-fill` (it keeps the empty columns), or cap the maximum: `minmax(200px, 300px)`.
</details>

---

## (f) The page layout falls apart — every area piles up in the same spot

```css
.page {
    display: grid;
    grid-template-columns: 220px 1fr;
    grid-template-areas:
        "header  header"
        "sidebar content"
        "footer";
}
```
(Each landmark has the matching `grid-area`, e.g. `.footer { grid-area: footer; }`.)

<details><summary>Show answer</summary>

Every row of the map must have the same number of cells. The last row has one; the others have two. One bad row makes the whole `grid-template-areas` declaration invalid, so the `grid-area` names point at areas that don't exist, and the browser piles the items into extra columns at the edge. Fix: `"footer  footer"`.
</details>

---

## (g) The media query does nothing

```css
.cards {
    display: grid;
    gap: 16px;
}

@media (min-width: 768px) {
    grid-template-columns: repeat(3, 1fr);
}
```

<details><summary>Show answer</summary>

The declaration inside `@media` has no selector, so the browser doesn't know which element it's for and throws it away. A media query holds complete rules:

```css
@media (min-width: 768px) {
    .cards {
        grid-template-columns: repeat(3, 1fr);
    }
}
```
</details>

---

## (h) A horizontal scrollbar on phones — caused by one photo

```css
.gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
}
.gallery .featured {
    grid-column: span 2;
}
```

<details><summary>Show answer</summary>

On a phone there's only room for one column, but `.featured` insists on two — so the browser adds a second column, and the grid sticks out past the edge of the screen. Move the span inside `@media (min-width: 700px) { ... }`, where the grid always has at least two columns.
</details>

---

## Requirements

- [ ] All 8 cases reproduced, fixed, and checked in the browser
- [ ] A one-sentence cause for each, in your own words (not copied)

## Acceptance criteria

- Every fixed case behaves as intended: three real columns, a banner covering three columns, three columns on desktop, a phone layout that lays out at the real width, card-sized cards, a working page map, a media query that fires, and no sideways scrolling on a phone.
