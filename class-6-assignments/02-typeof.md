# Assignment 02 — typeof

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 6 §6–7 (data types, the `+` trap)
**Build in:** `work/02-typeof/index.html` + `app.js`

---

## Goal

Predict the type of nine values, then check each one with `typeof`. Two of them surprise almost everybody.

## What you'll practice

- The five data types from this class
- `typeof` as a quick way to check what you really have
- Spotting the difference between `7` and `"7"`

## Instructions

1. In a comment at the top of `app.js`, write your prediction for the `typeof` each of these:

   `"hi"` · `42` · `true` · `null` · `undefined` · `3.14` · `"7"` · `2 + 2` · `"2" + 2`

2. Now log each one:
   ```js
   console.log(typeof "hi");
   ```
3. For the last two, put the sum in brackets: `typeof (2 + 2)` and `typeof ("2" + 2)`. Without the brackets, `typeof` only looks at the first value and the `+` happens afterwards.
4. Mark each prediction right or wrong.
5. For the two that surprised you, add a one-line comment saying why the answer is what it is.

## Requirements

- [ ] All nine predicted **before** running anything
- [ ] All nine logged with `typeof`
- [ ] The two sums are inside brackets
- [ ] A one-line explanation for each of your two surprises

## Acceptance criteria

- The nine lines, in order: `string`, `number`, `boolean`, `object`, `undefined`, `number`, `string`, `number`, `string`.
- Your comments explain `typeof null` (an old mistake in the language that can't be fixed) and `"2" + 2` (`+` joins when either side is a string, so the result is the string `"22"`).

## Hints

<details><summary>Show hint</summary>

`42` and `3.14` are the same type. JavaScript has one number type for whole numbers and decimals alike.
</details>
