# Assignment 19 — Course Homework: Interactivity on Earlier Pages

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~30 min each · 🧵 keep this file
**Prereqs:** your About Me, photo gallery, and blog homepage from Classes 3–5; Class 7 §7, §9, §11
**Build in:** `work/19-interactivity-on-earlier-pages/` — one folder for each page you work on

---

## Goal

Go back to pages you built weeks ago and make them interactive. The course homework asks for **one** new feature on **one** earlier page. Three are described here — do at least one, and all three if you can.

## What you'll practice

- Adding JavaScript to a page that already exists, without breaking it
- Show and hide, with a button that describes what it will do
- Toggling a class on any one of many elements
- Filtering a list as the user types

## Instructions

Copy each page in first — [work/README.md](work/README.md) lists the folders. Add an `app.js`, and a `<script>` tag at the end of `<body>`.

**A. About Me — "Read more"**

1. Add one more paragraph to your bio, with the class `hidden`. Under it, add `<button type="button" id="read-more">Read more</button>`.
2. On click, toggle `hidden` on the paragraph.
3. Then set the button's text: `Read less` when the paragraph is showing, and `Read more` when it isn't.

**B. Photo gallery — click to enlarge**

1. In the CSS, **inside** your `min-width: 700px` media query, add a `.gallery .big` rule that makes a photo cover 2 columns and 2 rows.
2. In `app.js`, find every photo in the gallery. On click, toggle `big` on the photo that was clicked.
3. Click several photos. The grid rearranges itself around the big ones — that's Grid doing its job.

**C. Blog homepage — filter the posts**

1. Above the posts, add a labelled text input: `Filter posts`.
2. On `input`, read the box, trim it, and make it lower case.
3. Loop over every `<article>`. If its `textContent`, in lower case, includes the keyword, remove `hidden`. Otherwise, add `hidden`.

## Requirements

- [ ] At least one of A, B, or C is finished
- [ ] The original HTML and CSS still work — you only added to them
- [ ] The look of each feature is a class in `style.css`; the JavaScript only switches classes
- [ ] The script is at the end of `<body>`, and there's no red in the Console
- [ ] Each page still works at 375px, 768px, and 1280px

## Acceptance criteria

- **A:** the extra paragraph is hidden on load. The first click shows it, and the button reads `Read less`. The second click hides it, and the button reads `Read more` again.
- **B:** clicking a photo makes it 2 × 2; clicking it again shrinks it. Several photos can be big at once. At 375px there's no horizontal scrollbar, whatever you click.
- **C:** typing a word leaves only the posts that contain it. Capital letters make no difference. Emptying the box brings every post back.

## Hints

<details><summary>Show hint</summary>

- **A** — after the toggle, ask the paragraph which state it's in: `if (moreBio.classList.contains("hidden"))`.
- **B** — why inside the media query? Because a 2-column span on a one-column phone grid forces an extra column, and the page scrolls sideways. You met this in Class 5.
- **C** — lower-case **both** sides before comparing, or `flexbox` won't find `Flexbox`. And you don't need a special case for an empty box: every string includes the empty string, so all the posts show.
</details>

## Stretch (optional)

For **C**: when no post matches, show a paragraph that says `No posts match "…"`, with the keyword in it. Count the matches inside your loop with a `let`, and decide after the loop.
