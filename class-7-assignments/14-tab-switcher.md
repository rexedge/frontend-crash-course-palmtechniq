# Assignment 14 — Tab Switcher

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~35 min
**Prereqs:** Class 7 §11 ("clear them all, then mark the one"; partners by index)
**Build in:** `work/14-tab-switcher/index.html` + `style.css` + `app.js`

---

## Goal

Build a set of tabs: three buttons and three panels of content, where only one panel shows at a time and the chosen tab looks "active".

## What you'll practice

- Two lists that line up by index: tabs and panels
- "Clear them all, then mark the one" — on two lists at once
- Starting the page in a sensible state, straight from the HTML

## Instructions

1. Build the page:
   - a row of three `<button type="button" class="tab">`s (lay the row out with Flexbox)
   - three `<div class="panel">`s underneath, each with a heading and a paragraph
2. Set the starting state **in the HTML**: the first tab has the class `active` as well, and the second and third panels have the class `hidden` as well.
3. In the CSS: style `.tab`. Then, **below** that rule, write an `.active` rule that looks clearly different (a different background, or a thick bottom border). Put `.hidden` last.
4. In `app.js`, loop over the tabs with `forEach((tab, i) => { ... })`. On click:
   - remove `active` from **every** tab
   - add `hidden` to **every** panel
   - add `active` to the clicked tab
   - remove `hidden` from `panels[i]`
5. Click every tab, in every order.

## Requirements

- [ ] Exactly one panel is visible at all times, including when the page first loads
- [ ] Exactly one tab has `active` at all times
- [ ] The tab row is laid out with Flexbox
- [ ] One `forEach` adds all the listeners
- [ ] Adding a fourth tab and panel to the HTML needs no change to `app.js`

## Acceptance criteria

- Clicking tab 3 shows panel 3 only, and tab 3 is the only one that looks active.
- Clicking the tab that's already active changes nothing — its panel stays open.
- In the Elements panel, you can watch `active` and `hidden` move around as you click.

## Hints

<details><summary>Show hint</summary>

If the active tab doesn't look any different, check the order of your CSS. `.tab` and `.active` are equally strong, so the one that comes **later** in the file wins (Class 3). `.active` has to be below `.tab`.

If two panels show at once, you're un-hiding the new one without hiding the others first. Hide them all, every time, then show one.
</details>

## Stretch (optional)

Put the "show tab number `n`" steps into a named function, `showTab(n)`, and call it from the click listeners. Then call `showTab(0)` once at the bottom of the file — and take the starting classes out of the HTML.
