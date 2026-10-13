# Assignment 15 — Loop Toolkit

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 6 §11–13 (loops, arrays, strings)
**Build in:** `work/15-loop-toolkit/index.html` + `app.js`

---

## Goal

Write eight functions that each have a loop at their heart. Between them they cover the three loop shapes you'll use again and again: build up a total, count the matches, and search for something.

## What you'll practice

- The running-total pattern: a variable above the loop, changed inside it, returned after it
- A loop with an `if` and a counter
- Returning early from inside a loop
- Looping over strings and arrays

## Instructions

Write and test them one at a time. Three logged calls each, with the expected answer in a comment.

| # | Function | What it does |
|---|---|---|
| 1 | `sumTo(n)` | returns 1 + 2 + … + n |
| 2 | `factorial(n)` | returns 1 × 2 × … × n |
| 3 | `countVowels(str)` | returns how many vowels are in the string — capitals count too |
| 4 | `reverseString(str)` | returns the string backwards. Build it with a loop |
| 5 | `multiplicationTable(n)` | **logs** twelve lines, from `1 x n` to `12 x n` |
| 6 | `isPrime(n)` | returns `true` if `n` is a prime number |
| 7 | `fibonacci(n)` | returns the nth number in the sequence 1, 1, 2, 3, 5, 8, 13… |
| 8 | `largestInArray(numbers)` | returns the biggest number in the array — **without** `Math.max` |

`multiplicationTable` is the one function here that's allowed to log. It has nothing to return; printing *is* its job.

## Requirements

- [ ] All eight written and tested
- [ ] Seven of them return a value; only `multiplicationTable` logs
- [ ] Every running total or counter is declared **above** its loop
- [ ] Every final `return` is **below** its loop's closing brace
- [ ] `largestInArray` gives the right answer for an array of negative numbers

## Acceptance criteria

| Call | Result |
|---|---|
| `sumTo(4)` · `sumTo(100)` | `10` · `5050` |
| `factorial(5)` · `factorial(1)` · `factorial(10)` | `120` · `1` · `3628800` |
| `countVowels("Apple")` · `countVowels("SKY")` | `2` · `0` |
| `reverseString("hello")` | `olleh` |
| `multiplicationTable(7)` | twelve lines, from `1 x 7 = 7` to `12 x 7 = 84` |
| `isPrime(2)` · `(9)` · `(13)` · `(1)` | `true` · `false` · `true` · `false` |
| `fibonacci(1)` · `(2)` · `(6)` · `(10)` | `1` · `1` · `8` · `55` |
| `largestInArray([3, 9, 4])` · `largestInArray([-5, -2, -9])` | `9` · `-2` |

## Hints

<details><summary>Show hint</summary>

- **`factorial`** — start the result at `1`, not `0`. Anything multiplied by 0 stays 0.
- **`reverseString`** — start with an empty string. Either loop **backwards**, from index `str.length - 1` down to `0`, adding each character on the end; or loop forwards, and put each character on the **front**: `result = str[i] + result`.
- **`isPrime`** — try dividing `n` by every number from 2 up to `n - 1`. If any of them divides exactly (`n % i === 0`), return `false` straight away. If the loop finishes without finding one, return `true`. Numbers below 2 aren't prime — deal with those first.
- **`fibonacci`** — each number is the sum of the two before it. Keep two variables for "the last two numbers", and move them along on every round.
- **`largestInArray`** — start with `numbers[0]`, not with `0`. If you start at `0`, an array of negative numbers gives you `0`, which isn't even in the array.
</details>

## Stretch (optional)

Make `isPrime` quicker. You only need to test divisors while `i * i <= n` — if nothing up to that point divides `n`, nothing bigger will either. Check that `isPrime(97)` is still `true`.
