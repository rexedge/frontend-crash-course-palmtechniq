# Assignment 08 — while Loop

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 6 §11 (the `while` loop, the infinite loop)
**Build in:** `work/08-while-loop/index.html` + `app.js`

---

## Goal

Use `while` to keep halving a number until it drops below 1 — a loop where it's hard to say in advance how many rounds there will be.

## What you'll practice

- `while (condition) { ... }`
- Changing the loop's variable **inside** the loop
- Counting rounds with a second variable
- Staying out of an infinite loop

## Instructions

1. Declare `let amount = 100;`.
2. Write a `while` loop that keeps going as long as `amount` is 1 or more. Inside it: halve `amount`, then log it.
3. **Before you save**, point at the line inside the loop that moves `amount` towards the exit. If you can't find one, don't save yet.
4. Predict: how many lines will it log, and what will the last one be?
5. Add `let rounds = 0;` above the loop, add 1 to it on every round, and after the loop log a sentence such as `It took 7 halvings.`
6. Change the starting amount to `1000`. Predict the number of halvings before you run it.

## Requirements

- [ ] A `while` loop, not a `for` loop
- [ ] `amount` is changed inside the loop
- [ ] A counter declared **above** the loop and logged **after** it
- [ ] Predictions made for both starting amounts

## Acceptance criteria

- Starting at 100, the Console shows seven lines: `50`, `25`, `12.5`, `6.25`, `3.125`, `1.5625`, `0.78125` — then `It took 7 halvings.`
- Starting at 1000, it takes 10.
- The last value logged is always below 1. You can say why it gets logged at all.

## Hints

<details><summary>Show hint</summary>

If the tab freezes, `amount` isn't changing. Writing `amount / 2;` on its own works out the answer and throws it away. You need `amount = amount / 2;` to put the answer back in the box. Close the frozen tab, fix the line, and open the page again.
</details>
