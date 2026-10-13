# Assignment 18 — Password Strength (Logic Only)

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min
**Prereqs:** Class 6 §10–11, §13 (`if`, loops, looping over a string, comparing characters)
**Build in:** `work/18-password-strength/index.html` + `app.js`

---

## Goal

Write `passwordScore(pw)`, which looks at a password one character at a time and rates it `"weak"`, `"ok"`, or `"strong"`. It's logic only for now — in Class 7 this kind of function gets connected to a real input box.

## What you'll practice

- Looping over the characters of a string
- Boolean "flag" variables: start at `false`, switch to `true` when you find something
- Adding up a score from several separate checks
- Turning a number into a label with an `if` ladder

## Instructions

1. The score starts at `0`. Add points like this:

   | Rule | Points |
   |---|---|
   | 8 characters or more | +1 |
   | contains a digit | +1 |
   | contains an upper-case letter | +1 |
   | contains a lower-case letter | +1 |
   | 12 characters or more | +1 |

2. Then return a label: a score of 0–2 is `"weak"`, 3 is `"ok"`, and 4–5 is `"strong"`.
3. Loop over the password **once**, character by character. Use three flags — `hasDigit`, `hasUpper`, `hasLower` — that all start as `false`.
4. After the loop, add up the points and return the label.
5. Test with at least seven passwords, including an empty string.

## Requirements

- [ ] One loop over the characters, using `pw[i]`
- [ ] Three boolean flags, declared above the loop
- [ ] The score is added up **after** the loop, not inside it
- [ ] The function returns one of three strings, and never logs
- [ ] At least seven logged test calls

## Acceptance criteria

| Password | Score | Returns |
|---|---|---|
| `""` | 0 | `weak` |
| `"password"` | 2 | `weak` |
| `"12345678"` | 2 | `weak` |
| `"Password"` | 3 | `ok` |
| `"abcdefghijkl"` | 3 | `ok` |
| `"Password1"` | 4 | `strong` |
| `"MyDogBarks2Loud"` | 5 | `strong` |

## Hints

<details><summary>Show hint</summary>

Three tests for one character, `c`:

- **A digit:** `c >= "0" && c <= "9"`. Strings compare in dictionary order, and the ten digits sit next to each other.
- **An upper-case letter:** `c !== c.toLowerCase()`. Lower-casing a capital letter changes it, so the two are different.
- **A lower-case letter:** `c !== c.toUpperCase()`.

Be careful with the "obvious" test, `c === c.toUpperCase()`. It's also true for digits and symbols — `"7".toUpperCase()` is still `"7"` — so `"12345678"` would count as having capital letters.
</details>

## Stretch (optional)

Add a sixth rule: +1 if the password contains a symbol — a character that is not a digit and not a letter. Then move the bands so that `"strong"` needs 5 or more.
