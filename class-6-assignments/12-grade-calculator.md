# Assignment 12 — Grade Calculator

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~25 min
**Prereqs:** Class 6 §10 (`if` ladders, testing the edges, checking for bad input first)
**Build in:** `work/12-grade-calculator/index.html` + `app.js`

---

## Goal

Write `letterGrade(score)`, which turns a score out of 100 into a letter — and refuses scores that can't be real.

## What you'll practice

- A five-step `if` / `else if` ladder, in the right order
- Dealing with bad input at the top of a function
- Testing every boundary

## Instructions

1. Write `letterGrade(score)` so that it returns:

   | Score | Returns |
   |---|---|
   | 90 or more | `"A"` |
   | 80–89 | `"B"` |
   | 70–79 | `"C"` |
   | 60–69 | `"D"` |
   | below 60 | `"F"` |
   | below 0, or above 100 | `"invalid"` |

2. Check for the invalid scores **first**, and return straight away.
3. Then write the ladder from the top grade down.
4. Test the boundaries: log `letterGrade` for 89, 90, 0, 100, -1, and 101. Then test both sides of the other boundaries: 79 and 80, 69 and 70, 59 and 60.

## Requirements

- [ ] The function returns one of six strings, and never logs
- [ ] Invalid scores are caught before the ladder starts
- [ ] Each rung of the ladder has **one** comparison — no `score >= 80 && score < 90`
- [ ] At least 12 logged test calls, covering both sides of every boundary

## Acceptance criteria

- 89 → `B`, 90 → `A`, 0 → `F`, 100 → `A`, -1 → `invalid`, 101 → `invalid`.
- 79 → `C`, 80 → `B`, 69 → `D`, 70 → `C`, 59 → `F`, 60 → `D`.
- You can explain why `score >= 80` on its own is enough for the `B` rung.

## Hints

<details><summary>Show hint</summary>

A ladder stops at the first condition that's true. By the time JS reaches `score >= 80`, it already knows the score is **not** 90 or more — otherwise it would have returned `"A"`. So you don't need to check the top of the band again. That only works if the strictest test comes first.
</details>

## Stretch (optional)

Write `gradeReport(scores)`. It takes an **array** of scores and logs one line for each, such as `Score 85: B`, by calling `letterGrade` inside a loop.
