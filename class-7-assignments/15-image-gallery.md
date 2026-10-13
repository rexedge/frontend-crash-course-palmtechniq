# Assignment 15 — Image Gallery

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min · 🧵 keep this file
**Prereqs:** Class 7 §8, §11 (`getAttribute` / `setAttribute`, "clear them all, then mark the one")
**Build in:** `work/15-image-gallery/index.html` + `style.css` + `app.js`

---

## Goal

Build a gallery with one large "main" photo and a row of six thumbnails. Clicking a thumbnail swaps the main photo to match, and highlights that thumbnail.

## What you'll practice

- Reading attributes from one element and writing them to another
- Changing an image's `src` **and** its `alt`
- Marking one item in a list as active

## Instructions

1. Build the page:
   - one main image: `<img id="main-photo" …>`
   - a row of six thumbnails: `<img class="thumb" …>`
2. Use this form of placeholder address, so each photo stays the same every time:
   `https://picsum.photos/seed/lagos/800/600`
   The word after `seed/` picks the photo — change the word, and you get a different one. Use six different words. Give every image a different `alt`.
3. The main image starts with the same `src` and `alt` as the first thumbnail, and the first thumbnail starts with the class `active`.
4. In the CSS:
   - the main photo: `width: 100%`, an `aspect-ratio`, and `object-fit: cover` (Class 5)
   - the thumbnails: a 6-column grid, each one a small square, with `cursor: pointer`
   - an `.active` rule, written **below** the `.thumb` rule: a thick border, so the chosen one stands out
5. In `app.js`, loop over the thumbnails. On click:
   - copy the thumbnail's `src` to the main photo, and its `alt` too
   - take `active` off every thumbnail, then put it on the clicked one

## Requirements

- [ ] Six thumbnails, and one main photo that starts off matching the first
- [ ] Clicking a thumbnail changes the main photo's `src` and its `alt`
- [ ] Exactly one thumbnail is highlighted at any time
- [ ] The values are read with `getAttribute` and written with `setAttribute`
- [ ] The gallery works at 375px, 768px, and 1280px, with no horizontal scrollbar

## Acceptance criteria

- Click the fourth thumbnail: the main photo becomes that photo, and the fourth thumbnail has the border.
- Inspect the main photo after a few clicks. Its `alt` matches the picture that's showing — not the first one.
- The thumbnail and the big version are always the same photo.

## Hints

<details><summary>Show hint</summary>

The swap is two lines:

```js
mainPhoto.setAttribute("src", thumb.getAttribute("src"));
mainPhoto.setAttribute("alt", thumb.getAttribute("alt"));
```

For a small practice gallery, it's fine for a thumbnail to use the same image file as the big version — the CSS just draws it smaller.
</details>

## Stretch (optional)

A plain `<img>` can be clicked with a mouse, but it can't be reached with the keyboard. Make the gallery work for everyone: wrap each thumbnail in a `<button type="button" class="thumb-button">`, and put the click listeners on the buttons. You'll then need two lists — the buttons, and the images inside them (`".thumb-button img"`) — and the index from `forEach` to link them.
