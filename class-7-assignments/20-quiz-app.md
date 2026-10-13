# Assignment 20 — Quiz App

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1.5 hr
**Prereqs:** Class 2 (radio buttons, `fieldset`); Class 7 §8, §10–11 (`.checked`, `submit`, `forEach` with an index)
**Build in:** `work/20-quiz-app/index.html` + `style.css` + `app.js`

---

## Goal

Build a five-question multiple-choice quiz. The user picks answers and presses Submit; the page shows a score, marks each question right or wrong, and offers a "Try again" button that resets everything.

## What you'll practice

- Reading which radio button in a group is chosen, with `.checked`
- Comparing the user's answers with an array of correct ones
- Marking elements with classes, and clearing those marks again
- A function that returns a value, used inside a loop

## Instructions

1. Write five questions in the HTML, inside one `<form>`. Each question is a `<fieldset class="question">` with a `<legend>` and three or four radio buttons.
   - The radios in one question share a `name` (`q1`, `q2`, …), as in Class 2.
   - They also share a **class** that your JavaScript can find them by: `q1-option`, `q2-option`, …
   - Each radio has a `value`: `a`, `b`, `c`.
2. Under the questions: a `Submit` button, a `<button type="button">Try again</button>`, and an empty paragraph for the score.
3. In the CSS: a `.right` class (a green border or background) and a `.wrong` class (a red one) for the fieldsets.
4. In `app.js`, keep the answers in an array, in question order:
   ```js
   const correctAnswers = ["b", "a", "c", "b", "a"];
   ```
5. Write `chosenAnswer(questionNumber)`. It finds that question's radios, loops over them, and **returns** the `value` of the one that's checked — or `""` if none is.
6. On `submit`: `preventDefault`, then loop over the fieldsets. For each one, compare the chosen answer with the correct one, add 1 to the score if they match, and mark the fieldset `right` or `wrong`. Then show `You scored 4 / 5`.
7. `Try again`: uncheck every radio, take the marks off every fieldset, and empty the score.

## Requirements

- [ ] Five questions, each a `fieldset` with a `legend` and labelled radio buttons
- [ ] The correct answers are in **one** array — not scattered through `if` statements
- [ ] `chosenAnswer` returns a value and changes nothing on the page
- [ ] An unanswered question counts as wrong; it doesn't cause an error
- [ ] Submitting twice gives the right marks the second time — old marks are cleared first
- [ ] `Try again` puts the page back exactly as it was when it loaded

## Acceptance criteria

- Answer four correctly and one wrongly: the page reads `You scored 4 / 5`, four fieldsets are green, and one is red.
- Submit with nothing chosen: `You scored 0 / 5`, all red, and no red in the Console.
- Change a wrong answer to the right one and submit again: that fieldset turns green, and the score goes up.
- After `Try again`: no radio is selected, nothing is marked, and the score line is empty.
- The page doesn't reload at any point.

## Hints

<details><summary>Show hint</summary>

A template literal builds the selector for whichever question you want:

```js
const options = document.querySelectorAll(`.q${questionNumber}-option`);
```

Inside `chosenAnswer`, start with `let chosen = "";`, loop over the options, and when you find one with `option.checked`, store its `option.value`. Return `chosen` after the loop.

In the submit loop, `forEach((fieldset, i) => …)` gives you an index that starts at 0 — but your questions are numbered from 1. So it's `chosenAnswer(i + 1)` compared with `correctAnswers[i]`.

To uncheck a radio from code: `option.checked = false;`.
</details>

## Stretch (optional)

After the score, add a line of feedback that depends on it: one message for 5 out of 5, another for 3 or 4, another for 2 or fewer. That's an `if` ladder from Class 6, with the score as its input.
