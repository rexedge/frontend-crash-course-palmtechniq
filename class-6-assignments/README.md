# Class 6 Assignments — JavaScript Basics

Practice for **Class 6**. Read the lesson first:
[../class-6-javascript-basics.md](../class-6-javascript-basics.md)

---

## How to use this folder

- Do **all warm-ups (01–10)** in order — they follow the lesson section by section, from your first variable to string methods.
- Work through the **core set (11–19)** — the real function-writing. Finish at least **11 (the classic ten)** and **19 (five logic functions)**: 11 carries straight on from the lesson's calculator hands-on, and 19 is the course homework. **15** is strongly recommended too — it's the loop patterns you'll use for the rest of your life.
- Do **debug (23)** and pick from **challenge (20–22)** as time allows. **22 (trace the code)** is the quickest of the three, and well worth it.
- Answer the **written questions (24)** from memory, in a text file.
- Put your code in `work/<assignment-slug>/` — an `index.html` **and** an `app.js`. See [work/README.md](work/README.md) for the starter page.
- **Type everything by hand.** Save, then check the **Console** after every change. In this class the page stays blank — the Console is where your work shows up, so keep it open (`F12`).

## Scope — only what's been taught

Use only Class 1–6 material. Everything here runs in the Console.

**In scope this class:**
- `<script src="app.js"></script>` at the end of `<body>`
- `console.log`, the dev-tools Console, and reading error messages
- Comments: `//` and `/* */`
- `let` and `const`
- Data types: string, number, boolean, `undefined`, `null` — and `typeof`
- Template literals: `` `Hello, ${firstName}!` ``
- Arithmetic: `+` `-` `*` `/` `%` `**`, and the shortcuts `+=` `-=` `*=` `++` `--`
- `Number()` to turn a string into a number; what `NaN` means
- Comparisons: `===` `!==` `>` `<` `>=` `<=`
- Logic: `&&` `||` `!`
- Functions: declaring, parameters and arguments, `return`, one function calling another
- `if` / `else if` / `else`, and the ternary `? :`
- `for` and `while` loops
- Arrays: creating, indexes, `.length`, `.push`, looping over
- Strings: indexes, `.length`, `.toUpperCase()`, `.toLowerCase()`, `.includes()`, `.slice()`
- `Math.round`, `Math.floor`, `Math.max`, `Math.random`, `Math.PI`

**Not yet — do not use:**
- The DOM: `document`, `querySelector`, changing anything on the page — that's Class 7
- Events and `addEventListener` — also Class 7
- `prompt()`, `alert()`, `confirm()` — every input in this class is an argument you pass to a function
- Objects (`{ key: value }`) and arrow functions (`=>`)
- Array and string methods beyond the ones listed: no `.map`, `.filter`, `.forEach`, `.sort`, `.reverse`, `.split`, `.join`, `.indexOf`
- `var`

If you find a solution online that uses something from the "not yet" list, there is always a way to do the same job with a loop and an `if`. That's the way to practise here.

## Difficulty / time key

| Mark | Meaning |
|---|---|
| ⭐ | ~5–15 min — a drill |
| ⭐⭐ | ~20–45 min — a real mini-build |
| ⭐⭐⭐ | ~1 hr+ — combines several ideas, expect to debug |
| 🧵 | feeds into the Class 8 capstone — keep the file |

---

## The assignments

### Warm-ups
| # | Title | Difficulty |
|---|---|---|
| [01](01-declare-and-log.md) | Declare and log | ⭐ |
| [02](02-typeof.md) | typeof | ⭐ |
| [03](03-arithmetic.md) | Arithmetic | ⭐ |
| [04](04-comparisons.md) | Comparisons | ⭐ |
| [05](05-if-else-ladder.md) | if/else ladder | ⭐ |
| [06](06-ternary.md) | Ternary | ⭐ |
| [07](07-for-loop.md) | for loop | ⭐ |
| [08](08-while-loop.md) | while loop | ⭐ |
| [09](09-array-basics.md) | Array basics | ⭐ |
| [10](10-string-methods.md) | String methods | ⭐ |

### Core
| # | Title | Difficulty |
|---|---|---|
| [11](11-the-classic-ten.md) | The classic ten | ⭐⭐ |
| [12](12-grade-calculator.md) | Grade calculator | ⭐⭐ |
| [13](13-ticket-pricing.md) | Ticket pricing | ⭐⭐ |
| [14](14-fizzbuzz.md) | FizzBuzz | ⭐⭐ |
| [15](15-loop-toolkit.md) | Loop toolkit | ⭐⭐ |
| [16](16-tip-bill-splitter.md) | Tip / bill splitter | ⭐⭐ |
| [17](17-array-report.md) | Array report | ⭐⭐ |
| [18](18-password-strength.md) | Password strength (logic only) | ⭐⭐ |
| [19](19-five-logic-functions.md) | Course homework: five logic functions | ⭐⭐ 🧵 |

### Challenge
| # | Title | Difficulty |
|---|---|---|
| [20](20-console-mini-games.md) | Console mini-games | ⭐⭐⭐ |
| [21](21-simple-cart-total.md) | Simple cart total | ⭐⭐⭐ |
| [22](22-trace-the-code.md) | Trace the code | ⭐⭐⭐ |

### Debug & review
| # | Title | Difficulty |
|---|---|---|
| [23](23-debug-broken-functions.md) | Debug: broken functions | ⭐⭐ |
| [24](24-written-questions.md) | Written questions | ⭐ |

---

## Definition of done for Class 6

- [ ] Warm-ups 01–10 complete; you can type `for (let i = 0; i < items.length; i++)` from memory
- [ ] Core 11 and 19 complete and hitting every checklist item (15 strongly recommended)
- [ ] Every function you wrote **returns** its answer, and is tested with at least three logged calls — including one awkward value
- [ ] Every file you built this class runs with **no red in the Console**
- [ ] Debug 23 complete, with the cause of each bug written in your own words
- [ ] Written questions 24 answered without looking
- [ ] No DOM, no `prompt` / `alert`, no objects, and no array methods beyond `.push` used anywhere
