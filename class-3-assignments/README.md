# Class 3 Assignments — CSS Basics & the Box Model

Practice for **Class 3**. Read the lesson first:
[../class-3-css-basics.md](../class-3-css-basics.md)

---

## How to use this folder

- Do **all warm-ups (01–06)** in order — they're short and build the core reflexes (selectors + the box model).
- Work through the **core set (07–13)** — the real builds. Finish at least **07 (style About Me)** and **08 (style contact form)**; those two are the class hands-on and homework.
- Do **debug (17)** and pick from **challenge (14–16)** as time allows.
- Answer the **written questions (18)** from memory, in a text file.
- Put your code in `work/<assignment-slug>/` — usually an `index.html` **and** a `style.css`. See [work/README.md](work/README.md).
- **Type everything by hand.** Save both files. Check the browser after every change. Keep the dev tools **Elements + Styles** panel open — it shows which rule won and why.

## Scope — only what's been taught

Use only Class 1–3 material.

**In scope this class:**
- External stylesheet linked with `<link rel="stylesheet" href="style.css">`
- Selectors: element, `.class`, `#id`, descendant `A B`, grouping `A, B`, universal `*`
- Box model: `width`, `height`, `padding`, `border`, `margin`, `box-sizing`
- Colours: named, `#hex`, `rgb()` / `rgba()`; `color` and `background-color`
- Typography: `font-family` (with fallbacks), `font-size`, `font-weight`, `line-height`, `text-align`, `letter-spacing`, `text-transform`
- Backgrounds: `background-color`, `background-image`, `background-size`, `background-position`, `background-repeat`
- `display`: `block` / `inline` / `inline-block` / `none`
- Units: `px`, `%`, `em`, `rem`
- Centring a block with `max-width` + `margin: 0 auto`
- (`a:hover` appears in one assignment — a small, flagged extension)

**Not yet — do not use:**
- Flexbox or CSS Grid
- `position` (`relative` / `absolute` / `fixed` / `sticky`)
- `@media` queries / responsive breakpoints — that's Class 5
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
| [01](01-wire-up-a-stylesheet.md) | Wire up a stylesheet | ⭐ |
| [02](02-selector-targeting.md) | Selector targeting | ⭐ |
| [03](03-box-model-by-eye.md) | Box model by eye | ⭐ |
| [04](04-colour-formats.md) | Colour formats | ⭐ |
| [05](05-type-scale.md) | Type scale | ⭐ |
| [06](06-box-sizing-experiment.md) | box-sizing experiment | ⭐ |

### Core
| # | Title | Difficulty |
|---|---|---|
| [07](07-style-the-about-me-page.md) | Style the About Me page | ⭐⭐ 🧵 |
| [08](08-style-the-contact-form.md) | Style the contact form | ⭐⭐ 🧵 |
| [09](09-business-card.md) | Business card (exact spec) | ⭐⭐ |
| [10](10-colour-palette-page.md) | Colour palette page | ⭐⭐ |
| [11](11-typography-specimen.md) | Typography specimen | ⭐⭐ |
| [12](12-re-theme-dont-re-structure.md) | Re-theme, don't re-structure | ⭐⭐ 🧵 |
| [13](13-match-the-mockup.md) | Match the mockup | ⭐⭐ |

### Challenge
| # | Title | Difficulty |
|---|---|---|
| [14](14-box-model-maths.md) | Box-model maths | ⭐⭐ |
| [15](15-style-the-blog-homepage.md) | Style the blog homepage | ⭐⭐⭐ 🧵 |
| [16](16-recreate-a-real-sites-typography.md) | Recreate a real site's typography | ⭐⭐⭐ |

### Debug & review
| # | Title | Difficulty |
|---|---|---|
| [17](17-debug-css-that-isnt-working.md) | Debug: CSS that isn't working | ⭐⭐ |
| [18](18-written-questions.md) | Written questions | ⭐ |

---

## Definition of done for Class 3

- [ ] Warm-ups 01–06 complete; you can write a `.class`, `#id`, and `A B` selector without thinking
- [ ] Core 07 and 08 complete and hitting every checklist item
- [ ] You can do the box-model maths in 14 on paper and predict the on-screen width
- [ ] Debug 17 complete, with the cause of each bug written in your own words
- [ ] Written questions 18 answered without looking
- [ ] Every build uses an **external** `style.css` — no `style=""` attributes, no `<style>` blocks
- [ ] No Flexbox, Grid, `position`, or media queries used anywhere
