# Assignment 21 — Mini Shopping Cart

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1.5 hr
**Prereqs:** Class 6 Assignment 21 (cart functions); Class 7 §11–12 (`forEach` with an index, creating and removing elements)
**Build in:** `work/21-mini-shopping-cart/index.html` + `style.css` + `app.js`

---

## Goal

Build a small shop: four products with "Add to cart" buttons, and a cart panel that lists what's been added, lets you change quantities, and keeps a live subtotal. The maths is the code you wrote in Class 6.

## What you'll practice

- Keeping the **data** in arrays, and redrawing the page from it
- One function that rebuilds a whole section of the page
- Listeners on elements that were created by code
- Reusing a pure function from an earlier class

## The big idea: change the data, then redraw

Don't try to edit the cart's HTML piece by piece. Instead:

1. Keep the truth in arrays.
2. Every time something changes, change the **arrays**.
3. Then call one function that **empties the cart and builds it again** from the arrays.

It sounds wasteful. It's actually the simplest way to keep a page correct, and it's how most real interfaces work.

## Instructions

1. In the HTML: four products, each with a name, a price, and a `<button type="button" class="add-to-cart">`. Then a cart panel: an empty `<ul id="cart-items">`, and a paragraph for the subtotal.
2. In `app.js`, the data — three arrays that line up by index, in the same order as the products in the HTML:
   ```js
   const productNames = ["Notebook", "Pen", "Eraser", "Backpack"];
   const prices = [2500, 1200, 800, 4000];
   const quantities = [0, 0, 0, 0];
   ```
3. Copy `cartSubtotal(prices, quantities)` in from your Class 6 work, unchanged.
4. Write `showCart()`:
   - empty the list: `cartItems.innerHTML = "";`
   - loop over the products. For each one with a quantity above 0, build an `<li>` containing the name and quantity (`Notebook × 2`), a `−` button, a `+` button, and a `Remove` button
   - each of those buttons changes `quantities[i]`, and then calls `showCart()` again
   - after the loop, show the subtotal using `cartSubtotal`
5. Give each "Add to cart" button a listener that adds 1 to `quantities[i]` and calls `showCart()`.
6. Call `showCart()` once at the bottom of the file, so the page starts with `Subtotal: 0`.

## Requirements

- [ ] The quantities live in an array; the page is only ever a picture of that array
- [ ] `showCart()` is the **only** place where the cart's HTML is built
- [ ] Every action follows the same two steps: change the data, call `showCart()`
- [ ] A product whose quantity reaches 0 disappears from the cart
- [ ] The subtotal comes from your Class 6 function
- [ ] Product names go in with `textContent`

## Acceptance criteria

With the prices above:

| Action | Cart shows | Subtotal |
|---|---|---|
| Page loads | nothing | `0` |
| Add Notebook twice, Eraser once | `Notebook × 2`, `Eraser × 1` | `5800` |
| Press `+` on Eraser | `Notebook × 2`, `Eraser × 2` | `6600` |
| Press `−` on Notebook twice | `Eraser × 2` | `1600` |
| Press `Remove` on Eraser | nothing | `0` |

## Hints

<details><summary>Show hint</summary>

`innerHTML = ""` is safe here: you're writing an empty string, not anything a user typed.

Inside `showCart`, use `productNames.forEach((productName, i) => { ... })`. That `i` is what links everything: `quantities[i]`, `prices[i]`, and the listeners you create inside the loop all use the same `i`.

If clicking "Add" twice shows **two rows** for the same product, you forgot to empty the list at the start of `showCart()`.
</details>

## Stretch (optional)

Add the tax and the total under the subtotal, using `cartTax` and `cartTotal` from Class 6. Then add a coupon box that calls `applyCoupon` — and shows the reduced total only when the code is `SAVE10`.
