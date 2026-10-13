# Assignment 04 — Comparisons

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 6 §8 (comparisons and logic)
**Build in:** `work/04-comparisons/index.html` + `app.js`

---

## Goal

Predict the answer to seven comparisons, then check them. By the end you should know exactly why this course only uses `===`.

## What you'll practice

- `==` vs `===`
- `&&`, `||`, and `!`
- Working out a combined condition one piece at a time

## Instructions

1. In a comment, write `true` or `false` for each of these:

   ```js
   5 == "5"
   5 === "5"
   0 === false
   "" === false
   10 > 3 && 3 > 5
   10 > 3 || 3 > 5
   !(5 > 2)
   ```
2. Log each one and compare with your predictions.
3. For any you got wrong, add a one-line comment saying why.
4. Add two of your own: one using `&&` that comes out `true`, and one using `||` that comes out `false`.

## Requirements

- [ ] Seven predictions written down first
- [ ] Seven comparisons logged
- [ ] Two of your own, one `&&` and one `||`
- [ ] A comment explaining the difference between the first two lines

## Acceptance criteria

- The seven lines, in order: `true`, `false`, `false`, `false`, `false`, `true`, `false`.
- Your comment says that `==` changes the types before comparing, and `===` doesn't — so a number is never `===` to a string.
- This is the only file in the course where you write `==`. From here on it's always `===`.

## Hints

<details><summary>Show hint</summary>

Work out `&&` and `||` in two steps. First each side on its own, then join them: `10 > 3 && 3 > 5` → `true && false` → `false`.
</details>
