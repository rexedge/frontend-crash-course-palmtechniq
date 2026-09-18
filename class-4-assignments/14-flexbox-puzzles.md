# Assignment 14 — Flexbox Puzzles

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 4 (all of it)
**Build in:** `work/14-flexbox-puzzles/` — one file per puzzle (`1.html`, `2.html`, …)

---

## Goal

Five small layout puzzles, each solvable with what this class taught. Reproduce each arrangement exactly.

## What you'll practice

- Combining `justify-content`, `align-self`, `order`, and `flex-grow` in less obvious ways
- Reading a target layout and working backwards to the properties that produce it

## The puzzles

Unless stated otherwise: the container is a flex **row**, and it holds several equal-size boxes.

**1. Clustered centre, pinned ends**
Most boxes cluster together in the centre with equal gaps between them, but the **first** box sticks to the far left edge and the **last** box sticks to the far right edge.
*(Hint: think about what `margin-right: auto` on the first box, and `margin-left: auto` on the last, would each push against.)*

**2. Wrapping, centred second row**
Six boxes that wrap onto a second row when the container narrows. Both rows should have equal `gap` in every direction, and the (shorter) second row should be centred rather than left-aligned.
*(Hint: `flex-wrap` plus `justify-content: center` handles more of this than you'd expect — try it before reaching for anything else.)*

**3. Three different vertical alignments in one row**
Three boxes in the same row: the first aligned to the top, the middle one vertically centred, the last aligned to the bottom.
*(Hint: one property overrides another, per-item.)*

**4. Visual order without HTML order**
Three boxes, written in the HTML in the order A, B, C — but they must **display** as C, A, B, without reordering the HTML.
*(Hint: one property does this, using negative or larger numbers.)*

**5. A fixed 1:2 split at any width**
Two boxes that always split their container exactly 1/3 and 2/3, no matter how wide the container gets — not just at the default size.
*(Hint: `flex-basis: 0` removes each box's "natural size" from the equation, leaving only the grow ratio.)*

## Requirements

- [ ] All 5 puzzles solved, each in its own file
- [ ] Each solution uses only Flexbox properties from this class — no `position`, no Grid, no fixed pixel widths standing in for the ratio in puzzle 5
- [ ] A one-line comment in each file's CSS naming which property(ies) solved it

## Acceptance criteria

- Resizing the window: puzzle 2's wrap and puzzle 5's ratio both hold up at any width, not just the size you first tested.
- Puzzle 4's HTML source order is unchanged — only the visual order differs.

## Hints

<details><summary>Show hint</summary>

If you're stuck on a puzzle for more than 10 minutes, re-read Class 4 §9–§11 — every puzzle here is a direct variation on a pattern already shown there.
</details>
