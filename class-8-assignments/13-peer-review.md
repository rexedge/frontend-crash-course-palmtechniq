# Assignment 13 — Peer Review

**Type:** Review · **Difficulty:** ⭐⭐ · **Time:** ~45 min
**Prereqs:** a finished portfolio ([Assignment 01](01-personal-portfolio.md)); Class 8 §11
**Answer in:** `work/13-peer-review/review.md` (or any text file)

---

## Goal

Review a portfolio the way a colleague would: against a clear list, with a score for each part and one specific suggestion. Do it **twice** — once on your own page, and once on a classmate's. Reviewing someone else's work is one of the fastest ways to get better at your own.

Learning alone? Review your own page today. Then leave it for a day, and review it again as though somebody else had built it.

## What you'll practice

- Judging a page against requirements, not against taste
- Reading somebody else's HTML, CSS, and JavaScript
- Giving feedback that is specific, kind, and useful
- Hearing feedback without defending yourself

## Instructions

1. **Present** (if you're in a class). About ten minutes each:
   - **Show the page.** Phone width first, then wide. Switch the theme. Use the third interaction. Send the form.
   - **Show one piece of code you're proud of**, and explain it line by line.
   - **Show one bug**: what you saw, what you tried, and what the cause turned out to be.
   - **Take questions.**
2. **Review.** Open the page yourself, with dev tools open. Go through the rubric below, one row at a time, and actually check each thing: resize the window, read the Console, look at the code.
3. **Score** each row 0, 1, or 2.
4. **Write the feedback:** two things that work well, and one thing to change. Be specific about all three.
5. **Swap, and listen.** When it's your turn to be reviewed, write the comments down before you answer them.
6. **Act on it.** Fix the weakest row on your own page, then score it again.

## The rubric

Score each row: **0** = missing · **1** = partly there · **2** = solid.

| Area | What to check | How to check it |
|---|---|---|
| Semantics | The landmarks are used correctly; the headings are in order; every form label is linked to its field | Read the HTML. Click each label |
| CSS structure | One external stylesheet; a consistent type and spacing scale; the `box-sizing` reset | Read `style.css`. Count how many different font sizes it uses |
| Layout | Flexbox and Grid are both used, each where it fits | Switch on the flex and grid overlays in dev tools |
| Responsive | Works from 320px to 1440px; no overflow; the nav and the cards both adapt | Drag the window. Try 320px exactly |
| JavaScript | The theme toggle works; the form is handled without a reload; the third interaction works; the Console is clean | Use all three, with the Console open |
| Content | It's clear who this is and what they can do; real words; every image has an `alt` | Read it as a stranger would |
| Code quality | Readable, indented, nothing left over, typed by hand — and the author can explain it | Point at three lines, and ask |

**Total: out of 14.**

- **14** — ready to share.
- **10 to 13** — one more polish pass.
- **Under 10** — find the weakest row, and go back to that class's assignments.

## Requirements

- [ ] Your **own** page scored on all seven rows, honestly
- [ ] One other page scored on all seven rows (or your own again, a day later)
- [ ] For each page: two specific things that work well, and one specific thing to change
- [ ] The feedback you received, written down
- [ ] At least one change made to your own page because of it

## Acceptance criteria

- Every score has a reason next to it. "Responsive: 1 — the header overlaps at 340px" is a review. "Responsive: 1" is not.
- Your one suggestion is something the author could act on today.
- Your own page scores **10 or more** after your fixes.

## Hints

<details><summary>Show hint</summary>

**Useful feedback is specific and about the page:**

- "The cards line up at every width I tried, and the links stay at the bottom of each one."
- "In dark mode, the Skills boxes stay white."
- "I couldn't tell what the third project was from its description."

**Unhelpful feedback is vague, or about the person:**

- "Looks good." (What does? Why?)
- "The colours are ugly." (That's taste. Is the contrast too low? Say that.)
- "You should have used a framework." (Not what the brief asked for.)

When you're the one being reviewed: don't explain, and don't defend. Say "thank you", write it down, and decide later what to do about it.
</details>

## Stretch (optional)

Ask someone who has never written code to use your page on their phone while you watch in silence. Write down every place they hesitated. That list is a second review, and often the more useful one.
