# Class 3: CSS Basics — Styling & the Box Model
### A self-guided read-through — read each section, then do the practice before moving on. Have your semantic "About Me" page from Class 2 ready; you'll style it at the end.

---

## 1. Recap: Where We Are

You can now write **structured, meaningful HTML** — headings, paragraphs, lists, links, images, semantic landmarks, tables, and forms. Every page you've built still looks like plain black text on a white background.

That changes today. **CSS** (Cascading Style Sheets) is the language that controls how a page *looks*: colours, fonts, sizes, spacing, and — from Class 4 — layout.

The single most important idea in this class is the **box model**. If you understand the box model, most "why is there a gap there?" and "why won't this line up?" questions answer themselves. Spend real time on Section 6.

---

## 2. What CSS Is

HTML says *what things are*. CSS says *how they should look*.

```
HTML:  <p>Hello</p>
CSS:   p { color: blue; font-size: 20px; }
Result: the word "Hello", in blue, at 20 pixels.
```

CSS is a list of **rules**. Each rule picks some elements and describes how to style them.

---

## 3. The Anatomy of a CSS Rule

```css
h1 {
    color: navy;
    font-size: 32px;
}
```

| Part | Name | Meaning |
|---|---|---|
| `h1` | **selector** | *Which* elements this rule applies to (here: every `<h1>`) |
| `{ ... }` | **declaration block** | The set of style changes, wrapped in curly braces |
| `color: navy;` | **declaration** | One change: a **property** and a **value**, separated by a colon, ended with a semicolon |
| `color` | **property** | What you're changing |
| `navy` | **value** | What you're changing it to |

Rules to burn in:
- Every declaration ends with a **semicolon** `;`. Forgetting it usually breaks the *next* line too.
- The colon `:` separates property from value. The semicolon `;` ends the declaration.
- Whitespace and line breaks don't matter to the browser — but write one declaration per line, indented, for your own sanity.

---

## 4. Connecting CSS to HTML

There are three ways to attach CSS. You will learn all three, then use **only the third**.

| Method | Looks like | Verdict |
|---|---|---|
| **Inline** | `<p style="color: red;">` | Avoid. Can't reuse, clutters HTML, hard to override. |
| **Internal** | `<style>` block inside `<head>` | OK for a quick test. Doesn't share between pages. |
| **External** | a separate `.css` file, linked in | ✅ **Best practice. Use this.** |

### Why external wins
- One stylesheet can style **every page** of a site.
- HTML stays about structure; CSS stays about appearance. (Remember "div soup"? This is the same idea — keep concerns separate.)
- The browser downloads the file once and reuses it — faster.

### Setup
1. In the same folder as your `index.html`, create a file called `style.css`.
2. In your HTML `<head>`, add this line:

```html
<head>
    <meta charset="UTF-8">
    <title>My Page</title>
    <link rel="stylesheet" href="style.css">
</head>
```

3. Prove it's connected. Put this in `style.css`, save, and check the browser:

```css
body {
    background-color: lightyellow;
}
```

If the page turns pale yellow, you're wired up.

> **`<link>`** is a self-closing tag. `rel="stylesheet"` tells the browser what kind of link it is; `href` is the path to the file — exactly like `href` on an `<a>`.

### Practice Now
Make a folder `css-practice/` with `index.html` (a heading and two paragraphs) and `style.css`. Link them. Make the `<body>` background a colour you like and the paragraphs a different text colour. Save and confirm both changes appear.

✅ **Checkpoint:** You changed the page's look without touching the HTML's content. That separation is the whole point.

---

## 5. Selectors — Choosing What to Style

The selector is the part before the `{`. Here are the five you need now.

### Element selector
Targets **every** element of that type.

```css
p { line-height: 1.6; }
a { color: teal; }
```

### Class selector — `.name`
Targets any element with that `class`. Reusable — put the same class on as many elements as you like. **This is your main tool.**

```html
<p class="intro">Bigger intro text.</p>
<p>Normal text.</p>
<p class="intro">Another intro-styled paragraph.</p>
```

```css
.intro {
    font-size: 20px;
    font-weight: bold;
}
```

