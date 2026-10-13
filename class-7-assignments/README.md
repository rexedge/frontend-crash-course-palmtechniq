# Class 7 Assignments — JavaScript & the DOM

Practice for **Class 7**. Read the lesson first:
[../class-7-javascript-and-the-dom.md](../class-7-javascript-and-the-dom.md)

---

## How to use this folder

- Do **all warm-ups (01–07)** in order — each one drills a single step: find, change, listen.
- Work through the **core set (08–19)** — the real builds. Finish at least **09 (light / dark toggle)**, **10 (contact form "thank you")**, and **19 (interactivity on earlier pages)**: 09 and 10 are the class hands-on, and 19 is the course homework. **13 (to-do list)** is strongly recommended too — it uses nearly everything in the class.
- Do **debug (24)** and pick from **challenge (20–23)** as time allows.
- Answer the **written questions (25)** from memory, in a text file.
- Put your code in `work/<assignment-slug>/` — an `index.html`, a `style.css`, and an `app.js`. See [work/README.md](work/README.md) for the starter page.
- **Type everything by hand.** Save all three files. After every change, check the page **and** the Console — when something doesn't work in this class, the page usually just does nothing, and the reason is in the Console.

## Scope — only what's been taught

Use only Class 1–7 material.

**In scope this class:**
- The DOM, `document`, and `document.body`
- `<script>` at the end of `<body>`, or in the `<head>` with `defer`
- `document.querySelector` and `document.querySelectorAll`, with the selectors from Class 3
- `.textContent`; `.innerHTML` for HTML you wrote yourself, and `innerHTML = ""` to empty an element
- `.classList.add` / `.remove` / `.toggle` / `.contains`, and a `.hidden { display: none; }` class
- `.style.property` in camelCase, for values worked out by the code
- `.getAttribute` and `.setAttribute`
- Form controls: `.value` (always a string), `.checked`, `.disabled`, and `.trim()` on what people type
- `addEventListener` with `click`, `input`, `change`, `submit`, and `keyup`
- The `event` object: `event.target`, `event.key`, `event.preventDefault()`
- Passing a function to `addEventListener` — by name, or as an arrow function `() => { ... }`
- `.forEach` on a list of elements or an array, with the item and (optionally) its index
- `document.createElement`, `.append`, `.remove`
- Objects: `{ title: "…", year: 2020 }`, reading properties with a dot, and arrays of objects
- Everything from Classes 1–6

**Not yet — do not use:**
- `fetch`, APIs, or loading data from anywhere else
- `localStorage` — nothing is saved between page loads in this class
- Timers (`setTimeout`, `setInterval`) and animation
- Moving around the tree with `parentElement`, `children`, `nextElementSibling`, or `closest` — use an `id`, a class, or the index from `forEach`
- `dataset`, and array methods such as `.map`, `.filter`, `.find`, `.sort`
- Inline handlers in the HTML (`onclick="…"`) — all JavaScript stays in `app.js`
- `innerHTML` with anything a user typed
- CSS `position`, transitions, and animations
- jQuery, or any other library or framework

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
| [01](01-select-and-log.md) | Select and log | ⭐ |
| [02](02-change-text-on-click.md) | Change text on click | ⭐ |
| [03](03-toggle-a-class.md) | Toggle a class | ⭐ |
| [04](04-read-an-input.md) | Read an input | ⭐ |
| [05](05-input-event.md) | input event | ⭐ |
| [06](06-queryselectorall-loop.md) | querySelectorAll loop | ⭐ |
| [07](07-preventdefault.md) | preventDefault | ⭐ |

### Core
| # | Title | Difficulty |
|---|---|---|
| [08](08-counter.md) | Counter | ⭐⭐ |
| [09](09-light-dark-mode-toggle.md) | Light / dark mode toggle | ⭐⭐ 🧵 |
| [10](10-contact-form-thank-you.md) | Contact form "Thank you" | ⭐⭐ 🧵 |
| [11](11-live-character-counter.md) | Live character counter | ⭐⭐ |
| [12](12-show-hide-accordion.md) | Show / hide (accordion) | ⭐⭐ 🧵 |
| [13](13-to-do-list.md) | To-do list | ⭐⭐ 🧵 |
| [14](14-tab-switcher.md) | Tab switcher | ⭐⭐ |
| [15](15-image-gallery.md) | Image gallery | ⭐⭐ 🧵 |
| [16](16-live-form-validation.md) | Live form validation | ⭐⭐ |
| [17](17-colour-changer.md) | Colour changer | ⭐⭐ |
| [18](18-temperature-converter-ui.md) | Temperature converter UI | ⭐⭐ 🧵 |
| [19](19-interactivity-on-earlier-pages.md) | Course homework: interactivity on earlier pages | ⭐⭐ 🧵 |

### Challenge
| # | Title | Difficulty |
|---|---|---|
| [20](20-quiz-app.md) | Quiz app | ⭐⭐⭐ |
| [21](21-mini-shopping-cart.md) | Mini shopping cart | ⭐⭐⭐ |
| [22](22-build-the-dom-from-data.md) | Build the DOM from data | ⭐⭐⭐ |
| [23](23-rebuild-a-component.md) | Rebuild a component you've used | ⭐⭐⭐ |

### Debug & review
| # | Title | Difficulty |
|---|---|---|
| [24](24-debug-dom-bugs.md) | Debug: DOM bugs | ⭐⭐ |
| [25](25-written-questions.md) | Written questions | ⭐ |

---

## Definition of done for Class 7

- [ ] Warm-ups 01–07 complete; you can type `querySelector` + `addEventListener("click", …)` that changes some text, from memory
- [ ] Core 09, 10, and 19 complete and hitting every checklist item (13 strongly recommended)
- [ ] Every page you built this class runs with **no red in the Console**
- [ ] The look of every feature lives in `style.css` as a class; your JavaScript switches classes instead of setting colours
- [ ] Anything a user typed reaches the page through `textContent`, never `innerHTML`
- [ ] Debug 24 complete, with the cause of each bug written in your own words
- [ ] Written questions 25 answered without looking
- [ ] No `fetch`, no `localStorage`, no timers, no inline `onclick`, and no libraries used anywhere
