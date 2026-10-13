# Assignment 02 — Photographer Portfolio

**Type:** Variant · **Difficulty:** ⭐⭐⭐ · **Time:** ~3 hr
**Prereqs:** Class 3 §9 (backgrounds); Class 5 §4, §12, §13; Class 7 §8, §11; Class 8
**Build in:** `work/02-photographer-portfolio/index.html` + `style.css` + `app.js`

---

## Goal

Build a portfolio for a photographer — real or made up — where the pictures do the talking: a photo that fills the top of the page, a gallery of mixed shapes, and a viewer for looking at one photo at a time.

## What you'll practice

- A background image that covers a whole section, with text you can still read on top of it
- A grid with fixed-height rows, where some items cover two rows or two columns
- One `let` variable that remembers which photo is showing, and one function that draws it
- Wrapping round at both ends of a list

## Instructions

1. **The hero.** A `<section class="hero">` with the photographer's name in an `<h1>` and one line about their work, inside a `<div class="hero-text">`. Give the section a `background-image`, `background-size: cover`, `background-position: center`, and a `min-height` of `60vh`. Centre the text box with Flexbox.
2. **Make the words readable.** Text straight onto a photo is hard to read. Give `.hero-text` white text and a see-through dark background: `background-color: rgba(0, 0, 0, 0.6);`.
3. **The gallery.** At least eight `<img class="photo">` elements in a `<section id="gallery">`, each with a real `alt`. Lay them out with `repeat(auto-fit, minmax(160px, 1fr))` and `grid-auto-rows: 160px`. Each photo gets `width: 100%`, `height: 100%`, and `object-fit: cover`.
4. **Mixed shapes.** Give two photos the class `tall` and two the class `wide`. Inside a `min-width: 600px` media query, `.tall` covers two rows and `.wide` covers two columns.
5. **The viewer.** Above the gallery, add a hidden `<section id="viewer">` with one large `<img>`, a caption paragraph, and three buttons: `Previous`, `Next`, and `Back to the gallery`.
6. **The JavaScript.** Clicking a photo hides the gallery and shows the viewer, with that photo in it. `Next` and `Previous` step through the photos and wrap round at the ends. `Back to the gallery` swaps the two sections back.
7. Add the rest of a portfolio: a short About section, a contact form with a thank-you message, and a footer.

## Requirements

- [ ] The hero photo runs from edge to edge of the window, and the text on it is easy to read
- [ ] At least eight photos, every one with an `alt` that describes it
- [ ] The spans are **inside** the media query
- [ ] Clicking a photo opens that photo in the viewer
- [ ] The caption shows the photo's `alt` text and its position, such as `(4 of 8)`
- [ ] `Next` on the last photo goes to the first; `Previous` on the first goes to the last
- [ ] The viewer's `alt` changes along with its `src`
- [ ] No `position`, and no libraries

## Acceptance criteria

- The gallery gains columns as the window widens, and there's no horizontal scrollbar at any width from 320px up.
- Below 600px every photo is one cell. From 600px, the `tall` and `wide` photos cover two.
- Click the fourth photo: the gallery disappears, and the viewer shows that photo with a caption ending `(4 of 8)`.
- Click `Next` until you reach the last photo, then once more: you're on photo 1.
- Click `Previous` from photo 1: you're on the last photo.
- `Back to the gallery` brings every photo back, exactly as it was.

## Hints

<details><summary>Show hint</summary>

Keep the position in one variable, and let one function draw whatever that variable says:

```js
let current = 0;

function showPhoto() {
    const photo = photos[current];

    viewerPhoto.setAttribute("src", photo.getAttribute("src"));
    viewerPhoto.setAttribute("alt", photo.getAttribute("alt"));
    viewerCaption.textContent = `${photo.getAttribute("alt")} (${current + 1} of ${photos.length})`;
}
```

Then every button does the same two things: change `current`, and call `showPhoto()`. A click on a photo sets `current` to that photo's index — the second parameter of `forEach`.

Wrapping round is the `%` trick from the Class 7 carousel:

```js
current = (current + 1) % photos.length;                    // Next
current = (current - 1 + photos.length) % photos.length;    // Previous
```

A few empty cells in the gallery are normal when some photos cover two cells. Move the `tall` and `wide` classes to different photos until the gaps close up.
</details>

## Stretch (optional)

- A plain `<img>` can't be reached with the keyboard. Wrap each photo in a `<button type="button">`, as in the stretch for [Class 7, Assignment 15](../class-7-assignments/15-image-gallery.md).
- *(stretch — beyond this course)* A true **lightbox**: the big photo pops up over the page, with the gallery dimmed behind it. Look up `position: fixed`.
- *(stretch — beyond this course)* Close the gaps in the gallery automatically. Look up `grid-auto-flow: dense`.
