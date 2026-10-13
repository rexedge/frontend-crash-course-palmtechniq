# Assignment 16 — Tip / Bill Splitter

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~25 min
**Prereqs:** Class 6 §9–10, §14 (functions, checking for bad input, rounding to 2 decimal places)
**Build in:** `work/16-tip-bill-splitter/index.html` + `app.js`

---

## Goal

Write `splitBill(total, tipPercent, people)`, which returns what **each person pays** when a group shares a bill and a tip.

## What you'll practice

- A function with three parameters
- Percentages
- Rounding money to 2 decimal places
- Dealing with an input that would break the maths

## Instructions

1. Write `splitBill(total, tipPercent, people)`:
   - work out the tip — `tipPercent` is a whole number, so `15` means 15%
   - add it to the total
   - divide by the number of people
   - round to 2 decimal places with `Math.round(x * 100) / 100`
   - return the result
2. Deal with `people` being `0` (or less). Decide what the function should return, and write your decision in a comment above it.
3. Log four test calls.
4. Log one formatted summary line using a template literal, such as:
   `Bill 100 + 15% tip, split 4 ways: 28.75 each`

## Requirements

- [ ] The function returns a **number**, rounded to 2 decimal places
- [ ] `people` of `0` is dealt with before any dividing happens
- [ ] At least four logged test calls, including one with 1 person and one with 0 people
- [ ] One summary line built with a template literal

## Acceptance criteria

| Call | Result |
|---|---|
| `splitBill(100, 15, 4)` | `28.75` |
| `splitBill(100, 0, 3)` | `33.33` |
| `splitBill(80, 20, 1)` | `96` |
| `splitBill(100, 15, 0)` | whatever you decided — but not `Infinity` and not `NaN` |

## Hints

<details><summary>Show hint</summary>

The tip is `total * tipPercent / 100`. For the zero check, put an `if` at the very top of the function and `return` early — returning `0` is a sensible choice. Without it, JS doesn't give an error for dividing by zero. It gives `Infinity`, which is worse: the program carries on with a nonsense number.
</details>

## Stretch (optional)

Write `tipOptions(total, people)`. It loops over the array `[10, 15, 20]` and logs what each person pays at each tip level, by calling `splitBill` three times.
