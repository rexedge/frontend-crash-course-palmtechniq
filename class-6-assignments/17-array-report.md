# Assignment 17 — Array Report

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~35 min
**Prereqs:** Class 6 §11–12 (loops, arrays)
**Build in:** `work/17-array-report/index.html` + `app.js`

---

## Goal

Given a week of daily step counts in an array, write four functions that each answer a different question about it.

## What you'll practice

- Passing an array into a function
- Total, average, "which one is biggest", and "how many pass a test" — the four classic array questions
- The difference between an **index** and a **value**

## Instructions

1. Start with this data:
   ```js
   const steps = [4200, 8100, 10250, 6400, 12050, 3000, 9800];
   ```
2. Write four functions. Each one takes the array as a parameter — don't use `steps` directly inside them.

   | Function | Returns |
   |---|---|
   | `totalSteps(arr)` | the sum of all the days |
   | `averageSteps(arr)` | the mean per day |
   | `bestDay(arr)` | the **day number** (1 to 7) with the most steps |
   | `daysAboveGoal(arr, goal)` | how many days had **more than** `goal` steps |

3. Log the result of each, with a label.
4. Make a second array for a different week, and run all four functions on that too. They should work without any changes.

## Requirements

- [ ] Four functions, each with a loop, each returning a value
- [ ] No "fancy" array methods — only indexes, `.length`, and a `for` loop
- [ ] `averageSteps` calls `totalSteps` instead of repeating its loop
- [ ] `bestDay` returns a day number that starts at 1, not an index that starts at 0
- [ ] All four tested on two different arrays

## Acceptance criteria

For the `steps` array above:

| Call | Result |
|---|---|
| `totalSteps(steps)` | `53800` |
| `averageSteps(steps)` | `7685.714285714285` (or `7686` if you rounded it) |
| `bestDay(steps)` | `5` |
| `daysAboveGoal(steps, 8000)` | `4` |
| `daysAboveGoal(steps, 10000)` | `2` |

## Hints

<details><summary>Show hint</summary>

For `bestDay`, keep track of the **index** of the best day so far — not its value. Start with `let best = 0;`. On each round, compare `arr[i]` with `arr[best]`, and if it's bigger, set `best = i`. At the end, return `best + 1`: people number days from 1.
</details>

## Stretch (optional)

Write `weekSummary(arr, goal)`, which logs one line built from all four functions, such as:
`53800 steps, about 7686 a day. Best: day 5. Over the goal on 4 days.`
