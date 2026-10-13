# Assignment 07 — for Loop

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 6 §11 (the `for` loop)
**Build in:** `work/07-for-loop/index.html` + `app.js`

---

## Goal

Write three counting loops — up, evens only, and down — by changing the three parts of the `for` header.

## What you'll practice

- The start, the condition, and the step
- Counting in steps other than 1
- Counting backwards
- Predicting how many times a loop runs

## Instructions

1. Log the numbers 1 to 20.
2. Log only the **even** numbers from 1 to 20. Do it two ways:
   - by changing the step, so the loop jumps 2 at a time
   - by keeping a step of 1, with an `if (i % 2 === 0)` inside the loop
3. Log the numbers from 20 **down** to 1.
4. Before you run each loop, write a comment above it saying how many lines you expect.

## Requirements

- [ ] 1 to 20
- [ ] The evens, both ways
- [ ] 20 down to 1
- [ ] A predicted line count above each of the four loops

## Acceptance criteria

- The first loop logs 20 lines, starting at `1` and ending at `20`.
- Both even loops log the same ten lines: `2`, `4`, … `20`.
- The countdown starts at `20` and ends at `1` — not `0`.
- All four of your predictions were right. (If one wasn't, write down why.)

## Hints

<details><summary>Show hint</summary>

A countdown changes **all three** parts: start high (`let i = 20`), keep going while `i >= 1`, and step with `i--`. If the tab freezes, the condition can never become false — check you didn't leave `i++` in a loop that's meant to count down.
</details>
