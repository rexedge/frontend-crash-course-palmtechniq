# Assignment 06 — Ternary

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 6 §10 (the ternary)
**Build in:** `work/06-ternary/index.html` + `app.js`

---

## Goal

Take a two-way decision written as an `if` / `else`, and rewrite it as a single line with the ternary operator.

## What you'll practice

- `condition ? valueIfTrue : valueIfFalse`
- Using a ternary straight after `return`
- Knowing when a ternary is the right tool, and when it isn't

## Instructions

1. Write `describeSign(n)` the long way, with `if` / `else`. It returns `"positive-ish"` when `n` is 0 or more, and `"negative"` otherwise. (Zero counts as "positive-ish" here — that's what keeps it a two-way choice.) Test it with `5`, `0`, and `-3`.
2. Turn the long version into a comment. Underneath, write the function again with a one-line body:
   ```js
   return n >= 0 ? "positive-ish" : "negative";
   ```
3. Run the same three tests. The output must be the same.
4. Write two more functions whose whole body is one `return` with a ternary:
   - `evenOrOdd(n)` → `"even"` or `"odd"`
   - `passOrFail(score)` → `"pass"` for 50 or more, otherwise `"fail"`

## Requirements

- [ ] `describeSign` written both ways (the long version kept as a comment)
- [ ] `evenOrOdd` and `passOrFail`, each with a one-line body
- [ ] Three logged calls for each function, including the boundary value
- [ ] No ternary with more than two outcomes

## Acceptance criteria

- `describeSign(5)` → `positive-ish`. `describeSign(0)` → `positive-ish`. `describeSign(-3)` → `negative`.
- `passOrFail(49)` → `fail`. `passOrFail(50)` → `pass`.
- `evenOrOdd(0)` → `even`.

## Hints

<details><summary>Show hint</summary>

A ternary **is** a value, so it goes wherever a value can go: after `return`, or after `=`. Read the `?` as "then" and the `:` as "otherwise".
</details>
