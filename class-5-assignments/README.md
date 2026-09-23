# Class 5 Assignments — CSS Grid & Responsive Design

Practice for **Class 5**. Read the lesson first:
[../class-5-css-grid-and-responsive-design.md](../class-5-css-grid-and-responsive-design.md)

---

## How to use this folder

- Do **all warm-ups (01–07)** in order — 01–05 drill Grid, 06–07 drill the responsive basics.
- Work through the **core set (08–14)** — the real builds. Finish at least **08 (photo gallery)** and **13 (responsive About Me + Contact)**; those are the class hands-on and homework. **09** is strongly recommended too — it's the page skeleton your capstone will grow from.
- Do **debug (19)** and pick from **challenge (15–18)** as time allows.
- Answer the **written questions (20)** from memory, in a text file.
- Put your code in `work/<assignment-slug>/` — usually an `index.html` **and** a `style.css`. See [work/README.md](work/README.md).
- **Type everything by hand.** Save both files. Check the browser after every change — and from this class on, check it at **three widths**: 375px, 768px, and 1280px (dev tools device toolbar: `Ctrl+Shift+M`, Mac `Cmd+Shift+M`).

## Scope — only what's been taught

Use only Class 1–5 material.

**In scope this class:**
- `display: grid`, `grid-template-columns`, `grid-template-rows`, `grid-auto-rows`
- The `fr` unit, `repeat()`, `minmax()`, `auto-fit` / `auto-fill`
- `gap` / `row-gap` / `column-gap` (same as Flexbox)
- Placing and spanning: `grid-column`, `grid-row`, line numbers (including `-1`), `span`
- `grid-template-areas` + `grid-area`
- `place-items`, `place-content`
- The viewport meta tag: `<meta name="viewport" content="width=device-width, initial-scale=1">`
- Relative units: `%`, `rem`, `em`, `vw`, `vh`, and `clamp()`
- Flexible images: `max-width: 100%`, `height: auto`, `aspect-ratio`, `object-fit`
- `@media` queries with `min-width` / `max-width`; mobile-first ordering
- Everything from Classes 1–4 (semantic HTML, forms, the box model, colour, typography, Flexbox)

**Not yet — do not use:**
- `position` (`relative` / `absolute` / `fixed` / `sticky`)
- transitions, animations, `transform`
- JavaScript — a "mobile menu" this class is just links stacked in a column, no toggle button
- Other Grid features you may find online (`grid-auto-flow`, named grid lines, `subgrid`) — nothing here needs them

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
| [01](01-first-grid.md) | First grid | ⭐ |
| [02](02-fr-vs-px-vs-auto.md) | fr vs px vs auto | ⭐ |
| [03](03-responsive-grid-no-media-query.md) | Responsive grid, no media query | ⭐ |
| [04](04-spanning.md) | Spanning | ⭐ |
| [05](05-named-areas.md) | Named areas | ⭐ |
| [06](06-media-query-drill.md) | Media query drill | ⭐ |
| [07](07-the-viewport-meta-tag.md) | The viewport meta tag | ⭐ |

### Core
| # | Title | Difficulty |
|---|---|---|
| [08](08-responsive-photo-gallery.md) | Responsive photo gallery | ⭐⭐ 🧵 |
| [09](09-page-layout-with-grid-areas.md) | Page layout with grid-template-areas | ⭐⭐ 🧵 |
| [10](10-dashboard-card-grid.md) | Dashboard card grid | ⭐⭐ |
| [11](11-magazine-bento-layout.md) | Magazine / bento layout | ⭐⭐ |
| [12](12-calendar-month.md) | Calendar month | ⭐⭐ |
| [13](13-responsive-about-me-and-contact.md) | Make About Me + Contact responsive | ⭐⭐ 🧵 |
| [14](14-mobile-first-rebuild.md) | Mobile-first rebuild | ⭐⭐ |

### Challenge
| # | Title | Difficulty |
|---|---|---|
| [15](15-grid-vs-flexbox-choose-and-justify.md) | Grid vs Flexbox: choose and justify | ⭐⭐ |
| [16](16-layout-at-three-breakpoints.md) | Reproduce a layout at three breakpoints | ⭐⭐⭐ 🧵 |
| [17](17-fluid-type-with-clamp.md) | Fluid type with clamp() | ⭐⭐⭐ |
| [18](18-flexbox-to-grid-and-back.md) | Convert Flexbox to Grid (and back) | ⭐⭐⭐ |

### Debug & review
| # | Title | Difficulty |
|---|---|---|
| [19](19-debug-grid-and-responsive.md) | Debug: Grid & responsive bugs | ⭐⭐ |
| [20](20-written-questions.md) | Written questions | ⭐ |

---

## Definition of done for Class 5

- [ ] Warm-ups 01–07 complete; you can type `repeat(auto-fit, minmax(220px, 1fr))` and the viewport tag from memory
- [ ] Core 08 and 13 complete and hitting every checklist item (09 strongly recommended)
- [ ] Every page you built this class checked at 375px, 768px, and 1280px, with no horizontal scrollbar at any of them
- [ ] Your media queries are mobile-first (`min-width`, smallest first) everywhere except Assignment 10, which is desktop-first on purpose
- [ ] Debug 19 complete, with the cause of each bug written in your own words
- [ ] Written questions 20 answered without looking
- [ ] No `position`, no transitions or animations, and no JavaScript used anywhere
