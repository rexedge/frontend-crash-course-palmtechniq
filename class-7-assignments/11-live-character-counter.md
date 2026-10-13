# Assignment 11 — Live Character Counter

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 7 §7–9 (`classList`, attributes, the `input` event)
**Build in:** `work/11-live-character-counter/index.html` + `style.css` + `app.js`

---

## Goal

Build the counter you've seen under message boxes everywhere: `0 / 200`, ticking up as you type, and changing colour as you get close to the limit.

## What you'll practice

- The `input` event on a `<textarea>`
- `.value.length`
- Reading a limit from an attribute with `getAttribute`
- Clearing old classes before adding the right one

## Instructions

1. Build the page: a labelled `<textarea maxlength="200">`, and a paragraph underneath that reads `0 / 200`.
2. In the CSS, write two classes for the counter: `.warning` (orange text) and `.full` (red text).
3. In `app.js`, read the limit **from the HTML**, so the number lives in one place:
   ```js
   const max = Number(messageInput.getAttribute("maxlength"));
   ```
4. On every `input` event:
   - work out how many characters are used, and how many remain
   - update the counter's text: `37 / 200`
   - remove both colour classes
   - then add `full` if nothing remains, or `warning` if fewer than 20 remain
5. Test the edges: 180, 181, 199, and 200 characters.

## Requirements

- [ ] The counter updates on every keystroke, including when you delete
- [ ] The limit is read from the `maxlength` attribute, not typed a second time in the JavaScript
- [ ] Orange when fewer than 20 remain; red at 0; the normal colour otherwise
- [ ] The colours come from classes — there's no `.style` in `app.js`

## Acceptance criteria

| Characters typed | Counter reads | Colour |
|---|---|---|
| 5 | `5 / 200` | normal |
| 180 (20 left) | `180 / 200` | normal |
| 181 (19 left) | `181 / 200` | orange |
| 200 (0 left) | `200 / 200` | red |
| back down to 100 | `100 / 200` | normal again |

- Change `maxlength` to `50` in the HTML only. The counter must still be right.

## Hints

<details><summary>Show hint</summary>

If the counter turns orange and then stays orange after you delete some text, you're adding classes but never taking them off. Remove **both** classes at the start of the function, every time — then add back whichever one applies.

To reach 200 characters quickly, type a few words, select them all, copy, and paste a few times.
</details>

## Stretch (optional)

Show the number **remaining** instead: `163 characters left`. And make it read `1 character left`, without the `s`, when there's exactly one.
