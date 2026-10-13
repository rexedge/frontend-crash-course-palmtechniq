# Assignment 04 — Product / App Landing Page

**Type:** Variant · **Difficulty:** ⭐⭐⭐ · **Time:** ~3 hr
**Prereqs:** Class 4; Class 5; Class 6 §7, §12 (arithmetic, arrays); Class 7 §6, §10, §11; Class 8
**Build in:** `work/04-product-landing-page/index.html` + `style.css` + `app.js`

---

## Goal

Build a landing page for a made-up product or app: what it does, what it costs, and a way to sign up. The interesting part is the pricing — one button switches every price between monthly and yearly.

## What you'll practice

- A features grid, and a three-tier pricing row with one tier standing out
- Keeping numbers in **one** place — an array — and letting JavaScript write them onto the page
- A `true` / `false` variable that remembers which mode you're in
- A form handler that uses what the visitor typed

## Instructions

1. **The page.** A header with in-page nav links; a hero with a headline and a call-to-action; a **features** section (at least six, in a Grid); a **pricing** section; an FAQ; an email sign-up form; a footer.
2. **The pricing tiers.** Three `<article class="tier">` cards in a Flexbox row that wraps. Each has a name, a `<p class="price">`, and a short list of what's included. Give the middle one a second class, `featured`, and make it stand out with a thicker border or a different background.
3. **A button above the tiers**: `<button type="button" id="billing-toggle">Show yearly prices</button>`.
4. **The prices, as data.** In `app.js`, keep the three monthly prices in one array. A yearly price is ten times the monthly one: "two months free".
5. **`showPrices()`.** One function that writes all three price lines, and the button's text, to match a variable called `yearly`. Clicking the button flips `yearly`, then calls the function.
6. **The sign-up form.** One email field. On `submit`: `preventDefault`, hide the form, and show a message that includes the address that was typed.
7. **The FAQ.** The accordion from [Class 7, Assignment 12](../class-7-assignments/12-show-hide-accordion.md).

## Requirements

- [ ] Each monthly price is written **once**, in the array — the yearly prices are worked out, not typed
- [ ] One `let` holds `true` or `false`; one function redraws the prices from it
- [ ] The button's text always says what clicking it will do
- [ ] The middle tier stands out, in both layouts
- [ ] The tiers sit in a row on a wide screen and stack on a phone
- [ ] The sign-up form uses `type="email"` and `required`, and the browser's own checks still work
- [ ] No red in the Console, and no horizontal scrollbar from 320px to 1440px

## Acceptance criteria

With monthly prices of 5, 12, and 30:

| Do this | You should see |
|---|---|
| Load the page | `$5 / month`, `$12 / month`, `$30 / month`. The button says `Show yearly prices` |
| Click the button | `$50 / year`, `$120 / year`, `$300 / year`. The button says `Show monthly prices` |
| Click it again | Back to the monthly prices |
| Send the form with `not-an-email` in the box | The browser's own complaint. Nothing else changes |
| Send it with `ada@example.com` | The form disappears. `Thanks. We'll email ada@example.com when it's ready.` |

Change one number in the array, save, and reload: both that tier's monthly price and its yearly price change.

## Hints

<details><summary>Show hint</summary>

The prices and the price lines are partners by index: `monthlyPrices[0]` belongs in the first `.price` element.

```js
const monthlyPrices = [5, 12, 30];

let yearly = false;

function showPrices() {
    priceLines.forEach((priceLine, i) => {
        if (yearly) {
            priceLine.textContent = `$${monthlyPrices[i] * 10} / year`;
        } else {
            priceLine.textContent = `$${monthlyPrices[i]} / month`;
        }
    });
}
```

`$${…}` looks odd, but it's two separate things: the first `$` is just a dollar sign, and `${…}` is the usual slot in a template literal.

To flip a boolean, use `!` from Class 6: `yearly = !yearly;`. And call `showPrices()` once at the bottom of the file, so that the prices come from the array from the very start.
</details>

## Stretch (optional)

- Under each yearly price, show the saving: `You save $10`. It's two months of the monthly price.
- Add a fourth tier by adding one card to the HTML and one number to the array — with no other change to the JavaScript.
