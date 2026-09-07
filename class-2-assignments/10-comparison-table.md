# Assignment 10 — Price / Spec Comparison Table

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 2 §6 (tables)
**Build in:** `work/10-comparison-table/index.html`

---

## Goal

Build a comparison table with headers on **both** axes — column headers for the items being compared and row headers for the attributes.

## What you'll practice

- `scope="col"` **and** `scope="row"` in the same table
- `<caption>`, `<thead>`, `<tbody>`
- Judging when a table is the right tool

## Instructions

1. Choose 3 things to compare (3 phones, 3 laptops, 3 streaming plans, 3 bikes — anything with clear attributes).
2. Build a table where:
   - the top row has an empty first cell, then `<th scope="col">` for each of the 3 items
   - each following row starts with `<th scope="row">` naming an attribute, then 3 `<td>` with each item's value
   - use **5 attribute rows** (e.g. Price, Weight, Battery, Storage, Warranty)
3. Add a `<caption>`.
4. Above the table: an `<h1>` and an intro `<p>`.
5. Below the table: a `<p>` explaining, in your own words, **when a table is the right choice and one situation where a table would be the wrong choice**.

## Requirements

- [ ] One `<table>` with `<caption>`, `<thead>`, `<tbody>`
- [ ] 3 column headers with `scope="col"`
- [ ] 5 row headers with `scope="row"`
- [ ] 15 `<td>` data cells (3 × 5)
- [ ] Written note on correct vs incorrect table use
- [ ] No CSS, no `<div>`

## Acceptance criteria

- Every cell that labels something is a `<th>` with the correct `scope`; every cell that holds a value is a `<td>`.
- The table would still make sense read aloud row by row by a screen reader.

## Hints

<details><summary>Show hint</summary>

The top-left cell (where the column of attribute names meets the row of item names) is usually left as an empty `<td>` — it doesn't label anything.
</details>
