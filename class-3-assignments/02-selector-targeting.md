# Assignment 02 — Selector Targeting

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 3 §5 (selectors)
**Build in:** `work/02-selector-targeting/index.html` + `style.css`

---

## Goal

Write four CSS rules that each hit exactly the right elements — one rule per requirement, no more.

## What you'll practice

- Element, descendant (`A B`), and `#id` selectors
- Targeting *only* what you mean to target
- One responsibility per rule

## Instructions

1. Build `index.html` with: an `<h1>`, two or three `<h2>`, several `<p>`, a `<nav>` containing a `<ul>` of links, and one paragraph marked `<p id="lead">`.
2. In `style.css`, write **exactly four rules**:
   - **(a)** every `<h2>` → a dark blue `color`
   - **(b)** every `<li>` **inside the `<nav>`** → `list-style: none` and a larger `font-size` (must not affect any other list)
   - **(c)** only `#lead` → `font-weight: bold` and a bigger `font-size`
   - **(d)** every `<p>` → `line-height: 1.6`
3. Add a second `<ul>` **outside** the nav to prove rule (b) doesn't touch it.

## Requirements

- [ ] Exactly 4 rules, one per requirement
- [ ] Rule (b) uses a descendant selector (`nav li` or `nav ul li`) and changes nothing outside the nav
- [ ] Rule (c) uses `#lead` and affects only that one paragraph
- [ ] No inline styles

## Acceptance criteria

- The non-nav `<ul>` still shows bullets at normal size.
- `#lead` is the only bold paragraph, but all paragraphs (including `#lead`) have the looser line height.
- Selecting each element in dev tools → Styles shows just the one rule you intended.

## Hints

<details><summary>Show hint</summary>

Descendant selector = two selectors with a **space**: `nav li` means "every `<li>` inside a `<nav>`". `nav, li` (comma) would mean "every `<nav>` and every `<li>` on the page" — very different.
</details>
