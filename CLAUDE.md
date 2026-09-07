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

## The four document types and how they relate

1. **`frontend-crash-course-palmtechniq.md`** — the master syllabus. Source of truth for what
   each class covers, its hands-on exercise, and its homework. Every other file must stay
   consistent with this outline.
2. **`class-<n>-<topic>.md`** — self-guided lesson read-throughs (Classes 1–3 written; 4–8 not
   yet). Fixed internal format: numbered sections split by `---`, "Practice Now" + "✅ Checkpoint"
   callouts, a Troubleshooting table, a "Self-Check" question list, a "Homework" section, a
   "What's Next" section.
3. **`assignments.md`** — the single-file assignment bank covering all 8 classes. Difficulty key
   (⭐ / ⭐⭐ / ⭐⭐⭐), 🧵 = "portfolio thread" (feeds the Class 8 capstone). Each class section is
   grouped Warm-up / Core / Challenge / Debug-it / Written questions.
4. **`class-<n>-assignments/`** — the per-class breakout of the same assignments (Classes 1–2
   done). Contains `README.md` (index + scope list + done-checklist), individual briefs
   `01`–`19`, and `work/README.md`. **The `class-<n>-assignments/` folder and the Class `<n>`
   section of `assignments.md` are two views of the same content — edit both when either
   changes.**

## Scope discipline (the most important rule)

Each class's lesson and assignments may use **only concepts taught up to and including that
class**. Every lesson and every assignments `README.md` carries an explicit "In scope" / "Not
yet" list — respect it. If a concept isn't taught yet, don't use it, or mark it `*(stretch)*`.

Progression: **C1** HTML basics (`html/head/body`, headings, `p`, `a`, `img`, `ul/ol/li`,
nesting — no CSS, no `class`/`id`, no `div`/`span`, no semantic tags, no forms) →
**C2** semantic structure + tables + forms/validation (still no CSS) →
**C3** CSS basics (external stylesheet, selectors, box model, colour, typography, `display` —
no Flexbox/Grid/media queries/position/animation) →
**C4** Flexbox → **C5** Grid + responsive/media queries → **C6** JS basics (logic only, run in
the Console — no DOM) → **C7** DOM + events → **C8** capstone portfolio.

## Conventions

- **Naming:** lessons `class-<n>-<kebab-topic>.md`; assignment folders `class-<n>-assignments/`;
  briefs `<NN>-<kebab-slug>.md` with zero-padded `NN` (~01–07 warm-ups, 08–14 core, 15–17
  challenge, 18 debug, 19 written questions).
- **Brief template:** `Type` / `Difficulty` / `Time` / `Prereqs` / `Build in` header, then Goal,
  "What you'll practice", Instructions, a `- [ ]` Requirements checklist, Acceptance criteria,
  a `<details><summary>Show hint</summary>` Hint, optional Stretch.
- **Debug exercises** hide answers in `<details><summary>Show answer</summary>…</details>`.
- **Student code** goes under `class-<n>-assignments/work/<assignment-slug>/index.html` (the
  `work/` dirs currently hold only a `README.md`).
- **Cross-links** use relative Markdown paths (lessons → `assignments.md`; briefs →
  `../class-<n>-<topic>.md` and sibling briefs).
- **Placeholder images:** `https://picsum.photos/<w>/<h>`.
- **Prose:** second person, plain language, short sentences, encouraging tone for absolute
  beginners; keep the recurring "type it by hand, don't paste" and "save often, check the
  browser" refrains.

## Current state

Lessons exist for Classes 1–3. Assignment breakout folders exist for Classes 1–2.
`assignments.md` covers all 8. Not yet written: Class 4–8 lessons, Class 3–8 assignment folders.
When adding a class, also update the status lines in `README.md` and the "8 classes" table there.
