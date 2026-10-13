# Assignment 01 — Declare and Log

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 6 §4–6 (connecting a script, variables, data types, template literals)
**Build in:** `work/01-declare-and-log/index.html` + `app.js`

---

## Goal

Connect your first script, make three variables of three different types, and log them — one at a time, then all together in a single sentence.

## What you'll practice

- `<script src="app.js"></script>` at the end of `<body>`
- Choosing between `const` and `let`
- A string, a number, and a boolean
- A template literal with `${ }`

## Instructions

1. Create `index.html` from the starter page in [work/README.md](work/README.md), and an empty `app.js` beside it. Open `index.html` with Live Server, then open the Console.
2. In `app.js`, declare three variables:
   - a `const` for your first name
   - a `let` for your age
   - a `const` boolean called `isStudent`
3. `console.log` each one on its own line.
4. Log **one** template-literal sentence that uses all three, for example:
   `My name is Ada, I am 28, and it is true that I am a student.`
5. It's your birthday. On a new line, add 1 to your age, and log the sentence again.
6. Now try to change your first name to a different name. Read the red message in the Console, then delete that line.

## Requirements

- [ ] `app.js` is loaded by a `<script>` tag at the end of `<body>`
- [ ] Three variables: one string, one number, one boolean
- [ ] The name is a `const`; the age is a `let`
- [ ] One template literal (backticks) that uses all three variables
- [ ] You saw the `Assignment to constant variable` error, and you read it

## Acceptance criteria

- The Console shows three single values, then two sentences — the second with the age one higher.
- The sentence is one template literal. No `+` signs are used to join strings.
- When you've finished, there's no red in the Console.

## Hints

<details><summary>Show hint</summary>

If the Console shows `${firstName}` exactly as you typed it, you used ordinary quotes. Only backticks fill in the gaps — the key at the top left of most keyboards, under `Esc`.
</details>