An element can have **several** classes, space-separated:

```html
<button class="btn btn-primary">Send</button>
```

### ID selector — `#name`
Targets the **one** element with that `id`. An `id` must be **unique on the page** — use it once. Use ids sparingly; prefer classes.

```html
<header id="site-header"> ... </header>
```

```css
#site-header {
    background-color: #222;
}
```

### Descendant selector — `A B`
Targets every `B` that is **inside** an `A` (at any depth).

```css
nav a { text-decoration: none; }      /* links inside <nav> only */
footer p { font-size: 14px; }         /* paragraphs inside <footer> only */
.card h2 { margin-top: 0; }           /* <h2> inside any .card */
```

### Grouping — `A, B, C`
One rule, several selectors, separated by commas.

```css
h1, h2, h3 {
    font-family: Georgia, serif;
}
```

> **Careful:** `nav a` (space) means "`a` inside `nav`". `nav, a` (comma) means "every `nav` **and** every `a` on the page". A misplaced comma is a classic bug.

### Practice Now
On a page with an `<h1>`, some `<p>`s, a `<nav>` containing a `<ul>` of links, and a `<p class="lead">`:
1. Colour every `<h2>` dark blue.
2. Remove the underline from links **inside the nav only**.
3. Make only `.lead` bold and 18px.
4. Give every `<p>` a `line-height` of 1.6 (one rule).

---

## 6. The Box Model — The Most Important Section in This Course

**Every element on a page is a rectangular box.** Even text sits inside a box. Each box has four layers, from the inside out:

```
        ┌───────────── margin ─────────────┐
        │   (transparent space OUTSIDE)    │
        │   ┌────────── border ──────────┐  │
        │   │   ┌────── padding ──────┐  │  │
        │   │   │                     │  │  │
        │   │   │      CONTENT        │  │  │
        │   │   │   (text, image)     │  │  │
        │   │   │                     │  │  │
        │   │   └─────────────────────┘  │  │
        │   └───────────────────────────┘  │
        └──────────────────────────────────┘
```

| Layer | What it is | Key point |
|---|---|---|
| **content** | the actual text or image | `width` / `height` set its size (by default) |
| **padding** | space **inside** the box, between content and border | the background colour shows through it; pushes the border outward |
| **border** | a line around the padding | has a width, a style, and a colour: `border: 2px solid #333;` |
| **margin** | space **outside** the box, pushing other boxes away | always transparent; no background |

### See it for real
Open any page, right-click an element → **Inspect**. In the dev tools, find the **box model diagram** (a set of nested rectangles). Hover it — the browser highlights content (blue), padding (green), border (yellow), margin (orange) right on the page. Do this constantly. It is the fastest way to understand spacing.

### Writing box values

```css
.box {
    width: 300px;
    padding: 20px;                 /* all four sides */
    border: 1px solid #ccc;
    margin: 40px;                  /* all four sides */
}
```

Shorthand for padding and margin:

```css
padding: 10px;                 /* all sides: 10 */
padding: 10px 20px;            /* top+bottom: 10, left+right: 20 */
padding: 10px 20px 30px 40px;  /* top, right, bottom, left (clockwise) */

margin-bottom: 24px;           /* just one side */
margin: 0 auto;                /* top+bottom: 0, left+right: auto → centres the box */
```

> **`margin: 0 auto` centres a block horizontally** — but only if the element has a `width` or `max-width` less than its container. `auto` means "share the leftover space equally on both sides". You'll use this to centre page content until we get to Flexbox.

### `box-sizing` — the gotcha everyone hits

By default (`box-sizing: content-box`), `width` sets the size of the **content only**. Padding and border are **added on top**.

```css
.card {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
}
/* Actual width on screen: 300 + 20 + 20 + 5 + 5 = 350px */
```

This surprises everyone and causes layouts to overflow. The fix: `box-sizing: border-box`, which makes `width` include padding and border.

```css
.card {
    box-sizing: border-box;
    width: 300px;
    padding: 20px;
    border: 5px solid black;
}
/* Actual width on screen: exactly 300px. Content shrinks to make room. */
```

**Standard practice:** put this reset at the very top of every stylesheet and forget about the problem forever:

