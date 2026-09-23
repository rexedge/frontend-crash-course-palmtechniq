# Class 5: CSS Grid & Responsive Design
### A self-guided read-through — read each section, then do the practice before moving on. Have your Class 4 navbar, three-card row, and two-column contact form nearby.

---

## 1. Recap: Where We Are

With Flexbox you can put things in a row or a column and control how the space is shared: navbars, card rows, sidebars, perfect centring.

Two gaps are left:

- **Two-dimensional layouts.** A photo gallery where the pictures line up in neat columns *and* neat rows. A page with a header across the top, a sidebar and content side by side, and a footer across the bottom. Flexbox can fake these — remember the `calc()` maths in Class 4's "card grid without Grid"? — but you're fighting the tool.
- **Small screens.** Everything you've built so far was checked at desktop width. Open it on a phone and the three-card row squashes into three skinny columns, or pushes off the side of the screen.

This class fixes both. The first half is **CSS Grid**: layout in rows *and* columns at once. The second half is **responsive design**: one page that works at every screen width, from a phone to a wide monitor.

---

## 2. Turning On Grid

Like Flexbox, Grid is switched on with one declaration on the **container**:

```html
<section class="grid">
    <p>1</p>
    <p>2</p>
    <p>3</p>
    <p>4</p>
    <p>5</p>
    <p>6</p>
</section>
```

```css
.grid {
    display: grid;
    grid-template-columns: 200px 200px 200px;
    gap: 16px;
}
```

The **direct children** become **grid items**. `grid-template-columns` says "make three columns, each 200px wide". The six paragraphs drop into the cells in order — left to right, then onto the next row — so you get a grid of 3 columns and 2 rows.

Notice what you *didn't* have to do:
- You didn't say how many rows. Grid makes new rows as items need them.
- You didn't wrap anything. Item 4 moved to row 2 because row 1 was full.
- You didn't size the items. The **container** decides the columns; the items just fill the cells.

That last point is the big difference from Flexbox. In Flexbox, the items' content decides their size and the container shares out the space. In Grid, the container draws the lines first and the items move in.

`gap` works exactly as it did in Flexbox: space *between* cells, never around the outside. `row-gap` and `column-gap` set the two directions separately.

### Practice Now
Build the example above. Give the `<p>`s a `background-color`, some `padding`, and `margin: 0` so you can see each cell. Then change the columns to `100px 300px 100px` and watch every row follow the same column sizes. Add a seventh `<p>` and see where it lands.

✅ **Checkpoint:** Six items became a neat grid, and you only styled the container. Every row lines up with the one above it. That's the "two-dimensional" part.

---

## 3. Sizing Tracks: `fr`, `repeat()`, and Rows

A **track** is one column or one row. You size tracks with `grid-template-columns` (and `grid-template-rows`), and you can mix units freely.

### The `fr` unit
`fr` means "a **fraction** of the free space". The browser first takes out any fixed sizes and the gaps. Then it shares out what's left according to the `fr` numbers.

```css
grid-template-columns: 1fr 1fr 1fr;    /* three equal columns that fill the width */
grid-template-columns: 1fr 2fr 1fr;    /* the middle one gets twice as much as each side */
grid-template-columns: 200px 1fr;      /* a fixed 200px column, then all the rest */
grid-template-columns: auto 1fr auto;  /* outer columns hug their content, the middle takes the rest */
```

`auto` means "as wide as the content needs".

`200px 1fr` is Class 4's sidebar layout (`flex: 0 0 240px` plus `flex: 1`) in one line — and it's written on the container, not on each child.

### Why `fr` beats percentages
Try `grid-template-columns: 33% 33% 33%` with `gap: 16px`. The columns add up to 99% of the container — *plus* two 16px gaps on top. That's wider than the container, so you get a horizontal scrollbar. `1fr 1fr 1fr` shares out the space **after** the gaps are taken out, so it always fits. Reach for `fr` first.

### `repeat()` — for when you're typing the same thing over and over
```css
grid-template-columns: repeat(3, 1fr);        /* same as 1fr 1fr 1fr */
grid-template-columns: repeat(12, 1fr);       /* twelve equal columns */
grid-template-columns: 200px repeat(2, 1fr);  /* you can mix: 200px 1fr 1fr */
```

