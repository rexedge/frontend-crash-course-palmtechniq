# Assignment 03 — Toggle a Class

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 7 §7 (`classList`)
**Build in:** `work/03-toggle-a-class/index.html` + `style.css` + `app.js`

---

## Goal

Switch a CSS class on and off with a button. The look lives in the stylesheet; the JavaScript only flips the switch.

## What you'll practice

- `classList.toggle`
- Keeping styles in CSS and behaviour in JS
- Watching the `class` attribute change in the Elements panel

## Instructions

1. Build a page with one paragraph and one `<button type="button">`.
2. In `style.css`, define the class:
   ```css
   .highlight {
       background-color: yellow;
   }
   ```
3. In `app.js`, make the button toggle `highlight` on the paragraph.
4. Open the Elements panel, select the paragraph, and click the button a few times. Watch the `class` attribute appear and disappear.
5. Add two more declarations to `.highlight` in the CSS — a `padding` and a `font-weight`. Notice that you didn't touch the JavaScript.
6. One experiment: change the class name in your JavaScript to `".highlight"`, with a dot. Click the button, and look at the paragraph in the Elements panel. Then take the dot out again.

## Requirements

- [ ] The yellow background is defined in `style.css`, not in JavaScript
- [ ] The button uses `classList.toggle`
- [ ] The class does three things by the end (background, padding, weight)
- [ ] The dot experiment done, and explained in a one-line comment

## Acceptance criteria

- One click switches the highlight on; the next switches it off.
- There is no `.style` anywhere in `app.js`.
- Your comment says that with the dot, the element gets a class literally called `.highlight` — which the CSS rule doesn't match — and that there's no error.

## Hints

<details><summary>Show hint</summary>

`querySelector(".highlight")` needs the dot, because its string is a selector and could be anything. `classList.toggle("highlight")` only ever deals with class names, so it takes the name on its own.
</details>
