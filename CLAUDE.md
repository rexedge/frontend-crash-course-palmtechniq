# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

Authoring materials for the **Frontend Development Crash Course — PalmTechnIQ**: an 8-class,
beginner-level (no prior coding) HTML/CSS/JS course. It is a **Markdown content repository** —
there is no application, no build system, no dependencies, and no test suite. Work here means
writing and editing course prose, not shipping code. It is a public git repo
(`rexedge/frontend-crash-course-palmtechniq` on GitHub); content is licensed CC BY 4.0. The root
`README.md` is the public landing page; `frontend-crash-course-palmtechniq.md` remains the
detailed syllabus and source of truth.

## Verifying example code

There are no build/lint/test commands. Snippets and student deliverables are plain
`.html` / `.css` / `.js` with **no framework, bundler, or package manager** — this is a
deliberate course constraint, not a gap. Example code is meant to be opened in VS Code with the
**Live Server** extension (right-click `index.html` → "Open with Live Server"). When adding a
code sample, hand-verify it renders correctly that way.

For JavaScript (Class 6 on), every quoted Console output, expected return value, and error
message must come from actually running the code. Pure-logic samples can be checked with
`node file.js` — a verification convenience only, never a course dependency — but anything
browser-specific (`<script>` loading, the DOM, events) must be confirmed in a real browser.
Responsive layouts are checked at real phone widths (320px and 375px) as well as tablet and
desktop, in both themes where a page has a dark mode; "no horizontal scrollbar" means the page
is no wider than the visible width at 320px.

## The four document types and how they relate

1. **`frontend-crash-course-palmtechniq.md`** — the master syllabus. Source of truth for what
   each class covers, its hands-on exercise, and its homework. Every other file must stay
   consistent with this outline.
2. **`class-<n>-<topic>.md`** — self-guided lesson read-throughs (all 8 written). Fixed internal
   format: numbered sections split by `---`, "Practice Now" + "✅ Checkpoint" callouts, a
   Troubleshooting table, a "Self-Check" question list, a "Homework" section, a "What's Next"
   section. Class 8 keeps that format, but its body is one guided build in five milestones, each
   with a "Test it" table, and its stylesheet and script are built up in three parts that are
   appended in order.
3. **`assignments.md`** — the single-file assignment bank covering all 8 classes. Difficulty key
   (⭐ / ⭐⭐ / ⭐⭐⭐), 🧵 = "portfolio thread" (feeds the Class 8 capstone). Each class section is
   grouped Warm-up / Core / Challenge / Debug-it / Written questions. Class 8 is the exception:
   core brief / milestones / variant briefs / stretch goals / Debug-it / peer-review rubric /
   wrap-up reflection.
4. **`class-<n>-assignments/`** — the per-class breakout of the same assignments (all 8 done).
   Contains `README.md` (index + scope list + done-checklist), individual briefs `01`–`19`, and
   `work/README.md`. **The `class-<n>-assignments/` folder and the Class `<n>` section of
   `assignments.md` are two views of the same content — edit both when either changes.**

## Scope discipline (the most important rule)

Each class's lesson and assignments may use **only concepts taught up to and including that
class**. Every lesson and every assignments `README.md` carries an explicit "In scope" / "Not
yet" list — respect it. If a concept isn't taught yet, don't use it, or mark it `*(stretch)*`.