```css
*, *::before, *::after {
    box-sizing: border-box;
}
```

(`*` is the **universal selector** — "every element".)

### One more thing: vertical margins collapse

If one box has `margin-bottom: 30px` and the next has `margin-top: 20px`, the gap between them is **30px, not 50px** — the larger of the two "wins". This only happens with top/bottom margins between block elements. Don't fight it; just know it's why your spacing sometimes looks smaller than the numbers suggest.

### Practice Now
Three `<p>` elements, each with a visible `border` so you can see its edges:
1. First: `padding: 30px`, no margin. Notice the space *inside* the border.
2. Second: `margin: 30px`, no padding. Notice the space *outside* the border.
3. Third: `width: 250px; padding: 20px; border: 4px solid` — measure it in dev tools. Then add the `border-box` reset and measure again.

✅ **Checkpoint:** You can state, without looking, the difference between padding and margin, and what `border-box` changes.

---

## 7. Colours

Three ways to write a colour:

| Form | Example | Notes |
|---|---|---|
| **Named** | `tomato`, `navy`, `rebeccapurple` | ~140 names. Fine for quick work. |
| **Hex** | `#e63946`, `#000`, `#fff` | `#RRGGBB` (red, green, blue), base-16. `#000` = black, `#fff` = white. The most common form. |
| **rgb / rgba** | `rgb(230, 57, 70)` / `rgba(0, 0, 0, 0.5)` | Each channel 0–255. The 4th value in `rgba` is **alpha** (opacity): `0` = invisible, `1` = solid. |

```css
body      { background-color: #f4f4f4; }
h1        { color: #1a1a1a; }
.overlay  { background-color: rgba(0, 0, 0, 0.6); }  /* 60% black, lets what's behind show through */
```

- `color` sets the **text** colour.
- `background-color` sets the **fill behind** the element.
- **Contrast matters.** Light-grey text on a white background is unreadable for many people. Keep body text dark on light, or light on dark.

---

## 8. Typography

### `font-family` — always give fallbacks

```css
body {
    font-family: system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
}
h1, h2, h3 {
    font-family: Georgia, "Times New Roman", serif;
}
```

The browser reads the list left to right and uses the **first font the user's computer actually has**. Always end with a **generic family** — `sans-serif`, `serif`, or `monospace` — as the last resort. Wrap any font name containing spaces in quotes.

(You can load custom fonts from Google Fonts with another `<link>` in the `<head>`. Not required this class — the system stack above looks good and loads instantly.)

### The other typography properties

```css
p {
    font-size: 16px;      /* 16px is a sensible base for body text */
    line-height: 1.6;     /* unitless multiplier: 1.6 × font-size. 1.4–1.7 reads well */
    font-weight: 400;      /* 400 = normal, 700 = bold. Or the words: normal / bold */
    text-align: left;      /* left | right | center | justify */
    letter-spacing: 0;     /* try 0.05em on an ALL-CAPS heading */
}

.eyebrow {
    text-transform: uppercase;   /* also: lowercase | capitalize */
    letter-spacing: 0.08em;
}
```

Guidance:
- Set `font-family`, `font-size`, `color`, and `line-height` on `body` once. Everything inherits it.
- Build a small **type scale**: e.g. `h1` 2rem, `h2` 1.5rem, `p` 1rem. Consistent sizes look designed; random sizes look messy.
- `line-height` with **no unit** is best (it scales with the font size of each element).

> **`rem` vs `px`:** `1rem` = the root font size (16px by default). `2rem` = 32px. Using `rem` for font sizes means everything scales together if you change the base. `px` is fine while you're learning; you'll meet `rem` properly in Class 5.

---

## 9. Backgrounds

```css
.hero {
    background-color: #0b3d91;                    /* solid colour */
}

.banner {
    background-image: url("mountains.jpg");        /* an image file */
    background-size: cover;                        /* fill the box, cropping if needed */
    background-position: center;                   /* keep the middle of the image visible */
    background-repeat: no-repeat;                  /* don't tile it */
}
```

