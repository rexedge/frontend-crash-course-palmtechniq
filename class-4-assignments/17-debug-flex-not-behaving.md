# Assignment 17 — Debug: Flex Not Behaving

**Type:** Debug · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 4 §13 (troubleshooting)
**Build in:** `work/17-debug-flex/` — one folder per case (`a/`, `b/`, …)

---

## Goal

Each case is broken or behaving unexpectedly. Reproduce it, **fix it**, and write one sentence explaining the cause in your own words. Try before opening the answer.

---

## (a) `justify-content` does nothing

```css
.row { display: flex; }
.row .item { justify-content: center; }
```

<details><summary>Show answer</summary>

`justify-content` belongs on the flex **container** (`.row`), not on an item. Move it up.
</details>

---

## (b) Items are stacked in a column, not a row

```css
.row { display: flex; flex-direction: column; }
```

<details><summary>Show answer</summary>

Either someone set `flex-direction: column` deliberately elsewhere, or it's being inherited from a broader rule. Set it to `row` explicitly (or remove the `column` rule) if a row is what you want.
</details>

---

## (c) `align-items: center` isn't vertically centring anything

```css
.row { display: flex; align-items: center; }
```
…and `.row` has no explicit height — it's exactly as tall as its tallest child.

<details><summary>Show answer</summary>

There's no extra room to centre *within*. Give `.row` a `height` or `min-height` taller than its children, and `align-items: center` will visibly centre them inside that space.
</details>

---

## (d) The "push to the right" trick isn't working

```css
.bar { display: flex; }
.bar .spacer { margin-left: auto; }
```
…but `.spacer` is `display: none`, or doesn't exist in the HTML at all.

<details><summary>Show answer</summary>

`margin-left: auto` must sit on a real, **visible** flex item — usually the element you actually want pushed to the right (e.g. the last real button), not a separate hidden spacer.
</details>

---

## (e) A flex child overflows instead of shrinking

```css
.row { display: flex; }
.row img { width: 400px; }
```

<details><summary>Show answer</summary>

Flex items won't shrink below their content's natural/`min-width` by default, even with `flex-shrink: 1` (the default). Add `min-width: 0` to the item (and/or `max-width: 100%` on the image) to allow it to shrink.
</details>

---

## (f) Cards in a row are wildly different heights

```css
.row { display: flex; align-items: flex-start; }
```
…the developer expected equal-height cards.

<details><summary>Show answer</summary>

`align-items: flex-start` opts **out** of the default equal-height behaviour. Remove it (or set `align-items: stretch`, which is the default) to let the cards match the tallest one.
</details>

---

## Requirements

- [ ] All 6 cases reproduced, fixed, and verified in the browser
- [ ] A one-sentence cause for each, in your own words (not copied)

## Acceptance criteria

- Every fixed case behaves as intended: `justify-content` spaces the row, the row lays out in the requested direction, centring is visible, the push-right trick works on a real element, the image shrinks instead of overflowing, and the cards match height.
