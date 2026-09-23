# Assignment 07 — The Viewport Meta Tag

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 5 §8–9 (testing widths, the viewport tag)
**Build in:** `work/07-the-viewport-meta-tag/index.html` + `style.css`

---

## Goal

See with your own eyes what a phone does to a page that has no viewport tag — so you never forget it again.

## What you'll practice

- Using the dev-tools device toolbar with a phone preset
- What `width=device-width, initial-scale=1` actually changes

## Instructions

1. Copy one of your Class 4 pages into `work/07-the-viewport-meta-tag/` — the three-card row is ideal. Check its `<head>`: it almost certainly has **no** viewport tag. Leave it that way for now.
2. Add this test rule to the bottom of its stylesheet. It turns the page yellow whenever the browser thinks the screen is phone-sized:
   ```css
   @media (max-width: 600px) {
       body {
           background-color: lightyellow;
       }
   }
   ```
3. Open dev tools, press `Ctrl+Shift+M` (Mac: `Cmd+Shift+M`), and pick a **phone** from the device list (any iPhone or Pixel). Look at the page. How big is the text? Is the background yellow?
4. Add `<meta name="viewport" content="width=device-width, initial-scale=1">` to the `<head>`. Save and look again.
5. At the bottom of the page, write two sentences in a `<p>`: what you saw before, and what you saw after.

## Requirements

- [ ] Before and after compared on a **phone** preset in the device toolbar
- [ ] The yellow test rule used to show whether the "phone" media query switched on
- [ ] Two sentences describing the difference

## Acceptance criteria

- Before: the page looks like a shrunken desktop page with tiny text, and the background is **not** yellow — the browser was pretending to be about 980px wide.
- After: the page lays out at the phone's real width, and the background **is** yellow.
- You can type the viewport tag from memory.

## Hints

<details><summary>Show hint</summary>

If nothing changes between before and after, check that you picked a **phone** from the device list (not a desktop size), and that you saved and reloaded after adding the tag.
</details>
