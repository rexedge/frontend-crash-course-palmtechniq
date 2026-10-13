# Assignment 10 — String Methods

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 6 §13 (more with strings)
**Build in:** `work/10-string-methods/index.html` + `app.js`

---

## Goal

Use one property and four methods on the same string — and prove to yourself that none of them changes the original.

## What you'll practice

- `.length`
- `.toUpperCase()` and `.toLowerCase()`
- `.includes()`
- `.slice()` and counting indexes

## Instructions

1. Declare `const s = "Frontend Crash Course";`.
2. Log:
   - its length
   - the string in upper case
   - the string in lower case
   - whether it includes `"Crash"`
   - its first word, using `.slice`
3. Slice out the other two words as well: `Crash`, and `Course`.
4. Log `s` itself at the very end. Has anything changed it?
5. Write `shout(text)`, which **returns** the text in capitals with a `!` on the end. `shout("hello")` gives `HELLO!`.

## Requirements

- [ ] `.length` is written without brackets; every method is written with them
- [ ] All three words sliced out
- [ ] `s` logged at the end, unchanged
- [ ] `shout` returns its result, and is tested with three logged calls

## Acceptance criteria

- The Console shows, in order: `21`, `FRONTEND CRASH COURSE`, `frontend crash course`, `true`, `Frontend`, `Crash`, `Course`, and then the original string.
- `s.includes("crash")` is `false`, and you can say why.
- `shout("hello")` → `HELLO!`

## Hints

<details><summary>Show hint</summary>

Count the indexes from 0, and remember that a space is a character too. `Frontend` sits at indexes 0 to 7, so it's `s.slice(0, 8)` — the end index is the first one you *don't* want. For the last word you only need a start: `s.slice(15)`.
</details>
