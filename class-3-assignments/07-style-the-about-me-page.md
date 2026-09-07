# Assignment 07 — Style the About Me Page

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min · 🧵 keep this file
**Prereqs:** Class 2 Assignment 07 (semantic About Me) done; Class 3 §5–13
**Build in:** `work/07-style-about-me/index.html` + `style.css`

---

## Goal

Give your semantic About Me page a designed look with an external stylesheet — layout by box model only, no Flexbox.

## What you'll practice

- The `box-sizing` reset
- Centring a content column with `max-width` + `margin: 0 auto`
- A type scale, consistent spacing, and styled links

## Instructions

1. Copy your Class 2 semantic About Me into `work/07-style-about-me/index.html`. Add a `<link rel="stylesheet" href="style.css">` to its `<head>` — **that is the only HTML change allowed.**
2. Create `style.css` and meet every requirement below.

## Requirements

**Foundations**
- [ ] `*, *::before, *::after { box-sizing: border-box; }` at the top
- [ ] `body`: a `font-family` stack, base `font-size`, `line-height: 1.6`, a text `color` that isn't pure black (e.g. `#222`), and a page `background-color`

**Layout (box model only)**
- [ ] `<main>` constrained with `max-width` (~700px) and centred with `margin: 0 auto`
- [ ] `<main>` has `padding` so text doesn't touch the edges
- [ ] `<header>` and `<footer>` each get a distinct `background-color` and `padding`

**Navigation**
- [ ] Nav links styled (`nav a`): `display: inline-block`, `padding`, a `color`, `text-decoration: none`

**Type & spacing**
- [ ] A type scale for `h1`, `h2`, `p`
- [ ] Consistent gaps between sections — pick **one** property (e.g. `margin-bottom` on each `<section>`) and one value, used everywhere

**Details**
- [ ] The profile `<img>`: a fixed `width` and a `border`
- [ ] Body-content links given a `color` (decide about the underline)

## Acceptance criteria

- The HTML content is unchanged (only the `<link>` was added).
- Content is centred with a comfortable reading width; nothing touches the browser edges.
- Headings are clearly, consistently stepped above body text.
- No horizontal scrollbar at a normal window size.
- Inspecting `<main>` shows `max-width` + `auto` side margins doing the centring.

## Hints

<details><summary>Show hint</summary>

If the content column isn't centring: it needs a `max-width` (or `width`) **and** it must be a block element (it is — `<main>` is block by default). `margin: 0 auto` shares the leftover horizontal space evenly.
</details>

## Stretch (optional)

Add a subtle `border` or extra `padding` to each `<section>`, or a `background-color` on alternating sections — just keep the spacing scale consistent.