- `background-size: cover` — scale the image to **fill** the box, cropping the overflow. Best for photos.
- `background-size: contain` — scale so the **whole image fits**, possibly leaving gaps.
- `background-position: center` — which part stays visible when it's cropped.
- If you set both a `background-color` and a `background-image`, the colour shows through any transparent parts and while the image loads.

---

## 10. `display` — How a Box Behaves

| Value | Behaviour | Examples of elements that default to it |
|---|---|---|
| `block` | Starts on a new line, takes the **full width** available. Respects `width`, `height`, all margins. | `div`, `p`, `h1`–`h6`, `section`, `ul`, `li` |
| `inline` | Flows **within a line** of text, only as wide as its content. **Ignores** `width`, `height`, and top/bottom margin. | `a`, `span`, `strong`, `em` |
| `inline-block` | Flows inline (sits next to other things) **but respects** `width`, `height`, padding, and margin. | — (you opt in) |
| `none` | Removed from the page entirely — takes up **no space** at all. | — (you opt in) |

`inline-block` is handy this class: it lets you give nav links padding and spacing so they sit in a row with breathing room, without Flexbox.

```css
nav a {
    display: inline-block;
    padding: 8px 12px;
    margin-right: 4px;
}
```

`display: none` fully hides an element (content *and* its box). Different from making it the same colour as the background — `none` means it's not there at all.

---

## 11. The Cascade & Specificity (Short Version)

When two rules set the **same property** on the **same element**, which wins?

1. **More specific selector wins.** Rough ranking: `#id` (strong) > `.class` (medium) > `element` (weak).
2. **On a tie, the rule written later in the file wins.**

```css
p { color: black; }
.note { color: gray; }
#intro { color: navy; }
```

```html
<p id="intro" class="note">Which colour am I?</p>
```

→ **navy**, because `#intro` (an id) beats `.note` (a class) beats `p` (an element).

Practical advice for now:
- Style with **classes** most of the time. They're easy to reuse and easy to override.
- Use `#id` rarely — for genuinely one-off elements.
- **Avoid `!important`.** It's a sledgehammer that makes future changes harder. If you're reaching for it, your selectors are fighting — fix those instead.
- When something's "not applying", open dev tools → select the element → the **Styles** panel shows every rule targeting it, with the losing ones **struck through**. That tells you exactly what won and why.

---

## 12. Guided Practice: Style the "About Me" Page

This is the main build for Class 3. Work on the **semantic** About Me page from Class 2 (Assignment 07). Create a `style.css` next to it and link it.

### Requirements checklist

**Foundations**
- [ ] `box-sizing` reset at the top (`*, *::before, *::after { box-sizing: border-box; }`)
- [ ] On `body`: a `font-family` stack, a base `font-size`, `line-height: 1.6`, a text `color` that isn't pure black (e.g. `#222`), and a page `background-color`

**Layout (with box model only — no Flexbox yet)**
- [ ] Constrain `<main>` with `max-width: 700px` and centre it with `margin: 0 auto`
- [ ] Give `<main>` some `padding` so text doesn't touch the edges
- [ ] Give `<header>` and `<footer>` a distinct `background-color` and `padding`

**Navigation**
- [ ] Style the nav links (use `nav a` or a class): `display: inline-block`, padding, a `color`, and remove the underline (`text-decoration: none`)

**Typography & spacing**
- [ ] A type scale: set sizes for `h1`, `h2`, and `p` (they should feel deliberately stepped)
- [ ] Consistent gaps between sections — pick **one** direction (e.g. `margin-bottom` on each `<section>`) and use the same value

**Details**
- [ ] The profile `<img>`: a fixed `width`, a `border`, maybe some `margin`
- [ ] Style body-content links (a `color`, and decide about the underline)

### Acceptance criteria
- The page content is unchanged — you only edited `style.css`.
- Nothing touches the browser edges; the content column is centred with comfortable line length.
- Headings are clearly larger than body text, in a consistent scale.
- Inspecting `<main>` in dev tools shows the `max-width` and `auto` side margins doing the centring.
- No horizontal scrollbar at a normal window width.

✅ **Checkpoint:** Your plain HTML page now looks like a designed document, and you can point to the exact CSS rule responsible for each visual change.

