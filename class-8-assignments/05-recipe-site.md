# Assignment 05 — Recipe Site

**Type:** Variant · **Difficulty:** ⭐⭐⭐ · **Time:** ~3 hr
**Prereqs:** Class 1 (linking pages); Class 2 §4; Class 5 §12; Class 6 §7, §14; Class 7 §8, §12, §13; Class 8
**Build in:** `work/05-recipe-site/` — `index.html`, `pancakes.html` (or your own recipe), `style.css`, `app.js`

---

## Goal

Build a small two-page recipe site: a homepage with a grid of recipe cards, and one full recipe page with a **servings scaler** — change the number of people, and every ingredient amount changes to match.

## What you'll practice

- Two pages that share one stylesheet and link to each other
- An `<article>` with a list of ingredients and an ordered list of steps
- An array of objects as the single source of truth
- Emptying a list and rebuilding it from data, every time something changes

## Instructions

1. **The homepage** (`index.html`). A header, a short introduction, and at least four recipe cards in a Grid: a photo, the recipe's name, one line about it, and a link. Only one card needs to link to a finished page.
2. **The recipe page.** A header with a link back to the homepage, and one `<article>`: the name in an `<h1>`, a photo, an **Ingredients** section, and a **Method** section with the steps in an `<ol>`.
3. **The scaler's HTML.** In the Ingredients section: a labelled `<input type="number" id="servings" min="1" max="12">` whose starting `value` is the number the recipe is written for; a hidden paragraph that says `Enter a number of servings from 1 to 12.`; and an **empty** `<ul id="ingredients">`.
4. **The ingredients, as data.** In `app.js`, write the recipe's ingredients as an array of objects. Each one has a `name`, an `amount`, and a `unit`. Something counted, like eggs, has an empty string for its unit.
5. **`showIngredients(servings)`.** Empty the list. Then, for each ingredient, work out the new amount, build an `<li>`, and append it. Call it once as the page loads.
6. **Listen for `input`** on the servings box. If the box is empty, or the number is under 1 or over 12, show the hidden message and leave the list alone. Otherwise hide the message and redraw.
7. Load `app.js` on the recipe page only. The homepage has no servings box for it to find.

## Requirements

- [ ] Both pages share `style.css`, and each links to the other
- [ ] The ingredient amounts appear **only** in the array — none are typed into the HTML
- [ ] One function rebuilds the whole list; the list never grows longer as you type
- [ ] The new amount is `amount × servings ÷ the servings the recipe was written for`, rounded to 2 decimal places
- [ ] An empty box, `0`, or `13` shows the message and changes nothing else
- [ ] List items are created with `createElement` and filled with `textContent`
- [ ] Both pages work from 320px to 1440px, with no red in the Console

## Acceptance criteria

For a recipe written for **4** servings, with 200 g plain flour, 300 ml milk, 2 eggs, and 20 g butter:

| Servings | The list reads |
|---|---|
| 4 (as the page loads) | `200 g plain flour` · `300 ml milk` · `2 eggs` · `20 g butter` |
| 6 | `300 g plain flour` · `450 ml milk` · `3 eggs` · `30 g butter` |
| 1 | `50 g plain flour` · `75 ml milk` · `0.5 eggs` · `5 g butter` |
| *(empty box)* | The message appears. The list still shows the last amounts |
| 13 | The message appears. The list still shows the last amounts |
| 12 | The message goes. `600 g plain flour` · `900 ml milk` · `6 eggs` · `60 g butter` |

However many times you change the number, the list has exactly four items.

## Hints

<details><summary>Show hint</summary>

The data:

```js
const baseServings = 4;

const ingredients = [
    { name: "plain flour", amount: 200, unit: "g" },
    { name: "milk", amount: 300, unit: "ml" },
    { name: "eggs", amount: 2, unit: "" },
    { name: "butter", amount: 20, unit: "g" }
];
```

The first line of `showIngredients` is `ingredientList.innerHTML = "";` — it empties the list, so the new items replace the old ones instead of piling up underneath.

For the rounding, reuse `roundTo2` from your Class 6 calculator toolkit:

```js
const amount = roundTo2(ingredient.amount * servings / baseServings);
```

An ingredient with no unit needs a slightly different sentence, or you get two spaces in a row. One `if` deals with it: when `ingredient.unit === ""`, leave the unit out of the template literal.

And remember that `Number("")` is `0`. That's handy here: an empty box fails the "at least 1" test anyway. Checking `servingsInput.value.trim() === ""` as well makes the reason obvious to whoever reads your code.
</details>

## Stretch (optional)

- Add `−` and `+` buttons on either side of the servings box. They change the box's `.value` and then redraw, and they never go below 1 or above 12.
- Finish a second recipe page. Give each page its own small script holding its own `ingredients` array, and move `showIngredients` and the listener into a shared file that both pages load **after** it.