The comma inside `repeat()` separates the **count** from the **size**. It's the only comma in a column template — track sizes themselves are separated by spaces.

### Rows
Usually you don't define rows at all. Grid makes them as needed, and each row is as tall as its tallest item. When you do want control:

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 100px 200px;   /* row 1 is 100px, row 2 is 200px */
}
```

If there are more items than those rows can hold, Grid adds extra rows automatically — and those extra rows ignore `grid-template-rows`. To size **every** automatic row, use `grid-auto-rows`:

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 150px;   /* every row is 150px tall, however many there are */
}
```

Rule of thumb: let rows size themselves (the default) unless you're building tiles that *must* be a set height, like a dashboard. Fixed row heights plus long text means text spilling out of the box.

### Practice Now
One grid with 6 boxes of different text lengths. Try each of these column templates in turn and write one line about what you see: `200px 200px 200px`, `1fr 1fr 1fr`, `1fr 2fr 1fr`, `200px 1fr`, `auto 1fr auto`. Resize the window for each. Which templates fill the width? Which stay the same size no matter what?

---

## 4. Grid Lines and Spanning

Grid numbers the **lines** between tracks, starting from 1. Three columns have **four** column lines. You can also count backwards from the end: the last line is always `-1`.

```
line:   1         2         3         4
        │  col 1  │  col 2  │  col 3  │
        │         │         │         │
from   -4        -3        -2        -1
the end:
```

You make an item cover more than one cell by saying which lines it runs between:

```css
.wide  { grid-column: 1 / 3; }    /* from line 1 to line 3 → covers columns 1 and 2 */
.wide  { grid-column: span 2; }   /* covers 2 columns, starting wherever it would normally go */
.full  { grid-column: 1 / -1; }   /* first line to last line → full width, however many columns */
.tall  { grid-row: span 2; }      /* covers 2 rows */
.third { grid-column: 3; }        /* starts at line 3 → sits in column 3 */
```

The other items flow around the big ones, filling free cells in order. By default Grid never goes back to fill a gap it has already passed, so a big item can leave a hole. That's normal. If it bothers you, change the spans or the order of the items.

> **The off-by-one trap:** `grid-column: 1 / 3` covers **two** columns, not three. You're naming *lines* — like the posts at either end of a fence panel. If counting lines trips you up, use `span`: `span 3` always means "three columns".

### See the lines
In Chrome or Edge dev tools, every grid container has a small **`grid`** badge next to it in the **Elements** panel. Click it and the browser draws the grid over your page. In the **Layout** tab you can turn on line numbers. Do this whenever a span doesn't land where you expected — the numbers answer the question instantly.

### Practice Now
A 4-column grid (`repeat(4, 1fr)`, `grid-auto-rows: 80px`) with 8 numbered boxes. Make box 1 `grid-column: span 2`, box 3 `grid-row: span 2`, and box 5 `grid-column: 1 / -1`. **Before you save**, sketch where you think each box will land. Then save, turn on the grid overlay with line numbers, and check. Are there any empty cells? Why?

---

## 5. Naming Areas with `grid-template-areas`

For whole-page layouts, counting lines gets fiddly. Instead, you can draw a little **map** of the layout, with a name in each cell:

```html
<div class="page">
    <header class="header">My Site</header>
    <nav class="sidebar">...links...</nav>
    <main class="content">...the main content...</main>
    <footer class="footer">Made by me</footer>
</div>
```

```css
.page {
    display: grid;
    grid-template-columns: 220px 1fr;
    grid-template-areas:
        "header  header"
        "sidebar content"
        "footer  footer";
    gap: 16px;
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.footer  { grid-area: footer; }
```

Read the map like a picture of the page:
- Each **string** (in quotes) is one row.
- Each **word** is one cell in that row — here, two per row, matching the two columns.
- Repeating a name makes that area bigger: `"header header"` makes the header cover both columns.
- `grid-area: header;` on an element says "go to the cells named `header`". **No quotes** here — it's a name, not a string.

The extra spaces in `"header  header"` just line the columns up so *you* can read the map. The browser doesn't care about them.

The rules — break one and the browser throws away the **whole** map, and your layout falls apart:
1. Every row must have the **same number of cells**.
2. Each area must be a **rectangle** — no L-shapes.
3. Use a `.` for an empty cell: `". content"`.

