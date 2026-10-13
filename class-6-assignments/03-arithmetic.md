# Assignment 03 — Arithmetic

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 6 §7 (operators)
**Build in:** `work/03-arithmetic/index.html` + `app.js`

---

## Goal

Run all six arithmetic operators on the same two numbers, and explain what the remainder operator `%` gave you.

## What you'll practice

- `+` `-` `*` `/` `%` `**`
- Template literals for readable output
- What a remainder is, and what it's useful for

## Instructions

1. Declare `const a = 17;` and `const b = 5;`.
2. Log `a + b`, `a - b`, `a * b`, `a / b`, `a % b`, and `a ** 2`. Use a template literal for each, so the output reads like `17 + 5 = 22`.
3. In a comment, say what `%` gave you, and why.
4. Change `b` to `2`. Predict all six results again before you save.
5. Now try a few different values of `a` (8, 9, 100, 101) and look only at `a % 2`. What does the answer tell you about `a`?

## Requirements

- [ ] Six operations logged, each labelled so the output makes sense on its own
- [ ] A comment explaining the remainder
- [ ] Repeated with `b = 2`, predicted first
- [ ] A one-line comment saying what `a % 2` tells you

## Acceptance criteria

- With 17 and 5: `22`, `12`, `85`, `3.4`, `2`, `289`.
- With 17 and 2: `19`, `15`, `34`, `8.5`, `1`, `289`.
- Your comment says that 5 goes into 17 three times (15), with 2 left over.
- You can say what `a % 2` is for an even number and for an odd number.

## Hints

<details><summary>Show hint</summary>

One line of the output: `` console.log(`${a} + ${b} = ${a + b}`); `` — the first two `${ }` drop in the variables, and the third one does the sum.
</details>
