# Class 4 Assignments — CSS Layout: Flexbox

Practice for **Class 4**. Read the lesson first:
[../class-4-css-layout-flexbox.md](../class-4-css-layout-flexbox.md)

---

## How to use this folder

- Do **all warm-ups (01–06)** in order — they drill the two-axis mental model, which everything else depends on.
- Work through the **core set (07–13)** — the real builds. Finish at least **07 (navbar)**, **08 (three-card row)**, and **13 (contact form → two columns)**; those are the class hands-on and homework.
- Do **debug (17)** and pick from **challenge (14–16)** as time allows.
- Answer the **written questions (18)** from memory, in a text file.
- Put your code in `work/<assignment-slug>/` — usually an `index.html` **and** a `style.css`. See [work/README.md](work/README.md).
- **Type everything by hand.** Save both files. Check the browser after every change. When something isn't aligning right, check `flex-direction` first — it decides which axis every other property acts on.

## Scope — only what's been taught

Use only Class 1–4 material.

**In scope this class:**
- `display: flex`, `flex-direction` (`row` / `column`)
- Main axis vs cross axis
- `justify-content`: `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly`
- `align-items` / `align-self`: `stretch`, `flex-start`, `center`, `flex-end`, `baseline`
- `flex-wrap`, `gap` / `row-gap` / `column-gap`
- `flex-grow`, `flex-shrink`, `flex-basis`, the `flex` shorthand
- `order`
- Everything from Classes 1–3 (semantic HTML, forms, external CSS, the box model, colour, typography, `display: block/inline/inline-block/none`)

**Not yet — do not use:**
- CSS Grid
- `@media` queries / responsive breakpoints — that's Class 5
- `position` (`relative` / `absolute` / `fixed` / `sticky`)
- transitions, animations, `transform`
- JavaScript

## Difficulty / time key

| Mark | Meaning |
|---|---|
| ⭐ | ~5–15 min — a drill |
| ⭐⭐ | ~20–45 min — a real mini-build |
| ⭐⭐⭐ | ~1 hr+ — combines several ideas, expect to debug |
| 🧵 | feeds into the Class 8 capstone — keep the file |

---

## The assignments

### Warm-ups
| # | Title | Difficulty |
|---|---|---|
| [01](01-turn-it-on.md) | Turn it on | ⭐ |
| [02](02-justify-content-tour.md) | justify-content tour | ⭐ |
| [03](03-align-items-tour.md) | align-items tour | ⭐ |
| [04](04-axis-flip.md) | Axis flip | ⭐ |
| [05](05-perfect-centring.md) | Perfect centring | ⭐ |
| [06](06-gap-vs-margin.md) | gap vs margin | ⭐ |

### Core
| # | Title | Difficulty |
|---|---|---|
| [07](07-navbar.md) | Navbar | ⭐⭐ 🧵 |
| [08](08-three-card-feature-row.md) | Three-card feature row | ⭐⭐ 🧵 |
| [09](09-media-object.md) | Media object | ⭐⭐ |
| [10](10-button-toolbar-group.md) | Button / toolbar group | ⭐⭐ |
| [11](11-pricing-table.md) | Pricing table | ⭐⭐ 🧵 |
| [12](12-sidebar-layout.md) | Sidebar layout | ⭐⭐ |
| [13](13-contact-form-two-columns.md) | Contact form → two columns | ⭐⭐ 🧵 |

### Challenge
| # | Title | Difficulty |
|---|---|---|
| [14](14-flexbox-puzzles.md) | Flexbox puzzles | ⭐⭐⭐ |
| [15](15-blog-homepage-with-flexbox.md) | Rebuild the blog homepage with Flexbox | ⭐⭐⭐ 🧵 |
| [16](16-card-grid-without-grid.md) | Card grid without Grid | ⭐⭐⭐ |

### Debug & review
| # | Title | Difficulty |
|---|---|---|
| [17](17-debug-flex-not-behaving.md) | Debug: Flex not behaving | ⭐⭐ |
| [18](18-written-questions.md) | Written questions | ⭐ |

---

## Definition of done for Class 4

- [ ] Warm-ups 01–06 complete; you can say, without pausing, which axis `justify-content` acts on in a `row` vs a `column`
- [ ] Core 07, 08, and 13 complete and hitting every checklist item
- [ ] You can build "perfectly centred" (05) and "pinned to the bottom of a card" from memory
- [ ] Debug 17 complete, with the cause of each bug written in your own words
- [ ] Written questions 18 answered without looking
- [ ] No `float`, no CSS Grid, no `position`, and no media queries used anywhere