The best part: to change the layout, you just redraw the map. You never touch the HTML. In Section 14 you'll use exactly this to make the page work on a phone.

### Practice Now
Build the page above with real content: a heading in the header, three links in the nav, a heading and two paragraphs in main, one line in the footer. Give each area a different `background-color` so you can see it. Then move the sidebar to the **right**, by editing only the `grid-template-columns` and `grid-template-areas` lines.

---

## 6. Aligning Things in a Grid

Each grid item sits inside its cell, and by default it **stretches** to fill that cell — the same default as Flexbox. To change that, use `place-items` on the container:

| Property (on the container) | What it does |
|---|---|
| `place-items: center` | centres every item **inside its own cell**, across and down |
| `place-items: start` | puts every item in the top-left corner of its cell |
| `place-content: center` | moves the **whole grid** into the middle of the container (you only see this when the tracks don't already fill it, e.g. `repeat(3, 100px)` in a wide container) |

`place-items` is a shorthand for two properties: `align-items` (up and down) and `justify-items` (left and right). You'll mostly use the shorthand.

It also gives you the shortest centring recipe in CSS:

```css
.stage {
    display: grid;
    place-items: center;
    min-height: 300px;
}
```

Compare it with the three-line Flexbox version from Class 4. Both work — use whichever you remember first.

### Practice Now
Redo Class 4's "perfect centring" drill (a 100 × 100 box in a 400 × 300 container) with Grid. How many declarations did you need on the container this time?

---

## 7. Grid or Flexbox?

Both lay things out. The difference is how many directions you care about.

| | Flexbox | Grid |
|---|---|---|
| Directions | **one** — a row *or* a column | **two** — rows *and* columns at once |
| Who's in charge | the **items** — their content decides their size | the **container** — it draws the tracks, the items fill them |
| Typical jobs | navbars, button toolbars, centring one thing, a row of tags that wraps, the inside of a card | page layouts, galleries, card grids, dashboards, calendars |

A quick test: **do things need to line up in both directions?** If card 4 must sit exactly under card 1, that's Grid. If you just need things in a line, nicely spaced, that's Flexbox.

They're not rivals. Most real pages use both: Grid for the page and the card section, Flexbox for the navbar inside the header and for the content inside each card. Your Class 4 navbar can drop straight into the `header` area of a grid page.

> Remember Class 4's "card grid without Grid", where you worked out `calc((100% - 40px) / 3)`? With Grid it's `grid-template-columns: repeat(3, 1fr); gap: 20px;` — no maths, and the last row lines up with the others.

✅ **Checkpoint:** You can say in one sentence when you'd pick Grid and when you'd pick Flexbox — and you know you'll often use both on the same page.

---

## 8. What "Responsive" Means

A **responsive** page is one HTML file and one stylesheet that look right at every screen width: a phone (about 360–430px wide), a tablet (about 768px), a laptop or desktop (1280px and up). Most people will see your pages on a phone first, so this isn't extra polish. It's part of the job.

You have three tools. Reach for them in this order:

1. **The viewport meta tag** — one line that tells phones to show your page at its real size (Section 9).
2. **Flexible sizes** — `fr`, `%`, `rem`, `vw`, `clamp()`, images that shrink, and grids that choose their own column count. These adapt smoothly with **no extra rules** (Sections 10–12).
3. **Media queries** — "from this width up, change these styles" (Sections 13–14). Use them for changes flexible sizes can't make on their own, like moving a sidebar.

### How to test
You don't need a phone. In Chrome or Edge, open dev tools and press **`Ctrl+Shift+M`** (Mac: **`Cmd+Shift+M`**) to switch on the **device toolbar**. Pick a phone from the device list, or choose **Responsive** and type any width.

Get into the habit of checking three widths every time: **375px** (phone), **768px** (tablet), **1280px** (desktop). Slowly dragging the edge of the browser window narrower works too — watch for the moment something breaks.

### Practice Now
Open your Class 4 three-card row, switch on the device toolbar, and pick a **phone** from the device list. Describe what you see. Look closely: is the text tiny, as if the whole desktop page has been shrunk to fit? Keep that picture in mind — the next section explains it.

---

## 9. The Viewport Meta Tag

Time for one more upgrade to your page skeleton. From now on, every page gets the `viewport` line in its `<head>`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>My Page</title>
    <link rel="stylesheet" href="style.css">
</head>
```

Why it's needed: phone browsers arrived when almost every website was built for desktops. So, by default, a phone browser **pretends its screen is about 980px wide**, lays the page out at that width, and then shrinks the whole thing to fit the real screen. Old desktop sites "work", but everything is tiny — and your media queries see a 980px screen, so the phone styles never switch on.

The tag turns that off:
- `width=device-width` — "lay the page out at the phone's real width".
- `initial-scale=1` — "start at normal zoom, not zoomed in or out".

> You'll see some sites add `maximum-scale=1` or `user-scalable=no`. Don't. They stop people zooming in, and people with low vision rely on zooming.

### Practice Now
Take the page from Section 8's practice. With the device toolbar still showing a phone, add the viewport tag, save, and reload. The page now lays out at the phone's real width — and you can see what actually breaks. That's the honest starting point for responsive work.

✅ **Checkpoint:** You can type the viewport tag from memory and say, in one sentence, what goes wrong without it.

---

## 10. Relative Units: `%`, `rem`, `vw`, `vh`, and `clamp()`

`px` is a fixed size: 300px is 300px on a phone and on a huge monitor. Responsive layouts need sizes that *relate* to something.

| Unit | Relative to | Good for |
|---|---|---|
| `%` | the **parent's** size | widths inside a container |
| `rem` | the **root font size** (the `<html>` element) — 16px unless the user changed it | font sizes, spacing, the `max-width` of text columns |
| `em` | the **current element's** font size | padding on a button that should grow with its text |
| `vw` | 1% of the **viewport's width** (the browser window) | sizes that should follow the screen width |
| `vh` | 1% of the **viewport's height** | full-screen sections: `min-height: 100vh` |

### `rem`, properly this time
In Class 3 you met `rem` as "16px, written differently". Here's why it matters. Anyone can go into their browser settings and choose a bigger default text size — many people with low vision do. `rem` sizes grow with that setting. `px` font sizes ignore it.

So use `rem` for font sizes. The maths is easy while the root is 16px:

| px | rem |
|---|---|
| 14px | 0.875rem |
| 16px | 1rem |
| 20px | 1.25rem |
| 24px | 1.5rem |
| 32px | 2rem |

A handy trick for readable text: `max-width: 40rem` on a text column (about 640px) keeps lines a comfortable length, and grows if the user's text is bigger.

### `vw` on its own is a trap for text
`font-size: 5vw` follows the screen — but it's tiny on a phone (about 19px at 375px wide), enormous on a big monitor (96px at 1920px), and it ignores the user's text-size setting. That's what `clamp()` is for.

### `clamp(MIN, PREFERRED, MAX)`
```css
h1 {
    font-size: clamp(1.75rem, 1rem + 4vw, 3.5rem);
}
```

Read it as: "Use `1rem + 4vw`. But never go below `1.75rem`, and never above `3.5rem`."

- On a phone 375px wide: `1rem + 4vw` = 16px + 15px = **31px**. That's above the 28px minimum, so the heading is 31px.
- As the window widens, the heading grows smoothly — no sudden jumps.
- At about 1000px wide it reaches the 56px maximum and stops growing.

The middle value can be a small sum, like `1rem + 4vw`. Including a `rem` part keeps the user's text-size setting working.

`clamp()` works for any size, not just fonts. A favourite for page padding:

```css
body {
    padding: 24px clamp(16px, 5vw, 48px);   /* sides: 16px on phones, growing to 48px */
}
```

### Practice Now
A page with an `<h1>` and a paragraph. Set the `h1` to `font-size: 5vw` and drag the window from very narrow to very wide — notice both extremes. Then switch to `clamp(1.75rem, 1rem + 4vw, 3.5rem)` and do the same. Check the actual size in dev tools (**Elements → Computed → font-size**) at 375px, 768px, and 1280px.

---

## 11. Images That Fit

An `<img>` is as wide as the image file unless you say otherwise. A 1200px photo on a 375px phone sticks out of the page and gives you a horizontal scrollbar. Add this near the top of every stylesheet, right after the `box-sizing` reset:

```css
img {
    max-width: 100%;
    height: auto;
    display: block;
}
```

- `max-width: 100%` — never wider than its container. (Small images stay their natural size.)
- `height: auto` — keep the image's proportions as it shrinks.
- `display: block` — removes the thin gap under images. By default an image sits on a line of text like a big letter, with room left underneath for the tails of letters like "g" and "y".

### Tidy thumbnails: `aspect-ratio` + `object-fit`
Photos come in all shapes — wide, tall, square. In a gallery you usually want every tile the same shape:

```css
.gallery img {
    width: 100%;
    aspect-ratio: 1 / 1;
    object-fit: cover;
}
```

- `aspect-ratio: 1 / 1` — width to height, 1 to 1. The browser works out the height from the width, so every image becomes a square. Try `4 / 3` or `16 / 9` for other shapes.
- `object-fit: cover` — fill the box completely and **crop** whatever doesn't fit, instead of squashing the photo. It's `background-size: cover` from Class 3, but for an `<img>`.

Without `object-fit: cover`, a wide photo forced into a square gets squeezed — people look thin, and circles look like eggs. (`object-fit: contain` is the other option: the whole photo shows, with empty space around it.)

### Practice Now
Three images of different shapes: `https://picsum.photos/600/400`, `https://picsum.photos/400/600`, and `https://picsum.photos/500/500`. Give all three `width: 200px; aspect-ratio: 1 / 1;` and look — squashed. Then add `object-fit: cover`. Three neat squares, nothing distorted.

---

## 12. Responsive With No Media Queries: `auto-fit` + `minmax()`

This is the most useful single line in this class:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 16px;
}
```

Read it from the inside out:
- `minmax(220px, 1fr)` — each column is **at least** 220px and **at most** 1fr (an equal share of the space).
- `repeat(auto-fit, ...)` — instead of a fixed number like `3`, "make **as many columns as will fit**".

The result: in a 1200px-wide container you get 5 columns; on a tablet, 2 or 3; on a phone, 1. The columns always stretch to fill the row exactly. And you didn't write a single media query.

> **Keep the minimum small.** It has to fit on the narrowest phone. `minmax(400px, 1fr)` on a 360px phone can't fit even one column, so the grid sticks out past the screen and you get a horizontal scrollbar. Around 200–250px is safe for most cards.

### `auto-fit` vs `auto-fill`
With lots of items, they look identical. The difference shows when there are only a **few** items on a wide screen:

- `auto-fill` keeps making columns even when they're empty. Your 2 items stay card-sized, with empty space after them.
- `auto-fit` collapses the empty columns, so your 2 items **stretch** to share the whole row.

Pick `auto-fit` when items should always fill the row (most galleries). Pick `auto-fill` when items should keep a steady size, however few there are.

### Practice Now
Put 8 cards in a grid with `repeat(auto-fit, minmax(200px, 1fr))`. Drag the window from wide to narrow and watch the columns drop away one at a time. Then delete cards until only 2 are left, make the window wide, and switch between `auto-fit` and `auto-fill`. Write one sentence on what `minmax(200px, 1fr)` is doing.

✅ **Checkpoint:** A grid that goes from five columns to one on its own, in one line of CSS. Whenever you need "fewer columns on smaller screens", try this first.

---

## 13. Media Queries

Flexible sizes handle a lot. But some changes need a rule that switches on at a certain width: "put the sidebar beside the content once there's room", "make this photo cover two columns on bigger screens". That's what a **media query** does:

```css
/* Base styles: apply at every width */
.cards {
    display: grid;
    grid-template-columns: 1fr;
    gap: 16px;
}

