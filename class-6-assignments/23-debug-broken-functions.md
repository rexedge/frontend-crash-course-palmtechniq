# Assignment 23 — Debug: Broken Functions

**Type:** Debug · **Difficulty:** ⭐⭐ · **Time:** ~40 min
**Prereqs:** Class 6 §15, §17 (debugging habits, troubleshooting)
**Build in:** `work/23-debug-broken-functions/` — one `index.html`, and one file per case (`a.js`, `b.js`, …)

---

## Goal

Each case is broken or behaving unexpectedly. Reproduce it, **fix it**, and write one sentence explaining the cause in your own words. Try before opening the answer.

For each one, start with the Console: is there a red message? If so, read all of it. If not, add a labelled `console.log` and look at the values.

---

## (a) Always logs `undefined`

```js
function double(n) {
    n * 2;
}

console.log(double(5));
```

<details><summary>Show answer</summary>

There's no `return`. The function works out `n * 2` and then throws the answer away, and a function with no `return` gives back `undefined`. Fix: `return n * 2;`.
</details>

---

## (b) Red in the Console: "Assignment to constant variable"

```js
const count = 0;

for (let i = 0; i < 3; i++) {
    count = count + 1;
}

console.log(count);
```

<details><summary>Show answer</summary>

`count` is declared with `const`, but the loop changes it. A value that changes needs `let`: `let count = 0;`. The message names the exact line where the change was attempted.
</details>

---

## (c) The `if` always runs — even when `n` is 5

```js
let n = 5;

if (n = 10) {
    console.log("n is ten");
}
```

<details><summary>Show answer</summary>

One `=` puts a value in; it doesn't compare. `n = 10` sets `n` to 10, and 10 counts as true, so the block always runs. Fix: `if (n === 10)`.
</details>

---

## (d) The tab freezes

**Read this one before you run it.** Work out the fix on paper first. If you do run the broken version, you'll need to close the tab.

```js
let i = 0;

while (i < 5) {
    console.log(i);
}
```

<details><summary>Show answer</summary>

Nothing inside the loop changes `i`, so `i < 5` is true forever: an infinite loop. Add `i++;` inside the loop, after the `console.log`.
</details>

---

## (e) `countVowels("Apple")` returns `1`, not `2`

```js
function countVowels(str) {
    let count = 0;

    for (let i = 0; i < str.length; i++) {
        if (str[i] === "a" || str[i] === "e" || str[i] === "i" || str[i] === "o" || str[i] === "u") {
            count++;
        }
    }

    return count;
}

console.log(countVowels("Apple"));
console.log(countVowels("AEIOU"));
```
…and `countVowels("AEIOU")` returns `0`.

<details><summary>Show answer</summary>

Comparing strings is case-sensitive: `"A"` is not `"a"`. The function only recognises lower-case vowels. Lower-case each character before you compare it: `const c = str[i].toLowerCase();`, and then test `c` in the `if`.
</details>

---

## (f) The last element is missing

```js
const arr = [10, 20, 30, 40];

for (let i = 0; i < arr.length - 1; i++) {
    console.log(arr[i]);
}
```
…it logs `10`, `20`, `30` and stops.

<details><summary>Show answer</summary>

An off-by-one error. The last **index** is `arr.length - 1`, and `i < arr.length - 1` stops before reaching it. The condition should be `i < arr.length`.
</details>

---

## (g) Nothing appears in the Console at all — no output, and no error

```js
function greet(firstName) {
    return `Hello, ${firstName}!`;
}

greet("Ada");
```

<details><summary>Show answer</summary>

The function works, and it *is* called — but nobody does anything with the value it returns. `return` hands the string back to the program; it doesn't show it. Log the call: `console.log(greet("Ada"));`.
</details>

---

## (h) Everyone who passes gets a D

```js
function letterGrade(score) {
    if (score >= 60) {
        return "D";
    } else if (score >= 70) {
        return "C";
    } else if (score >= 80) {
        return "B";
    } else if (score >= 90) {
        return "A";
    } else {
        return "F";
    }
}

console.log(letterGrade(95));
```
…it logs `D`.

<details><summary>Show answer</summary>

A ladder takes the **first** condition that's true and skips the rest. 95 is `>= 60`, so the function returns `"D"` and never looks at the other rungs. Put the strictest test first: `>= 90`, then `>= 80`, then `>= 70`, then `>= 60`.
</details>

---

## Requirements

- [ ] All 8 cases reproduced, fixed, and checked in the Console — except (d), which you may fix on paper before running
- [ ] A one-sentence cause for each, in your own words (not copied)
- [ ] For each case, a note of whether there was a red message, or whether the code ran with no complaint

## Acceptance criteria

- Every fixed case behaves as intended: `double(5)` logs `10`; the count reaches `3`; the `if` is skipped when `n` is 5; the loop logs `0` to `4` and stops; `countVowels("Apple")` is `2` and `countVowels("AEIOU")` is `5`; all four elements are logged; the greeting appears; and `letterGrade(95)` is `A`.
- You noticed that only **one** of the eight produced a red error message. Most bugs don't announce themselves.