---

## 13. Troubleshooting

| Problem | Likely cause |
|---|---|
| The stylesheet does nothing at all | `href` doesn't match the file name, or `<link>` isn't in `<head>`, or `rel="stylesheet"` is misspelled. Open dev tools → **Network** tab → look for a red/404 line for your CSS file. |
| One property is ignored, the rest work | Typo in the property name, or a missing **unit** (`width: 300` does nothing — needs `300px`), or a missing `;` broke this line and the next. |
| My change won't show up | Did you **save** `style.css`? Try a hard refresh (`Ctrl+Shift+R`). Check you're editing the file that's actually linked. |
| An element is wider than its container / there's a horizontal scrollbar | `content-box` maths: `width` + padding + border overflowed. Add the `border-box` reset. |
| `margin: 0 auto` isn't centring anything | The element has no `width`/`max-width`, or it's `display: inline`. Give it a `max-width` and make sure it's a block. |
| A colour name "doesn't work" | It's not a real CSS colour keyword, or it's misspelled. Use a hex value. |
| Two rules conflict and the "wrong" one wins | Specificity or order. Inspect the element; the Styles panel shows the winner and strikes through the losers. An `#id` rule beats a `.class` rule. |
| `text-align: center` won't centre my image | `text-align` goes on the **parent** and centres inline content. To centre a block image, make it `display: block` and use `margin: 0 auto`. |
| Spacing looks smaller than my numbers | Vertical margins between blocks **collapse** to the larger value, they don't add. |
| Page still looks unstyled after all that | The `<link>` line may be inside `<body>` or after `</html>`. It must be inside `<head>`. |

---

## 14. Self-Check: Can You Answer These?

Try without scrolling back.

1. Name the three ways to add CSS to a page. Why do we use the external file?
2. Write a CSS rule from memory and name all four parts (selector, declaration block, property, value).
3. Class selector vs id selector — what's the difference, and when do you use each?
4. What does `nav a` select? What does `nav, a` select? Why does the comma change everything?
5. List the four layers of the box model from the inside out.
6. Give one situation where only `padding` is correct, and one where only `margin` is correct.
7. What exactly does `box-sizing: border-box` change? Why is it usually applied to every element?
8. An element has `width: 200px; padding: 20px; border: 5px solid`. How wide is it on screen with the default `box-sizing`? With `border-box`?
9. Why must a `font-family` value end with `sans-serif` or `serif`?
10. Two rules set `color` on the same element with equal specificity. Which one wins?

---

## 15. Homework

1. **Style the Class 2 contact form page** (from Assignment 11). Create a `style.css` for it. Checklist:
   - [ ] The `box-sizing` reset; a `body` font, colour, and background
   - [ ] Constrain the `<form>`: `max-width: 480px`, `margin: 0 auto`, `padding`, and a subtle `border` or `background-color`
   - [ ] `label { display: block; }` with a small `margin-bottom`
   - [ ] Inputs, `<textarea>`, and `<select>`: `width: 100%`, `padding: 10px`, a `border` (the global `border-box` reset keeps them from overflowing)
   - [ ] Even spacing between fields (e.g. `margin-bottom` on each wrapping `<p>`)
   - [ ] The submit `<button>`: `padding`, a `background-color`, a text `color`, `border: none`, `cursor: pointer`
   - [ ] Give `<fieldset>` some padding and style the `<legend>`
   - [ ] Style the surrounding `<header>` / `<footer>` to match your About Me page

2. *(Optional)* Make a **second stylesheet** — `theme-dark.css` — for your About Me page: dark background, light text, a different accent colour, a different font. Swap which file the `<link>` points to and watch the whole look change with **zero HTML edits**. That's the separation of structure and style, proven.

For a lot more practice on this class — selector drills, box-model maths problems, "match the mockup" builds, and debugging exercises with answers — see the **Class 3** section of [`assignments.md`](assignments.md).

---

## What's Next

Class 4 is **Flexbox** — the tool for actual layout: navbars, rows of cards, sidebars, centring things properly. Everything so far has stacked straight down the page. Bring your styled About Me page and your styled contact form.