/* Only when the viewport is 700px wide or wider */
@media (min-width: 700px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}
```

The anatomy:
- `@media` — "the rules in here only apply sometimes".
- `(min-width: 700px)` — the condition, **in parentheses**. `min-width: 700px` means "700px **or wider**". `max-width: 699px` means "699px **or narrower**".
- `{ ... }` — **complete rules** go inside: a selector with its own braces, exactly as you'd write it anywhere else. So there are two sets of braces.

The width being measured is the **viewport** — the browser window — not the element you're styling.

### Two things that trip everyone up
**1. A media query doesn't make a rule stronger.** When a query matches, its rules compete with your other rules the usual way (the cascade from Class 3): if the selectors are equally specific, the rule **later in the file** wins. That's why media queries go **after** the base rules they change — usually at the bottom of the file.

**2. Declarations without a selector are thrown away.** This does nothing:

```css
@media (min-width: 700px) {
    grid-template-columns: repeat(2, 1fr);   /* ❌ which element? */
}
```

The browser doesn't know which element you mean, so it ignores the line — and sometimes the next rule in the block along with it. Always write the selector.

### Where to put breakpoints
A **breakpoint** is a width where your layout changes. Don't chase particular phone models — there are thousands of them. Instead, start narrow and slowly widen the window. When the design starts to look stretched or empty, that's a breakpoint. **640px**, **768px**, and **1024px** are common starting points, but your content decides.

### Practice Now
One paragraph with `font-size: 1rem`. Then add:

```css
@media (min-width: 600px) {
    p {
        font-size: 1.125rem;
    }
}

