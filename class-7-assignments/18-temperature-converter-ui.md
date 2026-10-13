# Assignment 18 — Temperature Converter UI

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min · 🧵 keep this file
**Prereqs:** Class 6 Assignment 11 (`celsiusToFahrenheit`); Class 7 §8–9 (`.value` is a string, the `input` event)
**Build in:** `work/18-temperature-converter-ui/index.html` + `style.css` + `app.js`

---

## Goal

Take a function you wrote in Class 6 and give it a face: type a temperature in °C, and see it in °F as you type. This is the pattern for connecting *any* logic to a page — the function doesn't change at all.

## What you'll practice

- Keeping the maths and the page code separate
- `Number()` on an input's value
- The empty-box trap: `Number("")` is `0`
- Rounding a result for display

## Instructions

1. Copy `celsiusToFahrenheit(c)` from your Class 6 work into `app.js`. **Don't change it.**
2. Build the page: a labelled `type="number"` input for °C, and beside it a `<span>` for the result, which starts as `—`.
3. On `input`:
   - if the box is empty, show `—`
   - otherwise, convert the value with `Number()`, pass it to `celsiusToFahrenheit`, round the answer to 1 decimal place, and show it
4. Add a second row that goes the other way. Write `fahrenheitToCelsius(f)` — subtract 32, multiply by 5, divide by 9 — and connect it in the same way.
5. Write a small `roundTo1(n)` helper and use it in both rows.

## Requirements

- [ ] `celsiusToFahrenheit` is exactly as you wrote it in Class 6 — it knows nothing about the page
- [ ] Both conversion functions **return** numbers; only the listeners touch the DOM
- [ ] An empty box shows `—`, not `32` or `-17.8`
- [ ] Results are rounded to 1 decimal place
- [ ] The result updates on every keystroke

## Acceptance criteria

| °C typed | °F shown | | °F typed | °C shown |
|---|---|---|---|---|
| `100` | `212` | | `212` | `100` |
| `37` | `98.6` | | `98.6` | `37` |
| `0` | `32` | | `32` | `0` |
| `-40` | `-40` | | `50` | `10` |
| `36.6` | `97.9` | | `0` | `-17.8` |
| *(empty)* | `—` | | *(empty)* | `—` |

## Hints

<details><summary>Show hint</summary>

Check for the empty box **before** you convert: `if (celsiusInput.value.trim() === "")`. Without that check, an empty box becomes `Number("")`, which is `0` — and the page confidently tells you that nothing at all is 32 °F.

Rounding to 1 decimal place is the Class 6 recipe with 10 instead of 100: `Math.round(n * 10) / 10`.
</details>

## Stretch (optional)

Make it one two-way converter: typing in the °C box fills in the °F **box**, and typing in the °F box fills in the °C box. (Setting an input's `.value` from your code doesn't trigger its `input` event, so the two listeners won't chase each other.)
