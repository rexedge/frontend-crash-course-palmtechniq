# Assignment 22 — Trace the Code

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~40 min
**Prereqs:** all of Class 6 — especially §7, §9, §11–13
**Answer in:** `work/22-trace-the-code/answers.md` first; then check each one in `index.html` + `app.js`

---

## Goal

For each snippet, write down exactly what appears in the Console **before** you run it. Then run it and compare. Reading code and predicting what it does is the skill underneath all debugging.

## What you'll practice

- Stepping through code line by line, the way the browser does
- Tracing a loop in a table
- Noticing the small details: `<=` vs `<`, a missing `return`, a string where you expected a number

## Instructions

1. For each snippet, write your prediction in `answers.md` — every line it logs, in order.
2. For the loops, draw a trace table (Class 6 §11): one row for each round, one column for each variable.
3. Only then type the snippet into `app.js` and run it. Do them one at a time, with an empty file each time.
4. For every snippet you got wrong, write one sentence saying what you missed.

## The snippets

**A**

```js
let x = 3;

function bump(n) {
    n = n + 1;
    return n;
}

bump(x);
console.log(x);
```

**B**

```js
const nums = [1, 2, 3];

for (let i = 0; i <= nums.length; i++) {
    console.log(nums[i]);
}
```

**C**

```js
let total = 0;

for (let i = 1; i < 5; i++) {
    total += i;
}

console.log(total);
```

**D**

```js
console.log(1 + "1");
console.log("5" - 2);
console.log(true + true);
console.log(10 / "a");
```

**E**

```js
function mystery(a, b) {
    if (a > b) return "first";
    if (a < b) return "second";
    return "equal";
    console.log("done");
}

console.log(mystery(4, 4));
```

**F**

```js
function shout(word) {
    word.toUpperCase();
    return word;
}

console.log(shout("hey"));
```

## Requirements

- [ ] Six predictions written down **before** anything is run
- [ ] A trace table for B and for C
- [ ] All six run and compared
- [ ] One sentence for each snippet you got wrong

## Acceptance criteria

- Your notes show honest predictions, wrong ones included. A wrong prediction that you now understand is worth more than a right one you guessed.
- Only **after** all six, open the answers below.

<details><summary>Show answers</summary>

- **A** → `3`. The function gets a **copy** of the number in `x`. Changing `n` inside `bump` doesn't touch `x`. And although `bump(x)` returns `4`, nobody stores or logs that value, so it's thrown away.
- **B** → `1`, `2`, `3`, `undefined`. The condition `i <= nums.length` allows one round too many. `nums[3]` doesn't exist, so it's `undefined`.
- **C** → `10`. The loop runs for `i` = 1, 2, 3, and 4 — it stops before 5 — and 1 + 2 + 3 + 4 is 10.
- **D** → `11`, `3`, `2`, `NaN`. The first is the *string* `"11"`: `+` joins when one side is a string. `-` only does maths, so `"5"` becomes a number. `true` counts as `1` in a sum. And `"a"` can't be turned into a number.
- **E** → `equal`. Neither `if` is true, so the function reaches `return "equal"`. The `console.log("done")` comes after a `return`, so it can never run.
- **F** → `hey`. `.toUpperCase()` gives back a **new** string; it doesn't change `word`. Here the new string isn't stored or returned, so it's lost. Fix: `return word.toUpperCase();`.
</details>