@media (min-width: 900px) {
    p {
        font-size: 1.25rem;
    }
}
```

Set the device toolbar to widths either side of 600px and 900px, and check the computed size each time. Then swap the two blocks' order and try 1000px. Which size wins now, and why?

---

## 14. Mobile-First Thinking

There are two ways to write responsive CSS:

- **Desktop-first:** write the wide layout as your base styles, then add `max-width` queries that *undo* parts of it for smaller screens.
- **Mobile-first:** write the **phone** layout as your base styles, then add `min-width` queries that *add* columns as more room appears.

Use **mobile-first**. Here's why:
1. **The phone layout is the simplest.** It's mostly one column — which is what HTML does on its own. Your base styles stay short.
2. **You add instead of undo.** Undoing is where bugs hide: a leftover width, a span you forgot to reset, a margin that only made sense side by side.
3. **The queries stack cleanly.** Write `min-width` queries **smallest first**. On a wide screen, every query up to that width matches, and the last (largest) one wins — exactly what you want.
4. **It makes you decide what matters.** On a phone there's only room for the important things.

Here's the page from Section 5, rewritten mobile-first:

```css
/* Phone: one column. The map is just the four areas stacked. */
.page {
    display: grid;
    gap: 16px;
    grid-template-areas:
        "header"
        "sidebar"
        "content"
        "footer";
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.footer  { grid-area: footer; }

/* Tablet and up: sidebar beside the content. */
@media (min-width: 768px) {
    .page {
        grid-template-columns: 220px 1fr;
        grid-template-areas:
            "header  header"
            "sidebar content"
            "footer  footer";
    }
}
```

The HTML never changes. At 768px and wider, the map is redrawn with two columns. (With a one-column map you don't even need `grid-template-columns` — the single column fills the width.)

### Keep spans inside the query too
A `grid-column: span 2` on a grid that only has **one** column doesn't shrink to fit. The browser adds an extra column to make room, and your page gets a horizontal scrollbar on phones. So put spans inside the `min-width` query, where you know the grid has at least two columns. You'll do exactly this in the guided practice.

### The mobile-first checklist
- [ ] The base styles have **no** media query and describe the phone layout.
- [ ] Every media query is `min-width`, ordered **smallest to largest**.
- [ ] Media queries sit **after** the base rules.
- [ ] Spans and multi-column templates live inside the queries.

You'll still see `max-width` queries in other people's code (and in one of this class's assignments). They work. Mobile-first is just easier to keep tidy.

✅ **Checkpoint:** You can explain why mobile-first uses `min-width`, and why the queries go smallest first.

---

## 15. Guided Practice: Build a Responsive Photo Gallery

This is the main build for Class 5. It uses almost everything in this class: the viewport tag, flexible images, an `auto-fit` grid that picks its own column count, and one mobile-first media query.

### Requirements
- [ ] The viewport meta tag in the `<head>`
- [ ] The `box-sizing` reset and the `img` reset from Section 11
- [ ] A heading and a short intro above the gallery, centred, and no wider than a comfortable reading width
- [ ] 12 photos in a grid using `repeat(auto-fit, minmax(220px, 1fr))` with a `gap`
- [ ] Photos of **mixed shapes** (wide, tall, square), all shown as neat squares with `aspect-ratio: 1 / 1` and `object-fit: cover`
- [ ] The column count changes by itself — 1 column on a phone up to 5 on a wide screen — with **no** media query for the columns
- [ ] One mobile-first media query: from 700px up, the first photo is **featured** (it covers 2 columns and 2 rows) and the gap grows a little
- [ ] Fluid side padding and a fluid heading, both with `clamp()`

**`index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>My Photo Gallery</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header class="intro">
        <h1>My Photo Gallery</h1>
        <p>A few favourite shots. Resize the window and watch the grid rearrange itself.</p>
    </header>

    <main>
        <section class="gallery">
            <img src="https://picsum.photos/800/600?random=1" alt="Placeholder photo 1" class="featured">
            <img src="https://picsum.photos/600/800?random=2" alt="Placeholder photo 2">
            <img src="https://picsum.photos/600/600?random=3" alt="Placeholder photo 3">
            <img src="https://picsum.photos/800/500?random=4" alt="Placeholder photo 4">
            <img src="https://picsum.photos/500/800?random=5" alt="Placeholder photo 5">
            <img src="https://picsum.photos/600/600?random=6" alt="Placeholder photo 6">
            <img src="https://picsum.photos/800/600?random=7" alt="Placeholder photo 7">
            <img src="https://picsum.photos/600/800?random=8" alt="Placeholder photo 8">
            <img src="https://picsum.photos/600/600?random=9" alt="Placeholder photo 9">
            <img src="https://picsum.photos/800/500?random=10" alt="Placeholder photo 10">
            <img src="https://picsum.photos/500/800?random=11" alt="Placeholder photo 11">
            <img src="https://picsum.photos/600/600?random=12" alt="Placeholder photo 12">
        </section>
    </main>
</body>
</html>
```

The `?random=1`, `?random=2`… on the end of each address makes the placeholder service send a different photo each time. Without it, the browser may show you the same photo twelve times.

While these are random placeholders, `alt="Placeholder photo 3"` is honest. When you swap in your own photos (please do), write a real description of each one.

**`style.css`**

```css
/* Resets */
*, *::before, *::after {
    box-sizing: border-box;
}

img {
    max-width: 100%;
    height: auto;
    display: block;
}

/* Page */
body {
    margin: 0;
    padding: 24px clamp(16px, 5vw, 48px);
    font-family: system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    line-height: 1.6;
    color: #222;
    background-color: #f4f4f4;
}

.intro {
    max-width: 40rem;
    margin: 0 auto 32px auto;
    text-align: center;
}

.intro h1 {
    font-size: clamp(1.75rem, 1rem + 4vw, 3rem);
    margin: 0 0 8px 0;
}

/* The gallery */
.gallery {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 12px;
}

.gallery img {
    width: 100%;
    aspect-ratio: 1 / 1;
    object-fit: cover;
}

/* Wider screens: a bit more breathing room, and a big featured photo */
@media (min-width: 700px) {
    .gallery {
        gap: 16px;
    }

    .gallery .featured {
        grid-column: span 2;
        grid-row: span 2;
    }
}
```

Type it by hand, save both files, and open `index.html` with Live Server.

### Test it
Switch on the device toolbar and check these widths:

| Width | What you should see |
|---|---|
| 375px | one column of large squares; photo 1 is a normal tile |
| 768px | two columns; photo 1 is a big square across both columns |
| 1024px | three or four columns (depending on your scrollbar); photo 1 covers 2 × 2 cells |
| 1280px | five columns; photo 1 covers 2 × 2 cells |

Then drag the window slowly from very narrow to very wide and watch the columns change.

### Acceptance criteria
- No horizontal scrollbar at any width from 320px to 1440px.
- Every photo is a square; nothing is squashed or stretched.
- Photo 1 is featured (2 × 2) only at 700px and wider. Below that, it's a normal tile.
- The column count comes from `auto-fit` + `minmax()` alone. Your only media query is for the featured photo and the gap.
- The dev-tools grid overlay shows the featured photo covering exactly 2 × 2 cells.

✅ **Checkpoint:** A gallery that works from a small phone to a wide monitor, in about 60 lines of CSS, with just one media query.

---

## 16. Troubleshooting

| Problem | Likely cause |
|---|---|
| Everything is still in one column | `display: grid` is missing, or it's on a child instead of the container. Or the `grid-template-columns` value is invalid — commas between sizes (`1fr, 1fr`) are the classic. Dev tools shows an invalid declaration struck through with a ⚠ warning icon. |
| `grid-column: 1 / 3` covers two columns, not three | You're naming **lines**, not columns. Use `1 / 4`, or `span 3`. |
| The page layout falls apart and the areas pile up in one spot | The `grid-template-areas` map is invalid, so the browser dropped all of it: rows with different numbers of cells, an area that isn't a rectangle, or a name spelled differently in the map and in `grid-area`. |
| One item ignores its `grid-area` | Quotes around the name. `grid-area: "header"` is invalid; write `grid-area: header;`. |
| The page looks tiny and zoomed-out on a phone, and media queries never switch on | The viewport meta tag is missing from `<head>`. |
| A media query does nothing | The declarations inside have no selector; or the parentheses are missing (`@media min-width: 700px` is invalid); or a missing `}` earlier in the file broke everything after it. |
| The media query applies, but the "wrong" value wins | Order. With equal specificity, the later rule wins. Base rules first, then `min-width` queries from smallest to largest. |
| A horizontal scrollbar on phones | An image without `max-width: 100%`; a fixed `px` width wider than the screen; a `minmax()` minimum too big for a phone; or a `span 2` on a grid that only has one column at that width. |
| Photos look squashed or stretched | You set `aspect-ratio` (or a fixed `height`) without `object-fit: cover`. |
| Two cards stretch into huge slabs on a wide screen | `auto-fit` collapses the empty columns. Use `auto-fill`, or cap the maximum, e.g. `minmax(200px, 300px)`. |
| A thin gap under every image | Images sit on the text line by default. Add `display: block`. |
| Text spills out of grid tiles | Fixed row heights (`grid-auto-rows: 150px`) with more content than fits. Let rows size themselves, or use `minmax(150px, auto)`: at least 150px, taller if needed. |

---

## 17. Self-Check: Can You Answer These?

Try without scrolling back.

1. What one declaration turns an element into a grid container? Which elements become grid items?
2. What does `1fr` mean? Why is `1fr 1fr 1fr` safer than `33% 33% 33%` when there's a `gap`?
3. Write `repeat(4, 1fr)` out the long way.
4. A grid has 3 columns. How many column lines does it have? What does `grid-column: 1 / -1` do?
5. Name two rules the strings in `grid-template-areas` must follow.
6. Grid or Flexbox for a navbar? For a photo gallery? For a whole-page layout? Give one reason each.
7. What does the viewport meta tag do? What happens on a phone without it?
8. What is `1rem` relative to, and why use `rem` instead of `px` for font sizes?
9. Explain `repeat(auto-fit, minmax(220px, 1fr))` in plain English.
10. What does "mobile-first" mean? Which kind of media query does it use, and in what order do they go?

---

## 18. Homework

1. **Make your About Me and Contact pages responsive** (the course homework). Work on copies so the originals stay safe. Checklist:
   - [ ] The viewport meta tag in both `<head>`s
   - [ ] The `img` reset (`max-width: 100%; height: auto; display: block;`) so no image can overflow
   - [ ] The main content gets a `max-width` and fluid side padding: `padding: 0 clamp(16px, 5vw, 48px)`
   - [ ] **About Me:** pick two content sections (e.g. "Things I Like" and "Goals"). Wrap them in one `<div class="two-col">` — the only other HTML change allowed. Mobile-first: they stack on phones, and from 640px they sit side by side in a 2-column grid.
   - [ ] **Contact:** your Class 4 two-column fields become **one column** on phones, and two from 640px. Either keep Flexbox (every field full width in the base styles; the half-width `flex` value only inside `@media (min-width: 640px)`), or switch the fields' container to Grid (`1fr` on phones; `1fr 1fr` from 640px, with full-width fields using `grid-column: 1 / -1`).
   - [ ] Test both pages at 375px, 768px, and 1280px, with no horizontal scrollbar at any of them.

2. *(Optional)* Rebuild your Class 4 three-card row with `grid-template-columns: repeat(auto-fit, minmax(240px, 1fr))`. Count how many lines of CSS you deleted.

For a lot more practice on this class — spanning drills, named-area layouts, breakpoint challenges, and debugging exercises with answers — see the **Class 5** section of [`assignments.md`](assignments.md).

---

## What's Next

Class 6 is **JavaScript Basics** — the third layer of the web. HTML is the structure, CSS is the look, and JavaScript is the *behaviour*. You'll start in the browser's Console with variables, conditions, loops, and functions: pure logic, no page changes yet. Keep your gallery and your About Me page safe — in Class 7 you'll make them interactive.
