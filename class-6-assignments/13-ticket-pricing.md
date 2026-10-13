# Assignment 13 — Ticket Pricing

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 6 §8–10 (comparisons, functions, `if` ladders)
**Build in:** `work/13-ticket-pricing/index.html` + `app.js`

---

## Goal

Write `ticketPrice(age, isWeekend)`, which works out the price of a cinema ticket from two inputs: a number and a boolean.

## What you'll practice

- A function with two parameters of different types
- Combining an age ladder with a second, separate rule
- Using a `let` that gets adjusted before it's returned
- Testing every branch

## Instructions

1. The rules:
   - The base price is **$12**.
   - Under 5 → **free**.
   - Age 5 to 17 → **half price**.
   - Age 65 or over → **$8** flat.
   - At the weekend, add **$3** to any ticket that isn't free.
2. Write `ticketPrice(age, isWeekend)`. `isWeekend` is `true` or `false`. Return the final price as a **number** — no `$` sign.
3. Test every row and both columns of the table in the acceptance criteria: twelve calls.

## Requirements

- [ ] The function returns a number, and never logs
- [ ] The weekend rule is written **once**, not repeated inside every age branch
- [ ] A free ticket stays free at the weekend
- [ ] All twelve combinations in the table are tested

## Acceptance criteria

| Age | Weekday (`false`) | Weekend (`true`) |
|---|---|---|
| 3 | `0` | `0` |
| 5 | `6` | `9` |
| 17 | `6` | `9` |
| 18 | `12` | `15` |
| 64 | `12` | `15` |
| 65 | `8` | `11` |

## Hints

<details><summary>Show hint</summary>

Do it in two stages. First, the age: return `0` straight away for under-5s; otherwise put the right price in a `let price`. Second, after the ladder, one line: `if (isWeekend) { price += 3; }`. Then return `price`. Because the under-5s have already been returned, the weekend rule can't touch them.

Notice that `if (isWeekend)` needs no `=== true`. `isWeekend` already *is* `true` or `false`.
</details>

## Stretch (optional)

Return `"invalid"` for an age below 0 or above 120.
