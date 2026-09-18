# Class 4: CSS Layout — Flexbox
### A self-guided read-through — read each section, then do the practice before moving on. Have your styled "About Me" page and contact form from Class 3 nearby.

---

## 1. Recap: Where We Are

By now you can make a page **look** good: fonts, colours, spacing, a centred content column. But every element still sits exactly where the browser's default stacking puts it — blocks stacked vertically, inline things flowing left to right, and `margin: 0 auto` as your only real layout trick.

Real layout needs things like:
- a navbar with the logo on one side and links on the other
- three cards in a row, all the same height, evenly spaced
- a sidebar next to a main content area
- something perfectly centred, both horizontally *and* vertically

None of that is comfortable with what you know so far. That's what **Flexbox** is for.

---

## 2. Why Layout Used to Be Hard

Before Flexbox existed, developers laid things out side by side using `float` (a property meant for wrapping text around images) or `display: table` — both were workarounds, not real layout tools. Floats don't clear themselves properly, there's no built-in way to vertically centre anything, and making a row of equal-height columns took genuine hacks.

Flexbox (widely supported since the mid-2010s) was purpose-built to answer one question: **"how do I arrange a row or column of things and control how the space is shared and aligned?"** That's most of what layout actually is. Grid (Class 5) handles the other half — two-dimensional layouts. You'll use both for the rest of this course.

---

## 3. Turning It On

One declaration changes everything:

```css
.row {
    display: flex;
}
```

The moment a container is `display: flex`, its **direct children** become **flex items** and line up in a row automatically — no floats, no hacks.

```html
<section class="row">
    <p>One</p>
    <p>Two</p>
    <p>Three</p>
</section>
```

```css
.row {
    display: flex;
    gap: 16px;
}
```

Those three paragraphs, which used to stack one per line, now sit side by side with a 16px gap between them.

### Practice Now
Build a `<section>` with three child `<p>`s. Add `display: flex` and watch them line up horizontally. Add `gap: 16px`. Do the whole thing from memory three times.

✅ **Checkpoint:** One line of CSS turned a vertical stack into a horizontal row. That's the whole trick — everything else in this class is about *controlling* that row (or column).

---

## 4. The Two Axes — the Most Important Concept

Flexbox thinks in terms of two axes, and almost every property in this class belongs to one or the other. Get this right and the rest falls into place.

```
flex-direction: row   (the default)

   ── main axis ──────────────────►
  ┌───────────────────────────────┐
  │ [ item ]  [ item ]  [ item ]  │  │ cross axis
  └───────────────────────────────┘  ▼

flex-direction: column

  ┌─────────┐  ▲
  │ [ item ]│  │
  │ [ item ]│  │ main axis
  │ [ item ]│  │
  └─────────┘  ▼
  ── cross axis ──►
```

- **`flex-direction: row`** (default) — the **main axis is horizontal**, the **cross axis is vertical**.
- **`flex-direction: column`** — flips it: the **main axis is vertical**, the **cross axis is horizontal**.

The two big alignment properties each control **one axis**:

| Property | Controls | 
|---|---|
| `justify-content` | spacing/position along the **main axis** |
| `align-items` | spacing/position along the **cross axis** |

This is the single most common source of Flexbox confusion: which property does what **depends on `flex-direction`**. In a row, `justify-content` moves things left/right and `align-items` moves things up/down. In a column, it's reversed.

### Practice Now
Take your row of three boxes. Toggle `flex-direction` between `row` and `column`. With `column` set, ask yourself: which property would now move the boxes *up and down* — `justify-content` or `align-items`? Test your answer.

---

## 5. `justify-content` — Spacing Along the Main Axis

```css
.row {
    display: flex;
    justify-content: space-between;
}
```

| Value | What it does |
|---|---|
| `flex-start` | items packed at the start (default) |
| `flex-end` | items packed at the end |
| `center` | items packed in the middle |
| `space-between` | equal gaps **between** items; none at the outer edges |
| `space-around` | equal gaps around each item (edges get half a gap) |
| `space-evenly` | perfectly equal gaps everywhere, including the edges |

### Practice Now
Five copies of a flex row with 3 boxes. Give each copy a different `justify-content` value from the table above. Label each one. This is worth doing by eye — the differences between `space-between`, `space-around`, and `space-evenly` are easy to mix up until you've seen them side by side.

---

## 6. `align-items` — Alignment Along the Cross Axis

```css
.row {
    display: flex;
    align-items: center;
}
```

| Value | What it does |
|---|---|
| `stretch` | items stretch to fill the cross axis (default!) |
| `flex-start` | items align to the start of the cross axis |
| `center` | items centred on the cross axis |
| `flex-end` | items align to the end of the cross axis |
| `baseline` | items align by their text baselines |

