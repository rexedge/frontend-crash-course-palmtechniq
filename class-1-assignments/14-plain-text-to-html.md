# Assignment 14 — Convert Plain Text to HTML

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~35 min
**Prereqs:** Class 1 (all core tags)
**Build in:** `work/14-plain-text-to-html/` — `source.txt` and `index.html`

---

## Goal

Take a real article and mark it up: turn raw text into structured HTML by choosing the right tag for each part.

## What you'll practice

- Reading unstructured text and identifying *what each part is*
- Mapping content to tags: title → `<h1>`, section title → `<h2>`, body → `<p>`, bullets → `<ul>`, steps → `<ol>`, in-text link → `<a>`
- Judgement, not memorisation

## Instructions

1. Find an article, blog post, or how-to guide — **200–400 words**, ideally one with a heading, a couple of sub-headings, and either a bullet list or a numbered list.
2. Save the raw text as `source.txt` in the folder (paste it in as plain text).
3. In `index.html`, mark it up:
   - the article's title → `<h1>`
   - each section sub-title → `<h2>`
   - each body paragraph → its own `<p>`
   - any bulleted points → `<ul>` / `<li>`
   - any numbered steps → `<ol>` / `<li>`
   - any link mentioned in the text → an `<a>` with sensible link text
   - if the article has a lead image you can link to, add one `<img>` with a written `alt`
4. Compare `index.html` in the browser against `source.txt` — same content, now structured.

## Requirements

- [ ] `source.txt` present with the original text
- [ ] Every paragraph is its own `<p>` (not one giant `<p>` with everything in it)
- [ ] Sub-headings use `<h2>`, in order under the `<h1>`
- [ ] At least one list, using the correct type for the content
- [ ] Valid skeleton; all tags closed in order; no CSS or non–Class-1 tags

## Acceptance criteria

- The browser version contains the same words as `source.txt`, with nothing lost.
- Each piece of content sits in the tag that matches what it *is*.
- No run-together paragraphs; no list where prose belongs, or vice versa.

## Hints

<details><summary>Show hint</summary>

Go through `source.txt` line by line and label each line first ("this is the title", "this is a paragraph", "these three lines are a list"). Then write the HTML from your labels.
</details>
