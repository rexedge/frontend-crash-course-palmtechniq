# Assignment 12 — Calendar Month

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min
**Prereqs:** Class 5 §3–4, §11, §13–14 (`repeat()`, placing items, `aspect-ratio`, media queries)
**Build in:** `work/12-calendar-month/index.html` + `style.css`

---

## Goal

Build one month of a wall calendar — 7 columns, weekday names across the top, numbered day squares below — that still fits on a phone.

## What you'll practice

- `repeat(7, 1fr)` — a column count fixed by meaning (7 days), not by screen size
- Starting the first day in the right column with `grid-column`
- `aspect-ratio: 1 / 1` for square cells
- A media query that changes the *details* (text size, padding) instead of the column count

## Instructions

1. Pick a real month and find which weekday the 1st falls on.
2. Build `index.html`:
   - an `<h1>` with the month and year
   - a `<ul class="weekdays">` with 7 `<li>`s: Mon, Tue, Wed, Thu, Fri, Sat, Sun
   - an `<ol class="days">` with one `<li>` per day, 1 to 28, 30, or 31
3. Give both lists `list-style: none`, `padding: 0`, and `margin: 0`. Then give both `display: grid; grid-template-columns: repeat(7, 1fr); gap: 4px;` — the same template, so their columns line up exactly.
4. Put day 1 under the right weekday: give the first `<li>` a class and `grid-column: 3` (for a month starting on Wednesday — use the column that matches your month). Every other day flows on from there.
5. Day cells: `aspect-ratio: 1 / 1`, a `border`, and a little `padding`.
6. Mobile-first: in the base styles, use a small `font-size` and small `padding` for the cells and weekday names. Add `@media (min-width: 500px)` with bigger text and padding. Keep 7 columns at every width.
7. Give the calendar a `max-width` (e.g. `50rem`) and centre it, so it doesn't stretch across a huge screen.

## Requirements

- [ ] The weekday row and the day grid both use `repeat(7, 1fr)`, so their columns line up
- [ ] Day 1 sits under the correct weekday using `grid-column` — no empty placeholder elements
- [ ] Every day cell is square (`aspect-ratio: 1 / 1`)
- [ ] 7 columns at every width; the media query changes only text size and padding
- [ ] Lists used for both the weekdays and the days

## Acceptance criteria

- Check it against a real calendar: every date is under the right weekday.
- At 375px: still 7 columns, numbers readable, no horizontal scrollbar.
- At 1280px: big square cells, and the calendar doesn't stretch across the whole screen.

## Hints

<details><summary>Show hint</summary>

You only have to place **one** item. `grid-column: 3` on day 1 puts it in the third column; days 2, 3, 4… follow automatically and wrap onto new rows.
</details>

## Stretch (optional)

Highlight the weekends and today's date with extra classes. Then think back to Class 2: a calendar is also a classic use of a `<table>`. Write one sentence on which you'd choose for a real site, and why.
