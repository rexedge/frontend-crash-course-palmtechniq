# Assignment 05 — Tiny Table

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 2 §6 (tables)
**Build in:** `work/05-tiny-table/index.html`

---

## Goal

Build one small, correctly-structured data table using `caption`, `thead`, `tbody`, and `scope`.

## What you'll practice

- `<th>` for header cells vs `<td>` for data cells
- Grouping with `<thead>` and `<tbody>`
- `scope="col"` for column headers, `scope="row"` for row headers
- Using a table for **real tabular data**, never for layout

## Instructions

1. Build a table of **your own** weekday routine.
2. Columns: `Time`, `Activity`, `Location`. Give it a `<caption>` like "My Weekday Routine".
3. Header row goes in `<thead>` using `<th scope="col">`.
4. At least **4** data rows in `<tbody>`. Make the first cell of each row a `<th scope="row">` holding the time, and the other two cells `<td>`.
5. Above the table add an `<h1>`; below it add a `<p>` answering: *when is a table the wrong tool?*

## Requirements

- [ ] `<caption>` is the first child of `<table>`
- [ ] Column headers use `<th scope="col">` inside `<thead>`
- [ ] Each row's first cell uses `<th scope="row">`
- [ ] Data cells use `<td>`
- [ ] 4+ rows in `<tbody>`
- [ ] A written sentence on a wrong use of tables

## Acceptance criteria

- The dev tools "Elements" tree shows `table > caption`, `table > thead > tr > th×3`, `table > tbody > tr > (th + td + td)`.
- No `<div>` or CSS involved.

## Hints

<details><summary>Show hint</summary>

`&amp;` writes a literal `&`. So "Rest &amp; lunch" renders as "Rest & lunch".
</details>

## Stretch (optional)

Add a `<tfoot>` with one row that summarises something (e.g. total hours). It goes after `<tbody>` in the source but browsers render it at the bottom.
