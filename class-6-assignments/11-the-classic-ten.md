# Assignment 11 — The Classic Ten

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 6 §9–14, §16 (guided practice)
**Build in:** `work/11-the-classic-ten/index.html` + `app.js`

---

## Goal

Write ten small functions that each **return** an answer, and test every one. This carries straight on from the calculator toolkit in the lesson's guided practice. Keep the file — Class 7 connects `celsiusToFahrenheit` to a real page.

## What you'll practice

- Parameters, arguments, and `return`
- Choosing between a plain sum, an `if`, and a loop
- Testing with several calls, including awkward ones

## Instructions

1. Write the functions **one at a time**. After each one, save and check the Console before you start the next.
2. For each function, log at least three calls. Put the answer you expect in a comment beside each call.

| # | Function | What it returns |
|---|---|---|
| 1 | `add(a, b)` | the sum |
| 2 | `isEven(n)` | `true` or `false` |
| 3 | `maxOfTwo(a, b)` | the larger of the two |
| 4 | `celsiusToFahrenheit(c)` | the temperature in °F |
| 5 | `circleArea(r)` | the area (use `Math.PI`) |
| 6 | `absoluteValue(n)` | the number without its minus sign — **without** using `Math.abs` |
| 7 | `average(a, b, c)` | the mean of three numbers |
| 8 | `secondsToClock(total)` | a string in the form `"MM:SS"` |
| 9 | `initials(fullName)` | the first letter of each word, in capitals |
| 10 | `isVowel(char)` | `true` or `false` |

## Requirements

- [ ] All ten written, each one returning a value
- [ ] No `console.log` inside any of the ten functions
- [ ] At least three logged test calls for each, with the expected answer in a comment
- [ ] `absoluteValue` doesn't use `Math.abs`
- [ ] `secondsToClock` always gives two digits on each side of the colon
- [ ] `initials` and `isVowel` give the right answer whatever capitals you pass in

## Acceptance criteria

| Call | Result |
|---|---|
| `add(2, 3)` | `5` |
| `isEven(4)` · `isEven(7)` · `isEven(0)` | `true` · `false` · `true` |
| `maxOfTwo(3, 9)` · `maxOfTwo(4, 4)` | `9` · `4` |
| `celsiusToFahrenheit(0)` · `(100)` · `(-40)` | `32` · `212` · `-40` |
| `circleArea(1)` | `3.141592653589793` |
| `absoluteValue(-8)` · `(8)` · `(0)` | `8` · `8` · `0` |
| `average(10, 20, 30)` | `20` |
| `secondsToClock(75)` · `(5)` · `(600)` | `01:15` · `00:05` · `10:00` |
| `initials("Ada Byron King")` · `initials("ada lovelace")` | `ABK` · `AL` |
| `isVowel("a")` · `isVowel("E")` · `isVowel("z")` | `true` · `true` · `false` |

## Hints

<details><summary>Show hint</summary>

- **`average`** — remember the brackets. `a + b + c / 3` only divides `c`.
- **`secondsToClock`** — the minutes are `Math.floor(total / 60)`, and the seconds are `total % 60`. To pad a part to two digits: if it's less than 10, put a `"0"` in front of it. A ternary does that neatly.
- **`initials`** — loop over the characters. A character is an initial if it's the very first one (`i === 0`), or if the character just before it, `fullName[i - 1]`, is a space. Start with an empty string and add to it with `+=`.
- **`isVowel`** — lower-case the character first. Then either compare it with each of the five vowels using `||`, or ask whether the string `"aeiou"` includes it.
</details>

## Stretch (optional)

Make `secondsToClock` cope with an hour or more, so that `secondsToClock(3665)` gives `1:01:05`.