> **The default is `stretch`, not `flex-start`.** This is why flex children often end up "full height" even though you never asked for that — if you don't want it, set `align-items` to something else, or give the item its own `height`.

### `align-self` — override one item

```css
.row { display: flex; align-items: center; }
.row .highlight { align-self: flex-start; }
```

`align-self` on a single child overrides the container's `align-items` for just that one item.

### Practice Now
A flex row, container `height: 200px`, three boxes of *different* heights (use different amounts of text, or set explicit heights). Cycle `align-items` through all five values. Note which one makes all three boxes the same height, and why (hint: it's the default).

---

## 7. `flex-wrap` — Letting Items Move to a New Line

By default, flex items try to **all fit on one line**, shrinking if they must. `flex-wrap: wrap` lets them flow onto additional rows instead:

```css
.row {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
}
```

Without `flex-wrap`, a row of items wider than their container will squeeze or overflow. With it, extras drop to the next line, like text wrapping.

---

## 8. `gap` — Space Between Items, the Easy Way

```css
.row {
    display: flex;
    gap: 16px;      /* both directions */
    /* or separately: */
    row-gap: 16px;
    column-gap: 24px;
}
```

`gap` puts space **between** flex items only — never before the first or after the last. That's what makes it nicer than giving every child a `margin-right`: no "remove the margin on the last child" cleanup needed. Always reach for `gap` before margin when spacing out flex children.

### Practice Now
Lay out 4 cards in a row with even spacing using `gap`. Then redo it using `margin-right` on each card instead, and notice the extra margin hanging off the last card that you have to manually remove. Keep `gap`.

---

## 9. Sizing Flex Items: `flex-grow`, `flex-shrink`, `flex-basis`

These three control how an item's size behaves *within* the row — separate from `justify-content`, which only controls spacing.

| Property | Meaning |
|---|---|
| `flex-basis` | the item's starting size along the main axis, before growing/shrinking (like `width` for a row) |
| `flex-grow` | a **ratio** of leftover space this item should take. `0` (default) = don't grow. |
| `flex-shrink` | how much this item shrinks if there isn't enough room. `1` (default) = shrink normally. |

Almost always written as the **`flex` shorthand**: `flex: grow shrink basis;`

```css
.sidebar { flex: 0 0 240px; }   /* never grow, never shrink, always 240px */
.main    { flex: 1; }            /* grow to fill all remaining space (shorthand for 1 1 0%) */
```

`flex: 1` is the single most-used Flexbox declaration in real projects: "take up whatever space is left."

```css
.thirds .a { flex: 1; }   /* splits leftover space evenly... */
.thirds .b { flex: 2; }   /* ...unless the ratios differ: this one gets twice as much */
```

### Practice Now
Two boxes side by side, container width 600px. Give one `flex: 1` and the other `flex: 2`. Resize the window and confirm they always split the space 1:2, whatever the width.

---

## 10. `order` — Reordering Without Touching the HTML

```css
.item-that-should-come-first {
    order: -1;
}
```

Every flex item defaults to `order: 0`. Lower numbers come first, higher numbers come later — visually only. The HTML source order doesn't change (which matters for screen readers and keyboard navigation — use `order` sparingly, for visual tweaks, not to fix bad HTML order).

---

## 11. Everyday Flexbox Patterns

A handful of combinations you will use constantly. Memorise these shapes.

**Perfect centring — both directions, in three declarations:**
```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

**Push one item to the far end of a row:**
```css
.toolbar { display: flex; }
.toolbar .delete-button { margin-left: auto; }
```
`margin-left: auto` on a flex item consumes all the leftover space on its left, shoving it (and everything after it) to the right edge.

**A card whose "action" link always sits at the bottom, however much text is above it:**
```css
.card {
    display: flex;
    flex-direction: column;
    height: 100%;
}
.card .cta {
    margin-top: auto;   /* pushes this element to the bottom of the column */
}
```

**A fixed sidebar plus a flexible main area:**
```css
.layout { display: flex; min-height: 100vh; }
.sidebar { flex: 0 0 240px; }
.main    { flex: 1; }
```

### Practice Now
Build the "card with a pinned bottom link" pattern with three cards of different text lengths, side by side in a row (`gap` between them, all `flex: 1` so they're equal width). Confirm the "Learn more" link lines up at the same height on all three, regardless of how much text is above it.

---

## 12. Guided Practice: Build a Navbar and a 3-Card Layout

This is the main build for Class 4 — two classic layouts, both with Flexbox.

### Part A — Navbar

Requirements:
- [ ] `<header>` (or `<nav>`) is `display: flex`
- [ ] Brand/logo text on the left, a list of 4 nav links on the right — use `justify-content: space-between`
- [ ] The links themselves sit in their own flex row with `gap` between them
- [ ] Everything vertically centred with `align-items: center`
- [ ] The bar has `padding` and a `background-color`

```html
<header class="navbar">
    <p class="brand">My Site</p>
    <nav class="nav-links">
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Work</a>
        <a href="#">Contact</a>
    </nav>
</header>
```

```css
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 24px;
    background-color: #1a1a1a;
}
.nav-links {
    display: flex;
    gap: 20px;
}
```

### Part B — Three-Card Feature Row

Requirements:
- [ ] A container `display: flex` with `gap` between three cards
- [ ] All three cards `flex: 1` (equal width) and the same height, however much text each has
- [ ] Each card is itself `display: flex; flex-direction: column`
- [ ] Each card contains an icon/emoji, an `<h3>`, a `<p>`, and a link — with the link pinned to the bottom via `margin-top: auto`

```html
<section class="cards">
    <article class="card">
        <p class="icon">🚀</p>
        <h3>Fast</h3>
        <p>Built for speed from the ground up, with no wasted steps.</p>
        <a href="#" class="cta">Learn more</a>
    </article>
    <!-- two more .card articles -->
