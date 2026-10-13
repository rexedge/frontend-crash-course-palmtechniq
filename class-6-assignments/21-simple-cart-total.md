# Assignment 21 — Simple Cart Total

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1 hr
**Prereqs:** Class 6 §9, §11–12, §14 (functions calling functions, array loops, rounding)
**Build in:** `work/21-simple-cart-total/index.html` + `app.js`

---

## Goal

Work out a shopping cart's subtotal, tax, and total from two arrays — using four small functions that build on each other. Keep the file: the Class 7 mini shopping cart reuses these functions for its maths.

## What you'll practice

- **Parallel arrays**: two arrays where index `i` in each one describes the same item
- Splitting one job into several small functions
- Calling your own functions from inside other functions
- Rounding money

## Instructions

1. The cart is two arrays that line up by index:
   ```js
   const prices = [2500, 1200, 800];
   const quantities = [2, 1, 3];
   ```
   That's 2 of the first item, 1 of the second, and 3 of the third.
2. Write four functions:

   | Function | Returns |
   |---|---|
   | `cartSubtotal(prices, quantities)` | each price × its quantity, all added up |
   | `cartTax(subtotal, taxRate)` | the tax on that subtotal. `taxRate` is a decimal: `0.075` means 7.5% |
   | `cartTotal(prices, quantities, taxRate)` | subtotal + tax. It **calls** the first two |
   | `applyCoupon(total, code)` | the total with 10% off if `code` is `"SAVE10"`. For any other code, the total unchanged |

3. Round every money result to 2 decimal places. Write a small `roundTo2(n)` helper and use it wherever you need to.
4. Log the three pieces for the cart above, each with a label: `Subtotal`, `Tax`, `Total`. Then log the total after the `SAVE10` coupon.
5. Test a second cart with decimal prices: `[10, 4.5, 20]` with quantities `[2, 4, 1]` and a tax rate of `0.1`.

## Requirements

- [ ] Four functions plus `roundTo2`, each returning a number
- [ ] `cartSubtotal` uses **one** loop, with one index for both arrays
- [ ] `cartTotal` contains no loop of its own — it calls `cartSubtotal` and `cartTax`
- [ ] `applyCoupon` leaves the total alone for an unknown code
- [ ] Two different carts tested

## Acceptance criteria

| | Cart 1 (tax `0.075`) | Cart 2 (tax `0.1`) |
|---|---|---|
| `cartSubtotal` | `8600` | `58` |
| `cartTax` | `645` | `5.8` |
| `cartTotal` | `9245` | `63.8` |
| `applyCoupon(total, "SAVE10")` | `8320.5` | `57.42` |
| `applyCoupon(total, "HELLO")` | `9245` | `63.8` |

- An empty cart — `cartTotal([], [], 0.075)` — gives `0`, not `NaN`.

## Hints

<details><summary>Show hint</summary>

In `cartSubtotal`, the same `i` reads from both arrays: `prices[i] * quantities[i]`. Add that to a running total on each round.

In `cartTotal`, store the subtotal in a `const` first, then pass it to `cartTax`. That way the loop only runs once.

10% off means paying 90%: `total * 0.9`.
</details>

## Stretch (optional)

*(This reaches ahead of Class 6.)* Three functions for three numbers is a bit awkward. JavaScript has a way to return several named values at once, called an **object**: `return { subtotal: 8600, tax: 645, total: 9245 };`. Look up "JavaScript object literal", and write a `cartSummary` function that returns all three pieces in one object.
