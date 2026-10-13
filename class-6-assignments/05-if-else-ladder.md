# Assignment 05 — if/else Ladder

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 6 §9–10 (functions, `if` / `else if` / `else`)
**Build in:** `work/05-if-else-ladder/index.html` + `app.js`

---

## Goal

Write `describeNumber(n)`, a function that sorts any number into one of three groups: negative, zero, or positive.

## What you'll practice

- A function with one parameter and a `return`
- `if` / `else if` / `else`
- Testing a function with several calls

## Instructions

1. Write `function describeNumber(n)`. Inside, use an `if` / `else if` / `else` ladder to **return** `"negative"`, `"zero"`, or `"positive"`.
2. Log five calls: a negative number, `0`, a positive number, a negative decimal such as `-0.5`, and a very large number.
3. Now change the order of your conditions and run it again. Does the output change?
4. Compare with `describeTemperature` in the lesson (Class 6 §10), where the order matters a lot. In a comment, say why it matters there and not here.

## Requirements

- [ ] One function with an `if`, an `else if`, and an `else`
- [ ] It **returns** one of three strings — there's no `console.log` inside the function
- [ ] Five logged calls, including `0` and a negative decimal
- [ ] A comment answering the question in step 4

## Acceptance criteria

- `describeNumber(-5)` → `negative`. `describeNumber(0)` → `zero`. `describeNumber(7)` → `positive`. `describeNumber(-0.5)` → `negative`.
- Your comment says that here the three conditions never overlap — a number can't be negative *and* zero — so the order makes no difference. In `describeTemperature`, 31 passes several of the tests, so the first one wins.

## Hints

<details><summary>Show hint</summary>

Three outcomes only need **two** conditions. Whatever isn't negative and isn't zero must be positive — that's the `else`.
</details>