Progression: **C1** HTML basics (`html/head/body`, headings, `p`, `a`, `img`, `ul/ol/li`,
nesting — no CSS, no `class`/`id`, no `div`/`span`, no semantic tags, no forms) →
**C2** semantic structure + tables + forms/validation (still no CSS) →
**C3** CSS basics (external stylesheet, selectors, box model, colour, typography, `display` —
no Flexbox/Grid/media queries/position/animation) →
**C4** Flexbox (`display: flex`, `flex-direction`, main/cross axis, `justify-content`,
`align-items`/`align-self`, `flex-wrap`, `gap`, `flex-grow`/`shrink`/`basis`, `order` — no Grid,
media queries, or `position`) → **C5** Grid (`grid-template-columns/rows`, `grid-auto-rows`, `fr`,
`repeat()`, `minmax()`, `auto-fit`/`auto-fill`, line-number/`span` placement, `grid-template-areas`,
`place-items`) + responsive (viewport meta, `%`/`rem`/`em`/`vw`/`vh`/`clamp()`, `max-width: 100%`
images, `aspect-ratio`, `object-fit`, `@media` `min-width`/`max-width`, mobile-first — no `position`,
transitions/`transform`, or JS) → **C6** JS basics, logic only, run in the Console
(`<script src>` at the end of `<body>`, `console.log`, reading Console errors, `let`/`const`,
string/number/boolean/`null`/`undefined`, `typeof`, template literals, arithmetic incl. `%`/`**`,
`+=`/`++`, `Number()`/`NaN`, `===`/`!==`/`>`/`<`/`>=`/`<=`, `&&`/`||`/`!`, function declarations
with `return`, `if`/`else if`/`else`, ternary, `for`/`while`, arrays with index/`.length`/`.push`,
strings with index/`.length`/`.toUpperCase`/`.toLowerCase`/`.includes`/`.slice`,
`Math.round`/`floor`/`max`/`random`/`PI` — no DOM, events, `prompt`/`alert`, objects, arrow
functions, array methods beyond `.push`, `.split`/`.join`, or `var`) →
**C7** DOM + events (`document`/`document.body`, `querySelector`/`querySelectorAll`, `textContent`,
`innerHTML` for self-written HTML only, `classList` + a `.hidden` class, `.style` in camelCase,
`getAttribute`/`setAttribute`, `.value`/`.checked`/`.disabled`, `.trim()`, `addEventListener` for
`click`/`input`/`change`/`submit`/`keyup`, `event.target`/`event.key`/`event.preventDefault()`,
handlers passed by name or as block-body arrow functions, `.forEach` with item and index,
`createElement`/`append`/`remove`, object literals and arrays of objects, `defer` — no `fetch`,
`localStorage`, timers, DOM traversal such as `parentElement`/`closest`, `dataset`,
`.map`/`.filter`/`.sort`, inline `onclick`, or libraries; and still no CSS `position`, transitions,
`:hover`, compound selectors like `.tab.active`, or CSS variables, none of which any lesson teaches) →
**C8** capstone portfolio: adds only in-page links (`<a href="#contact">` → `id="contact"`);
everything else is C1–C7 combined on one page. The course ends without ever teaching CSS
`position`, transitions/animations, `:hover`, CSS variables, `border-radius`/`box-shadow`, the
two-value `gap` shorthand, `localStorage`, timers, scroll events, the clipboard, or `fetch` — so
Class 8 material must not rely on them (no sticky headers, pop-up lightboxes, scroll-triggered
buttons, typing animations, or a remembered theme) except as a `*(stretch)*` that says it reaches
beyond the course. `list-style: none` appears only in assignments (Classes 3 and 5), so a lesson
that uses it says what it does.

## Conventions

- **Naming:** lessons `class-<n>-<kebab-topic>.md`; assignment folders `class-<n>-assignments/`;
  briefs `<NN>-<kebab-slug>.md` with zero-padded `NN` (~01–07 warm-ups, 08–14 core, 15–17
  challenge, 18 debug, 19 written questions). `NN` mirrors the bank's `<n>.<NN>` numbering, so the
  counts vary per class (Classes 3–4 end at 18; Class 5 has four challenges and ends at 20;
  Class 6 has ten warm-ups and nine core briefs and ends at 24; Class 7 has twelve core and four
  challenge briefs and ends at 25; Class 8 is `01` the core brief, `02`–`06` variants, `07`–`11`
  stretch goals, `12` debug, `13` peer review, `14` wrap-up reflection).
- **Brief template:** `Type` / `Difficulty` / `Time` / `Prereqs` / `Build in` header, then Goal,
  "What you'll practice", Instructions, a `- [ ]` Requirements checklist, Acceptance criteria,
  a `<details><summary>Show hint</summary>` Hint, optional Stretch.
- **Debug exercises** hide answers in `<details><summary>Show answer</summary>…</details>`.
- **Student code** goes under `class-<n>-assignments/work/<assignment-slug>/index.html` (the
  `work/` dirs currently hold only a `README.md`). Class 6 work is `index.html` + `app.js`, with
  no stylesheet; all output goes to the Console. Class 7 work is `index.html` + `style.css` +
  `app.js`. The Class 8 portfolio adds `images/` and a `projects/` folder holding copies of the
  student's earlier builds, so the site is self-contained.
- **The running example persona** is "Ada Lovelace" (the Class 1 About Me page, the Class 7 test
  table, the Class 8 portfolio). Example prices use `$`.
- **JS style in samples:** `const` by default; arrow functions always with braces; elements found
  once at the top of the file by `id`; looks changed by toggling classes, not `.style`; user text
  written with `textContent`.
- **Code-sample indentation:** 4 spaces in lessons and briefs; the bank's compact snippets use 2.
- **Cross-links** use relative Markdown paths (lessons → `assignments.md`; briefs →
  `../class-<n>-<topic>.md` and sibling briefs).
- **Placeholder images:** `https://picsum.photos/<w>/<h>`.
- **Prose:** second person, plain language, short sentences, encouraging tone for absolute
  beginners; keep the recurring "type it by hand, don't paste" and "save often, check the
  browser" refrains.

## Current state

The course content is complete: lessons and assignment breakout folders exist for all 8 classes,
and `assignments.md` covers all 8. Work from here is revision. When changing a class, keep its
lesson, its section of `assignments.md`, and its folder in step, and re-run any code you touch.
If a class is ever added or renamed, also update the status lines in `README.md` and the
"8 classes" table there.
