# Assignment 13 — Contact Form → Two Columns

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min · 🧵 keep this file
**Prereqs:** Class 3 Assignment 08 (styled contact form) done; Class 4 §9 (flex-basis)
**Build in:** `work/13-contact-form-two-columns/index.html` + `style.css`

---

## Goal

Convert your Class 3 contact form into a two-column layout with Flexbox — this is the **Class 4 homework**.

## What you'll practice

- Wrapping each field in its own container so you can control it individually
- `flex-wrap` so the layout survives a narrow window
- `flex-basis` percentages for "roughly half" vs "full width" fields

## Instructions

1. Copy your Class 3 styled contact form into `work/13-contact-form-two-columns/`. Do **not** change the form's fields, labels, or validation — only how they're arranged.
2. Wrap each label+input pair in its own container if it isn't already, e.g.:
   ```html
   <div class="field field-half">
       <label for="name">Full name</label>
       <input type="text" id="name" name="name" required>
   </div>
   ```
3. In `style.css`:
   - The form's field container: `display: flex`, `flex-wrap: wrap`, `gap`
   - `.field-half` (Name, Email): `flex: 1 1 45%` — roughly half the row each, leaving room for the gap
   - `.field-full` (Subject, Message, and anything else): `flex: 1 1 100%` — always its own full-width row
4. Shrink the browser window narrow. Confirm the half-width fields drop to a single column instead of squeezing unreadably thin.

## Requirements

- [ ] Name and Email sit side by side on one row at normal widths
- [ ] Subject and Message (and any other full-width fields) always take the entire row
- [ ] `flex-wrap: wrap` is set, and fields drop to one column on a narrow window
- [ ] All original labels, `required`, `minlength`, etc. from Class 2/3 are unchanged
- [ ] The submit button still works and the form still validates as before

## Acceptance criteria

- At a normal desktop width: Name and Email are visibly two columns; Subject and Message each span the full form width.
- Narrowed to a small width: every field becomes a single column, still fully readable, nothing overlaps or overflows.
- No HTML structure changed beyond adding the field wrapper `<div>`s.

## Hints

<details><summary>Show hint</summary>

`flex: 1 1 45%` reads as "grow: yes, shrink: yes, starting size: 45% of the row" — two of those plus a `gap` comfortably fit two fields per row without hitting exactly 100%. If they don't wrap when the window narrows, double-check `flex-wrap: wrap` is on the **parent**, not the fields themselves.
</details>
