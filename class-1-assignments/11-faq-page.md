# Assignment 11 — FAQ Page

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~25 min
**Prereqs:** Class 1 §4 (headings, paragraphs, links)
**Build in:** `work/11-faq-page/index.html`

---

## Goal

Build a "Frequently Asked Questions" page for a made-up small business, using a heading for each question and a paragraph for each answer.

## What you'll practice

- Using `<h2>` as a repeated structural pattern (one per question)
- Pairing each heading with a `<p>` answer
- Keeping a repetitive document consistent and well-indented

## Instructions

1. Invent a small business: a barbershop, a tutoring service, a bakery, a bike-repair shop — your choice.
2. Build `index.html`:
   - `<h1>` — the business name
   - one intro `<p>` — one sentence on what the business does
   - **six** question-and-answer pairs, each as: an `<h2>` holding the question, followed by a `<p>` holding the answer
   - a final `<h2>` `Still need help?` followed by a `<p>` that contains an `<a>` link (to a real site standing in for a contact page)

## Requirements

- [ ] `<h1>` business name + intro `<p>`
- [ ] Exactly 6 `<h2>` questions, each immediately followed by a `<p>` answer
- [ ] A closing `Still need help?` `<h2>` + `<p>` with an `<a>` inside it
- [ ] Questions are phrased as real questions ("Do I need an appointment?")
- [ ] Valid skeleton; consistent structure for every pair; no CSS or non–Class-1 tags

## Acceptance criteria

- The page reads as a genuine FAQ — scannable by question.
- Every `<h2>` has exactly one `<p>` answer under it.
- The link in "Still need help?" works.

## Hints

<details><summary>Show hint</summary>

An `<a>` can sit **inside** a `<p>`: `<p>Email us at <a href="https://example.com">our contact page</a> and we'll reply within a day.</p>`
</details>

## Stretch (optional)

Add one `<h2>` question whose answer uses an `<ol>` (e.g. "How do I book?" → a numbered 3-step process) and one whose answer uses a `<ul>` (e.g. "What services do you offer?").
