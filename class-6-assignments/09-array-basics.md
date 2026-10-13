# Assignment 09 — Array Basics

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 6 §12 (arrays)
**Build in:** `work/09-array-basics/index.html` + `app.js`

---

## Goal

Make an array, read from both ends of it, add to it, and loop over it.

## What you'll practice

- Creating an array
- Indexes that start at 0
- `.length`, and the last item at `length - 1`
- `.push`
- The standard array loop

## Instructions

1. Make `const cities`, an array of five city names.
2. Log its `.length`.
3. Log the first city and the last city. Find the last one with `cities[cities.length - 1]` — not with a number you counted yourself.
4. `.push` a sixth city onto the end. Log the length and the last city again. (The same line of code now finds the *new* last city. That's why you didn't type a number.)
5. Loop over the array with `for`, and log one line per city in this style: `City 1: Lagos`.
6. Log `cities[10]`. In a comment, explain what you got.

## Requirements

- [ ] Five strings in a `const` array
- [ ] The last item found with `length - 1`
- [ ] One `.push`
- [ ] A `for` loop with `i < cities.length` as its condition
- [ ] The output is numbered from 1, even though the indexes start at 0

## Acceptance criteria

- The length logs as `5`, then as `6` after the push.
- The "last city" line prints your sixth city after the push, without being changed.
- Six lines, from `City 1: …` to `City 6: …`. There's no `City 0`, and no `undefined`.
- `cities[10]` logs `undefined`, with no error.

## Hints

<details><summary>Show hint</summary>

Inside the loop you need two different things: `${i + 1}` for the label a person reads, and `cities[i]` for the item itself.
</details>
