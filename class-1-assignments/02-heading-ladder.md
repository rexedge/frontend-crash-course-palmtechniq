# Assignment 02 — Heading Ladder

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~5 min
**Prereqs:** Class 1 §4 (Headings)
**Build in:** `work/02-heading-ladder/index.html`

---

## Goal

Use every heading level, `<h1>` through `<h6>`, once each, in order, and see how the browser sizes them.

## What you'll practice

- The six heading levels and their order
- That headings carry *importance/rank*, not just size
- Not skipping levels (never jump `<h1>` straight to `<h4>`)

## Instructions

1. Build a valid page skeleton.
2. Inside `<body>`, add `<h1>` then `<h2>` then `<h3>` ... down to `<h6>` — in that order, one of each.
3. Make each heading's text say what it is, e.g. `This is heading level 3`.
4. Save and open in the browser. Confirm each one is visually smaller than the one before.

## Requirements

- [ ] All six levels present, `h1`–`h6`, each used exactly once
- [ ] They appear in order in the HTML (no skipping, no going back up)
- [ ] Each heading's text names its level
- [ ] Valid skeleton, content inside `<body>`

## Acceptance criteria

- In the browser, the headings step down in size from `h1` (biggest) to `h6` (smallest).
- Reading the HTML top to bottom, the numbers go 1, 2, 3, 4, 5, 6 with no gaps.

## Hints

<details><summary>Show hint</summary>

`<h6>` may render *smaller* than normal paragraph text — that's expected. Heading level is about structure and rank, not "make text big".
</details>

## Stretch (optional)

Below the ladder, add a second `<h1>` and three `<h2>`s that form a tiny fake article outline ("My Trip", then "Getting There", "The Hotel", "Coming Home"). This is how headings are actually used — to outline a document.
