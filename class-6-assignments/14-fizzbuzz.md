# Assignment 14 — FizzBuzz

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 6 §7, §10–11 (the `%` operator, `if` ladders, `for` loops)
**Build in:** `work/14-fizzbuzz/index.html` + `app.js`

---

## Goal

Solve the most famous beginner puzzle in programming — then tidy it up, so the **deciding** and the **looping** live in separate places.

## What you'll practice

- `%` to test "is this a multiple of…?"
- Why the order of an `if` ladder matters
- Moving a decision out of a loop and into a function

## Instructions

1. **Version 1.** Loop from 1 to 100. For each number, log:
   - `Fizz` if it's a multiple of 3
   - `Buzz` if it's a multiple of 5
   - `FizzBuzz` if it's a multiple of both
   - otherwise, the number itself
2. Check the first 15 lines against the acceptance criteria before you go on.
3. **Version 2.** Move the decision into a function, `fizzbuzz(n)`, which **returns** the right value for one number. Then the loop has one job left:
   ```js
   for (let i = 1; i <= 100; i++) {
       console.log(fizzbuzz(i));
   }
   ```
4. Now that it's a function, test single values directly: log `fizzbuzz(3)`, `fizzbuzz(5)`, `fizzbuzz(15)`, and `fizzbuzz(98)`.

## Requirements

- [ ] Both versions work (turn Version 1 into a comment once Version 2 is done)
- [ ] `fizzbuzz(n)` returns a value and never logs
- [ ] The loop in Version 2 contains no `if`
- [ ] Four single values tested outside the loop

## Acceptance criteria

- The first 15 lines: `1`, `2`, `Fizz`, `4`, `Buzz`, `Fizz`, `7`, `8`, `Fizz`, `Buzz`, `11`, `Fizz`, `13`, `14`, `FizzBuzz`.
- The last three lines: `98`, `Fizz`, `Buzz`.
- `fizzbuzz(15)` returns `FizzBuzz` — not `Fizz`.

## Hints

<details><summary>Show hint</summary>

If 15 comes out as `Fizz`, your ladder tests for 3 first. 15 passes that test, and JS never looks any further. Test for **both** first: `n % 3 === 0 && n % 5 === 0` (or, shorter, `n % 15 === 0`).
</details>

## Stretch (optional)

Count them. Add three counters and work out how many of the 100 lines are `Fizz`, how many are `Buzz`, and how many are `FizzBuzz`. (You should get 27, 14, and 6.)
