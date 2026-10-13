# Assignment 17 — Colour Changer

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~35 min
**Prereqs:** Class 7 §7, §9, §11 (`style`, the `input` event, one function for many elements); Class 6 §13–14 (string indexes, `Math.random`)
**Build in:** `work/17-colour-changer/index.html` + `style.css` + `app.js`

---

## Goal

Change the page's background colour three ways: with preset buttons, by typing a hex code, and with a "random colour" button. This is the one place in the class where `.style` is the right tool — the colour is worked out by the code, so it can't live in the stylesheet.

## What you'll practice

- `document.body.style.backgroundColor`
- One shared function with `event.target`
- Building a string, one random character at a time
- Knowing when `.style` beats a class

## Instructions

1. Build the page:
   - three preset buttons whose text is a CSS colour name: `Tomato`, `Gold`, `SkyBlue`
   - a labelled text input for a hex code, with a placeholder such as `#ff8800`
   - a `Random colour` button
   - a paragraph that shows the current colour
2. **Presets.** Write one named function that sets the background to `event.target.textContent`, and add it to all three buttons with `forEach`.
3. **Hex input.** On `input`, apply the typed value — but only when it looks complete: it starts with `#`, and it's 7 characters long.
4. **Random.** Write `randomHexColour()`, which **returns** a string such as `#3fa9c2`:
   - start with `"#"`
   - six times, add one random character from the string `"0123456789abcdef"`
5. Whichever way the colour changes, update the paragraph to show it.

## Requirements

- [ ] The three presets share one function, and use `event.target`
- [ ] A half-typed hex code (such as `#ff8`) changes nothing
- [ ] `randomHexColour()` returns its string, and doesn't touch the page itself
- [ ] The paragraph is updated every time the colour changes
- [ ] Every button is a `<button type="button">`

## Acceptance criteria

- Each preset button turns the page that colour.
- Typing `#1a56db` changes the background at the moment you type the seventh character.
- `Random colour` gives a different colour nearly every click, and the paragraph shows a `#` followed by exactly six characters from `0`–`9` and `a`–`f`.
- Log `randomHexColour()` ten times in the Console. Every result is 7 characters long.

## Hints

<details><summary>Show hint</summary>

Picking a random character is the "random item from an array" recipe from Class 6, used on a string:

```js
const digits = "0123456789abcdef";
const randomDigit = digits[Math.floor(Math.random() * digits.length)];
```

Do that six times in a `for` loop, adding each one to your string with `+=`.
</details>

## Stretch (optional)

*(This reaches a little outside Class 2.)* Add three sliders — `<input type="range" min="0" max="255">` — for red, green, and blue. On `input`, build the colour as `` `rgb(${red}, ${green}, ${blue})` `` and apply it.
