# Assignment 20 — Console Mini-Games

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1 hr
**Prereqs:** Class 6 §10–12, §14 (`if`, loops, arrays, `Math.random`)
**Build in:** `work/20-console-mini-games/index.html` + `app.js` — all three games in the one file, under a comment heading each

---

## Goal

Build the logic for three small games. There are no buttons and nothing to click yet: you "play" by calling a function and reading what it returns.

## What you'll practice

- `Math.random` and the random-whole-number recipe
- Keeping the random part separate from the logic, so the logic can be tested
- A `while` loop that runs until something is found
- Running an experiment thousands of times with a loop

## The games

**1. Rock, paper, scissors**

- `randomMove()` — returns `"rock"`, `"paper"`, or `"scissors"`, picked at random from an array.
- `roundResult(playerMove, computerMove)` — returns `"win"`, `"lose"`, or `"draw"` from the player's point of view. There's no randomness in here, so you can test it properly.
- `rockPaperScissors(playerMove)` — calls the other two, and returns the result.

**2. Guess the number**

- `guessOutcome(secret, guess)` — returns `"too high"`, `"too low"`, or `"correct"`.
- `countGuesses(secret)` — a loop that **plays the game for you**, for a secret number from 1 to 100. It keeps a `low` and a `high`, always guesses the middle (`Math.floor((low + high) / 2)`), calls `guessOutcome`, and moves `low` or `high` to shrink the range. It returns how many guesses it needed.

**3. Dice**

- `rollDice(times)` — rolls **two** dice, `times` times, and returns how many of the rolls added up to 7.

## Requirements

- [ ] `roundResult` is tested with all three outcomes, using moves you chose yourself
- [ ] `rockPaperScissors` contains no rules of its own — it only calls `randomMove` and `roundResult`
- [ ] `countGuesses` uses a `while` loop, and calls `guessOutcome`
- [ ] `rollDice` rolls two separate dice per turn — not one random number from 2 to 12
- [ ] Every function returns its answer; the logging is all outside

## Acceptance criteria

- `roundResult("rock", "scissors")` → `win`. `roundResult("rock", "paper")` → `lose`. `roundResult("rock", "rock")` → `draw`.
- Logging `rockPaperScissors("rock")` ten times gives a mix of all three results.
- `countGuesses(50)` → `1`. `countGuesses(1)` → `6`. `countGuesses(100)` → `7`. No secret from 1 to 100 ever needs more than 7.
- `rollDice(6000)` gives a number close to 1000, and a slightly different one each time you reload.

## Hints

<details><summary>Show hint</summary>

- **`randomMove`** — put the three moves in an array, and use the index `Math.floor(Math.random() * moves.length)`.
- **`roundResult`** — check for a draw first (`playerMove === computerMove`). Then list the three ways the player wins, joined with `||`. Anything else is a loss.
- **`countGuesses`** — if the guess was too high, the secret must be below it: `high = guess - 1`. If it was too low: `low = guess + 1`. Keep looping `while` the outcome is not `"correct"`, and count the rounds.
- **`rollDice`** — why not one random number from 2 to 12? Because the totals aren't equally likely. There are six ways to make 7 with two dice, and only one way to make 12.
</details>

## Stretch (optional)

Play 3000 rounds of `rockPaperScissors("rock")` in a loop, and count the wins, losses, and draws. Each should come out near 1000. What does that tell you about always choosing rock?