</section>
```

```css
.cards { display: flex; gap: 24px; }
.card {
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 24px;
    border: 1px solid #e0e0e0;
}
.card .cta { margin-top: auto; }
```

### Acceptance criteria
- The navbar keeps the brand pinned left and links pinned right at any (reasonable) window width.
- All three cards are the same height and the same width, and every "Learn more" link sits at the same vertical position.
- No `float`, no `position`, no Grid used anywhere.

✅ **Checkpoint:** Two of the most common real-world layouts, done with about a dozen lines of CSS. Compare that to how painful both used to be with floats.

---

## 13. Troubleshooting

| Problem | Likely cause |
|---|---|
| `justify-content` does nothing | It's on the wrong element — it belongs on the flex **container**, not on a child/item. |
| Items are still stacked vertically, one per line | `display: flex` is missing, or `flex-direction: column` is set (on purpose or inherited) when you wanted `row`. |
| `align-items: center` doesn't seem to centre anything | The container has no `height`/`min-height` taller than its content — there's no room to centre *within*. Give it one. |
| `margin-left: auto` "push to the end" isn't working | It needs to be on a real, visible flex **item** — not a hidden spacer, and the parent must actually be `display: flex`. |
| A flex child (often an image) overflows its box instead of shrinking | Flex items won't shrink below their content size by default. Add `min-width: 0` (and/or `max-width: 100%`) to the item. |
| Items don't wrap onto a new line when they should | `flex-wrap: wrap` is missing — the default is `nowrap`, so items squeeze or overflow instead. |
| Everything is "full height" and you didn't ask for it | `align-items` defaults to `stretch`. Set it to `flex-start` (or give items their own height) if you don't want that. |
| `flex: 1` isn't filling the space you expected | Check every sibling's `flex` value too — `flex-grow` is a **ratio** between all the flexible siblings, not an absolute size. |

---

## 14. Self-Check: Can You Answer These?

Try without scrolling back.

1. What single declaration turns a container's children into a flex row?
2. What is the "main axis"? What is the "cross axis"? How does `flex-direction` decide which is which?
3. `justify-content` vs `align-items` — which axis does each control?
4. What does `align-items` default to, and why does that surprise people?
5. What's the difference between `flex-grow`, `flex-shrink`, and `flex-basis`?
6. What does `flex: 1` actually mean, expanded out?
7. Why is `gap` usually better than `margin` for spacing out flex children?
8. How would you push one button to the far right of an otherwise left-aligned toolbar?

---

## 15. Homework

1. **Convert your Class 3 contact form into a two-column layout using Flexbox** (the course homework). Requirements:
   - Wrap each field (label + input) in its own small container.
   - Lay the field containers out with `display: flex; flex-wrap: wrap; gap: ...` on their parent.
   - Name and Email share a row (each roughly `flex: 1 1 45%` so they sit side by side).
   - Subject and Message each span the full width (`flex: 1 1 100%`).
   - The layout should still look reasonable when the browser window is narrow — fields should wrap down to one column rather than squeezing unreadably thin.

2. *(Optional)* Redo your Class 3 business card or pricing layout using the "card with pinned bottom" pattern from Section 11, if you haven't already.

For a lot more practice on this class — axis drills, layout puzzles, and debugging exercises with answers — see the **Class 4** section of [`assignments.md`](assignments.md).

---

## What's Next

Class 5 is **CSS Grid & Responsive Design** — Flexbox's two-dimensional sibling, plus making pages adapt to different screen sizes with media queries. Bring your navbar, your card row, and your two-column contact form.
