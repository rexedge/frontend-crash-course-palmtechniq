# Assignment 05 — input Event

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 7 §9 (more events, the `event` object)
**Build in:** `work/05-input-event/index.html` + `app.js`

---

## Goal

Make a piece of text on the page follow what you type, live, one keystroke at a time.

## What you'll practice

- The `input` event
- Writing a value into the page with `textContent`
- `event.target`

## Instructions

1. Build a page with a labelled text input, and a line underneath: `<p>You are typing: <span id="mirror"></span></p>`.
2. Listen for `input` on the text box. Each time it happens, put the box's value into the span.
3. Type, delete, select everything and type over it. The span should always match the box.
4. Rewrite the function so it takes the `event` parameter and uses `event.target.value` instead of your input variable. It should behave the same.
5. When the box is empty, show `nothing yet` in the span instead of leaving it blank.
6. Type `<h1>Big</h1>` into the box. What appears in the span?

## Requirements

- [ ] The listener is for `input`, not `click` or `change`
- [ ] The span is updated with `textContent`
- [ ] One version uses `event.target.value`
- [ ] An empty box shows `nothing yet`

## Acceptance criteria

- The span changes on every keystroke, with no button to press.
- Emptying the box brings back `nothing yet`.
- Typing `<h1>Big</h1>` shows those exact characters as text. There's no giant heading — that's `textContent` keeping you safe.

## Hints

<details><summary>Show hint</summary>

For the empty case, check the value with an `if` before you write it: if it's `""`, write the fallback text; otherwise write the value. A ternary does it in one line.
</details>

## Stretch (optional)

Swap `input` for `change` and type again. When does the span update now? Write one sentence on the difference, then swap it back.
