# Assignment 06 — Media Query Drill

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 5 §13–14 (media queries, mobile-first)
**Build in:** `work/06-media-query-drill/index.html` + `style.css`

---

## Goal

Write your first media queries, watch them switch on at exact widths, and prove to yourself why `min-width` queries go smallest first.

## What you'll practice

- `@media (min-width: ...)` syntax — a whole rule inside, selector and all
- Reading the computed value in dev tools
- The cascade: with equal specificity, the later rule wins

## Instructions

1. Build a page with an `<h1>` and one long `<p>`. (Viewport tag in the `<head>`!)
2. In `style.css`:
   ```css
   p {
       font-size: 1rem;
   }

   @media (min-width: 600px) {
       p {
           font-size: 1.125rem;
       }
   }

   @media (min-width: 900px) {
       p {
           font-size: 1.25rem;
       }
   }
   ```
3. Open the device toolbar, choose **Responsive**, and set the width to 500px, 600px, 899px, 900px, and 1200px. At each width, select the `<p>` in the Elements panel and read its `font-size` in the **Computed** tab. Write the five values down.
4. Swap the order of the two `@media` blocks. Check 1200px again. Write down what changed, and why.
5. Put them back in ascending order.

## Requirements

- [ ] Two `min-width` queries, each containing a full rule with a selector
- [ ] Five widths checked, with the computed value written down for each
- [ ] The swapped-order experiment done and explained in one sentence

## Acceptance criteria

- Your five values are 16px, 18px, 18px, 20px, 20px.
- Your explanation says that at 1200px **both** queries match, so the rule that comes later in the file wins.

## Hints

<details><summary>Show hint</summary>

`min-width: 900px` means "900px or wider", so 900px itself counts. And `1.125rem` × 16px = 18px.
</details>
