# Frontend Crash Course — Assignment Bank

A large pool of practice for every class. You are **not** expected to do all of it.
Do the **Core** set for each class, then pick from **Challenge** and **Debug** as time allows.
Repetition is the point — redoing a "Core" assignment from a blank file next week is good practice, not wasted time.

---

## How to use this document

1. **One folder per class.** Suggested structure:

   ```
   frontend-crash-course/
     class-1/
       about-me/
         index.html
       recipe/
         index.html
       ...
     class-2/
       ...
   ```

2. **Type everything by hand.** Copy-pasting code skips the part where your fingers and brain learn the shapes.
3. **Save often, check the browser after every change.** Bugs are cheap to find when you only changed one line.
4. **Only use what has been taught up to and including that class.** Each class lists exactly what is "in scope." Reaching ahead is allowed only where an assignment says *(stretch)*.
5. **Difficulty / time key:**
   - ⭐ ~5–15 min — a drill, do several in one sitting
   - ⭐⭐ ~20–45 min — a real mini-build
   - ⭐⭐⭐ ~1 hr+ — combines several ideas, expect to get stuck and debug

6. **The 🧵 "portfolio thread" marker** means the assignment feeds into your Class 8 capstone. Keep those files.
7. **Debug exercises** have answers hidden behind a *Show answer* toggle. Try to fix it before opening.

---

## Table of contents

- [Class 1 — HTML Basics](#class-1--html-basics)
- [Class 2 — Semantic HTML & Forms](#class-2--semantic-html--forms)
- [Class 3 — CSS Basics & the Box Model](#class-3--css-basics--the-box-model)
- [Class 4 — CSS Layout: Flexbox](#class-4--css-layout-flexbox)
- [Class 5 — CSS Grid & Responsive Design](#class-5--css-grid--responsive-design)
- [Class 6 — JavaScript Basics](#class-6--javascript-basics)
- [Class 7 — JavaScript & the DOM](#class-7--javascript--the-dom)
- [Class 8 — Capstone: Portfolio Project](#class-8--capstone-portfolio-project)
- [Spaced-review sets](#spaced-review-sets)

---
---

# Class 1 — HTML Basics

**In scope:** `<!DOCTYPE html>`, `html`, `head`, `title`, `body`, `h1`–`h6`, `p`, `a` (with `href`), `img` (with `src`, `alt`), `ul`, `ol`, `li`, nesting, indentation.
**Out of scope (do not use yet):** CSS, `class`/`id`, `div`, `span`, `br`, `strong`/`em`, semantic tags, forms.

### Warm-up drills

**1.1 — Skeleton from memory** ⭐
Close the notes. In a blank `index.html`, type the full HTML skeleton (`<!DOCTYPE html>` down to `</html>`) from memory. Open with Live Server. Repeat 3 times in 3 separate files. By the third time you should not need to look.

**1.2 — Heading ladder** ⭐
Create a page that uses `<h1>` through `<h6>` once each, in order, each one saying what level it is ("This is heading level 3"). Confirm in the browser they get visually smaller.

**1.3 — Ten paragraphs** ⭐
Write a page with an `<h1>` title "My Day" and 10 `<p>` elements, one sentence each, describing your day in order. No lists.

**1.4 — Link sampler** ⭐
A page titled "Sites I Use" with a `<p>` intro and 8 separate `<a>` links to 8 real websites. Each link's text must describe the destination ("The Wikipedia homepage"), never "click here".

**1.5 — Image sampler** ⭐
A page with 5 `<img>` elements using `https://picsum.photos/300/200` style placeholder URLs (or any real image URLs). Every image needs a **written, specific** `alt` describing what the image shows. Under each image, a `<p>` caption.

**1.6 — List triple** ⭐
One page containing: an unordered list of 5 foods, an ordered list of your 5-step morning routine, and an ordered list counting down your top 3 movies. Each list gets its own `<h2>`.

**1.7 — Nesting by hand** ⭐
Reproduce this outline as nested `<ul>`/`<li>` (a list inside a list inside a list). Indent every level.

```
Africa
  Nigeria
    Lagos
    Abuja
  Kenya
    Nairobi
Europe
  France
    Paris
```

### Core assignments

**1.8 — About Me page** ⭐⭐ 🧵
The Class 1 baseline. In `class-1/about-me/index.html`, build a page about yourself using only in-scope tags. Must contain:
- [ ] `<title>` with your name
- [ ] one `<h1>` — your name
- [ ] one intro `<p>` (2–3 sentences)
- [ ] `<h2>` "Things I Like" + `<ul>` with ≥ 3 `<li>`
- [ ] `<h2>` "My Goals" + `<ol>` with ≥ 3 `<li>` in priority order
- [ ] `<h2>` "A Link" + one `<a>` to a site you like
- [ ] one `<img>` with a real `src` and a written `alt`
- [ ] correct nesting and indentation throughout

**1.9 — Recipe page** ⭐⭐
Pick a dish you can actually cook. Build `class-1/recipe/index.html`:
- [ ] `<h1>` dish name
- [ ] `<p>` one or two sentences about the dish
- [ ] `<h2>` "Ingredients" + `<ul>` (list every ingredient with rough amounts as plain text, e.g. "2 cups rice")
- [ ] `<h2>` "Steps" + `<ol>` (order matters — that's why it's `<ol>`)
- [ ] `<h2>` "Source" + `<a>` to a recipe site
- [ ] one `<img>` of the finished dish with `alt`

**1.10 — Study notes page** ⭐⭐
Turn the Class 1 lesson itself into your own notes page: `<h1>` "HTML Basics — My Notes", then `<h2>` per topic (What is HTML, The Skeleton, Headings, Paragraphs, Links, Images, Lists, Nesting), each with a `<p>` explanation in your own words and a `<ul>` of key points. This doubles as revision.

**1.11 — FAQ page** ⭐⭐
Build a "Frequently Asked Questions" page for a made-up small business (a barbershop, a tutoring service, whatever). One `<h1>`, then for each of 6 questions: an `<h2>` with the question and a `<p>` with the answer. End with an `<h2>` "Still need help?" and an `<a>` link.

**1.12 — Photo journal** ⭐⭐
A page titled "Five Things I Saw This Week". Five entries, each: `<h2>` short title, one `<img>` with `alt`, one `<p>` describing it. Consistent order every time.

**1.13 — Document outline** ⭐⭐
Choose a topic you know well. Produce a page that is *only* headings and short paragraphs: `<h1>` topic, then at least three `<h2>` sections, each with at least two `<h3>` sub-sections, each `<h3>` followed by a 1–2 sentence `<p>`. No lists, no images. The goal is practising a clean, ordered heading hierarchy.

**1.14 — Convert plain text to HTML** ⭐⭐
Take any article or blog post (200–400 words). Save the raw text, then mark it up: the title becomes `<h1>`, section titles become `<h2>`, body becomes `<p>` elements, any bullet points become `<ul>`, any numbered steps become `<ol>`, any links in the text become `<a>`.

### Challenge assignments

**1.15 — Three-page mini-site** ⭐⭐⭐ 🧵
Make a folder `class-1/mini-site/` with three files: `index.html`, `hobbies.html`, `contact.html`.
- Each page has its own `<h1>` and content built from in-scope tags.
- At the top of **every** page, put the same set of 3 links pointing at the other pages, e.g. `<a href="hobbies.html">Hobbies</a>`. (A link to a file in the same folder just uses the file name — no `http`.)
- You should be able to click around all three pages in the browser without touching the address bar.

**1.16 — "Rebuild it blind"** ⭐⭐⭐
Look at your finished About Me page (1.8) in the browser for 60 seconds. Close the file. In a brand-new file, rebuild it from memory. Then diff the two. Whatever you got wrong is your weak spot — note it.

**1.17 — Reference sheet** ⭐⭐
Build `class-1/cheatsheet/index.html`: a single page listing every tag you learned this class. For each tag: `<h3>` with the tag name, a `<p>` saying what it's for, and a `<p>` with an example written out in words (since you can't show raw tags without more HTML, just describe: "opening angle bracket, p, closing angle bracket…"). Keep this and extend it every class.

### Debug-it

**1.18 — Fix five broken snippets** ⭐⭐
Each snippet below has one or more bugs. Put each in a file, find the bug in the browser + by reading, fix it.

**(a)**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Broken One
</head>
<body>
  <h1>Hello</h1>
</body>
</html>
```

**(b)**
```html
<body>
  <h1>My List</h1>
  <ul>
    <li>One</li>
    <li>Two
    <li>Three</li>
  </ul>
</body>
```

**(c)**
```html
<body>
  <h1>Visit my favourite site</h1>
  <a href=https://example.com>Example</a>
  <img src="https://picsum.photos/200">
</body>
```

**(d)**
```html
<html>
<body>
  <h1>Photos</h1>
  <p>Here are my photos.
  <ol>
    <li>Beach trip</li>
    <li>Mountain hike</li>
  </ul>
</body>
</html>
```

**(e)**
```html
<!DOCTYPE html>
<html>
<body>
  <title>About Me</title>
  <h1>About Me</h2>
  <p>I like <a href="">links</a> that go nowhere.</p>
</body>
</html>
```

<details>
<summary>Show answers</summary>

- **(a)** `<title>` is never closed. Add `</title>`.
- **(b)** The second `<li>Two` is never closed. Add `</li>`.
- **(c)** Two issues: `href` value should be quoted (`href="https://example.com"`) — browsers often tolerate it but always quote attribute values; and the `<img>` has no `alt` — add one.
- **(d)** Two issues: the `<p>Here are my photos.` is not closed; and the list opens with `<ol>` but closes with `</ul>` — make both `<ol>`/`</ol>` (or both `ul`).
- **(e)** Three issues: `<title>` is inside `<body>` — move it into `<head>` (and add a `<head>`); `<h1>` is closed with `</h2>` — fix to `</h1>`; the `<a href="">` has an empty destination — give it a real URL.
</details>

**1.19 — Wrong-order nesting** ⭐
Fix this so tags close in the reverse order they opened:
```html
<ul>
  <li><a href="https://example.com">Example</li></a>
</ul>
```
<details><summary>Show answer</summary>The `</li>` and `</a>` are swapped. Correct: `<li><a href="https://example.com">Example</a></li>`.</details>

### Written questions

Answer in your own words, in a text file, without scrolling back to the notes.

1. What are the three languages of the web and what is each responsible for?
2. What is the difference between what goes in `<head>` and what goes in `<body>`?
3. When should you use `<ol>` instead of `<ul>`? Give a real example of each.
4. What is an *attribute*? Name two attributes and the tag each belongs to.
5. Why must every `<img>` have an `alt`? Name two different situations where `alt` matters.
6. What does "nesting" mean, and what is the rule about the order you close nested tags?
7. Why is `index.html` a special file name?
8. Indentation does not change how the browser renders the page. So why do it?

---
---

# Class 2 — Semantic HTML & Forms

**In scope (adds to Class 1):** `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`, `figure`/`figcaption`, `table`/`thead`/`tbody`/`tr`/`th`/`td` (with `scope`), `form`, `label` (with `for`), `input` (types: `text`, `email`, `password`, `number`, `tel`, `url`, `date`, `checkbox`, `radio`, `submit`), `textarea`, `button`, `select`/`option`, `fieldset`/`legend`, validation attributes: `required`, `placeholder`, `minlength`, `maxlength`, `min`, `max`, `pattern`, `name`, `id`.
**Still out of scope:** all CSS, `class` for styling (you may use `id` where a form field needs it).

### Warm-up drills

**2.1 — Landmark skeleton** ⭐
Type, from memory, a page whose `<body>` contains exactly: `<header>`, `<nav>`, `<main>`, `<footer>` — in that order, each with one line of placeholder text. Do it 3 times in 3 files.

**2.2 — Section vs article** ⭐
One page: a `<main>` with two `<article>` elements (two separate blog-post-like chunks), each containing its own `<h2>` and `<p>`. Then one `<section>` titled "About this blog" with an `<h2>` and `<p>`. Write a one-line comment-free `<p>` at the bottom explaining, in plain text, why you put each thing in `article` vs `section`.

**2.3 — Label pairs** ⭐
Type 8 `label` + `input` pairs, each correctly linked with `for`/`id`: full name, email, password, age, birthday, phone, website, "subscribe" checkbox. No `<form>` wrapper needed yet — just the pairs.

**2.4 — Input type tour** ⭐
One page, one field per input type in scope (`text`, `email`, `password`, `number`, `tel`, `url`, `date`, `checkbox`, `radio` ×2 as a group, plus a `submit` button). Every field has a `<label>`. Submit and watch what the browser does with each type.

**2.5 — Tiny table** ⭐
Build a 3-column, 4-row table (`Day | Subject | Room`) with a proper `<thead>` (using `<th scope="col">`) and `<tbody>`. Fill it with your real or imagined class timetable for one day.

**2.6 — Validation attribute drill** ⭐
Make one text input that is `required`, `minlength="3"`, `maxlength="12"`; one number input with `min="1" max="10"`; one input with `pattern="[0-9]{11}"` and a `placeholder`. Submit with bad values and read every browser error message.

### Core assignments

**2.7 — Semantic rewrite of About Me** ⭐⭐ 🧵
Copy your Class 1 About Me into `class-2/about-me/index.html`, then restructure it with landmarks: `<header>` (name + one-line tagline), `<nav>` (even if links just point to `#`), `<main>` containing `<section>` blocks for "About", "Things I Like", "Goals", `<footer>` (a line and a link). Content stays the same; the *structure* becomes meaningful.

**2.8 — Blog homepage** ⭐⭐ 🧵
`class-2/blog/index.html`: a fake blog front page.
- [ ] `<header>` with blog title + `<nav>` of 4 links
- [ ] `<main>` with **three** `<article>` previews, each: `<h2>` post title, `<p>` date line, `<p>` 2–3 sentence excerpt, `<a>` "Read more"
- [ ] an `<aside>` with `<h2>` "About the author" and a short `<p>`
- [ ] `<footer>` with a copyright line and 2 links

**2.9 — News / long-form article page** ⭐⭐
`class-2/article/index.html`: a single article laid out properly.
- [ ] `<header>` (site name + `<nav>`)
- [ ] `<main>` → one `<article>` with `<h1>` headline, a `<p>` byline/date, several `<h2>` sub-sections with `<p>` bodies, at least one `<figure>` with `<img>` + `<figcaption>`
- [ ] `<aside>` "Related stories" with a `<ul>` of links
- [ ] `<footer>`

**2.10 — Data table: price/spec comparison** ⭐⭐
Build a table comparing 3 products across 5 attributes. Use `<th scope="col">` for the product names across the top **and** `<th scope="row">` for the attribute names down the side. Above it, an `<h2>`; below it, a `<p>` note on *when a table is the right choice and when it is not*.

**2.11 — Contact form** ⭐⭐ 🧵
`class-2/contact/index.html`. A working `<form>` (it doesn't need to send anywhere — no `action` is fine):
- [ ] wrapped in `<main>` with a `<header>`/`<footer>` around it
- [ ] fields: full name (`text`, `required`), email (`email`, `required`), subject (`text`), message (`textarea`, `required`, `minlength="10"`)
- [ ] every field has a `<label for>` correctly linked
- [ ] a "Send" `<button type="submit">`
- [ ] a "consent" `checkbox` that is `required`
- [ ] submitting with empty required fields must trigger the browser's built-in validation

**2.12 — Job application form** ⭐⭐
One `<form>` grouped with `<fieldset>`/`<legend>` into: "Personal details", "Experience", "Availability".
- Personal: name, email, phone (`tel` + `pattern`), portfolio URL (`url`)
- Experience: years of experience (`number`, `min="0" max="50"`), a `<select>` for "highest role held", a `<textarea>` "describe a project"
- Availability: a `date` for "earliest start", radio group for "full-time / part-time / contract", checkboxes for days available
- A submit button.

**2.13 — Survey form** ⭐⭐
A feedback survey: one `<textarea>`, one `<select>` (dropdown), one radio group (1–5 rating), a checkbox group ("which features do you use"), an optional email field. Use a `<fieldset>` around each group with a `<legend>`.

**2.14 — Event registration form with real validation rules** ⭐⭐
"Register for the workshop":
- name — `required`, `minlength="2"`
- email — `required`, type `email`
- number of guests — `number`, `min="1"`, `max="4"`, `required`
- t-shirt size — `<select>` with a disabled placeholder option selected by default
- dietary notes — `textarea`, `maxlength="200"`
- phone — `pattern` for an 11-digit number, with a `placeholder` showing the format
- "I agree to the code of conduct" — `checkbox`, `required`
Test every rule by trying to break it.

### Challenge assignments

**2.15 — Rebuild the mini-site, semantically** ⭐⭐⭐ 🧵
Take your Class 1 three-page mini-site and rebuild all three pages in `class-2/mini-site/` with a shared `<header>` + `<nav>` structure, a `<main>` per page, and a shared `<footer>`. The contact page's `<main>` should contain the full contact form from 2.11.

**2.16 — Accessibility fix-up** ⭐⭐⭐
Below is a page that "works" but is structurally poor. Rewrite it with proper landmarks, real `<label>`s, correct input types, and a caption/scope on the table.

```html
<body>
  <p>SUPER STORE</p>
  <p>Home | Shop | Contact</p>
  <p>Our Products</p>
  <table>
    <tr><td>Name</td><td>Price</td></tr>
    <tr><td>Mug</td><td>$8</td></tr>
    <tr><td>Cap</td><td>$15</td></tr>
  </table>
  <p>Join our newsletter</p>
  Email: <input>
  <input type="button" value="Go">
  <p>© Super Store</p>
</body>
```

**2.17 — Form spec from a screenshot** ⭐⭐⭐
Find any real signup or checkout form online. Without reading its source, recreate its fields, types, grouping, and which fields are required, using only in-scope tags. Then compare.

### Debug-it

**2.18 — Broken forms** ⭐⭐

**(a)** Labels don't focus their inputs when clicked:
```html
<label for="uname">Username</label>
<input type="text" id="username">
```
<details><summary>Show answer</summary>`for="uname"` must match the input's `id`. Make them identical (`for="username"` or `id="uname"` on both).</details>

**(b)** Radio buttons let you pick more than one at a time:
```html
<input type="radio" id="s" name="ship"> Standard
<input type="radio" id="e" name="express"> Express
```
<details><summary>Show answer</summary>Radios only behave as a group when they share the same `name`. Set both to `name="delivery"`.</details>

**(c)** The form's "required" isn't being enforced:
```html
<form>
  <input type="text" required="false">
  <button>Submit</button>
</form>
```
<details><summary>Show answer</summary>`required` is a boolean attribute — its mere presence means true. `required="false"` still means required. Remove it entirely if the field is optional.</details>

**(d)** Table headers aren't announced correctly / structure is off:
```html
<table>
  <tr><td>Day</td><td>Topic</td></tr>
  <tbody>
    <tr><td>Mon</td><td>HTML</td></tr>
  </tbody>
</table>
```
<details><summary>Show answer</summary>The header row uses `<td>` not `<th>`, and it isn't wrapped in `<thead>`. Use `<thead><tr><th scope="col">Day</th><th scope="col">Topic</th></tr></thead>`.</details>

**(e)** Nothing submits:
```html
<form>
  <label for="q">Question</label>
  <textarea id="q"></textarea>
  <button type="button">Send</button>
</form>
```
<details><summary>Show answer</summary>`type="button"` does not submit a form. Use `type="submit"` (or just `<button>` inside a form, which defaults to submit).</details>

### Written questions

1. Name four semantic landmark elements and say what content belongs in each.
2. `<section>` vs `<article>` vs `<div>` — how do you decide?
3. What two concrete benefits does semantic HTML give you over `<div>`s everywhere?
4. What does linking a `<label>` to an `<input>` with `for`/`id` actually do for the user?
5. When is a `<table>` the correct tool, and what is a common misuse of tables?
6. What is the difference between `placeholder` and a `<label>`? Why is a placeholder not a substitute for a label?
7. `required`, `minlength`, `pattern`, `min` — which apply to which input types, and what does each check?
8. Why might you group fields in a `<fieldset>` with a `<legend>`?

---
---

# Class 3 — CSS Basics & the Box Model

**In scope (adds to Class 2):** linking an external `style.css` with `<link>`, selectors (element, `.class`, `#id`, descendant `A B`, grouping `A, B`), the box model (`width`, `height`, `padding`, `border`, `margin`, `box-sizing`), colors (named, `#hex`, `rgb()`/`rgba()`), typography (`font-family`, `font-size`, `font-weight`, `line-height`, `text-align`, `letter-spacing`), `background` (`background-color`, `background-image`, `background-size`, `background-position`), `color`, basic units (`px`, `%`, `em`, `rem`), `display` (`block`/`inline`/`inline-block`/`none`).
**Still out of scope:** Flexbox, Grid, `position`, media queries, transitions/animations.

### Warm-up drills

**3.1 — Wire up a stylesheet** ⭐
Create `style.css` next to an HTML file, link it in `<head>` with `<link rel="stylesheet" href="style.css">`, and prove it's connected by setting `body { background-color: lightyellow; }`. Do it from memory twice.

**3.2 — Selector targeting** ⭐
Given one HTML page with headings, paragraphs, a `<ul>` inside a `<nav>`, and a paragraph with `id="lead"`: write CSS that (a) colours all `<h2>` dark blue, (b) makes every `<li>` inside the `<nav>` have no bullet and larger text, (c) makes only `#lead` bold and bigger, (d) gives every `<p>` a `line-height` of 1.6. One rule per requirement.

**3.3 — Box model by eye** ⭐
Three `<p>` elements. Give the first `padding: 20px`, the second `margin: 40px`, the third `border: 4px solid crimson`. Open dev tools, hover each, and read the box-model diagram. Write one sentence on what visibly differs between padding and margin.

**3.4 — Colour formats** ⭐
Make 6 boxes (use `<p>` or `<section>`), each a different colour, one written as a named colour, two as `#hex`, two as `rgb()`, one as `rgba()` with 50% alpha over a background image. Label each with its own value as text.

**3.5 — Type scale** ⭐
Set `body` font to a readable stack (e.g. `font-family: system-ui, Arial, sans-serif`). Then set `h1` 2.5rem, `h2` 2rem, `h3` 1.5rem, `p` 1rem/1.6, and a `.small` class at 0.85rem. View and adjust until it *feels* balanced.

**3.6 — box-sizing experiment** ⭐
Two identical `<section>`s, each `width: 300px; padding: 40px; border: 10px solid black`. Give one `box-sizing: border-box`. Measure both in dev tools. Write down the total rendered width of each and why they differ.

### Core assignments

**3.7 — Style the About Me page** ⭐⭐ 🧵
Take your Class 2 semantic About Me and add `class-3/about-me/style.css`. Requirements:
- [ ] readable body font, `max-width` on `<main>` (e.g. 700px) with `margin: 0 auto` to centre it
- [ ] a distinct `background-color` and `padding` on `<header>` and `<footer>`
- [ ] consistent vertical spacing between sections (use `margin`, pick one direction and stick to it)
- [ ] links styled (colour, and remove or restyle underline)
- [ ] a type scale for `h1`/`h2`/`p`
- [ ] the profile image given a fixed `width` and a `border`

**3.8 — Style the contact form** ⭐⭐ 🧵
Add CSS to your Class 2 contact form:
- [ ] labels on their own line, `display: block`, small margin below
- [ ] inputs and textarea: full width of the form (`width: 100%`), `padding: 10px`, `border`, `box-sizing: border-box`
- [ ] the form itself: `max-width: 480px`, centred, with `padding` and a subtle `border` or `background`
- [ ] the submit button: padding, background colour, `color`, no default border, pointer cursor
- [ ] consistent spacing between fields

**3.9 — Business card** ⭐⭐
Build one "card" to an exact spec — practising box-model precision:
- outer card: `width: 350px`, `padding: 24px`, `border: 1px solid #ddd`, `margin: 40px auto`, `background: #fff`
- inside: a name (`h2`, 1.4rem, no default margin-top), a role (`p`, `.muted` grey, uppercase via `text-transform`), a divider (a `<p>` or empty element with `border-top` and margin), then 3 contact lines
- Use dev tools to confirm the card's total width on screen is exactly 350px (hint: `box-sizing`).

**3.10 — Colour palette page** ⭐⭐
A page presenting a 6-colour palette: for each colour a `<section>` with `background-color` set, a fixed `height`, and text inside showing the hex and rgb values with enough `color` contrast to read. Add an `<h1>` and intro `<p>`. Group selectors where the rules repeat.

**3.11 — Typography specimen** ⭐⭐
A single-page "type specimen": show one font family at sizes from 0.75rem to 4rem, demonstrate `font-weight` 300/400/700, `line-height` tight vs loose on a paragraph of real text, `letter-spacing` on an all-caps heading, and `text-align` left/center/justify on three copies of the same paragraph. Label each demo.

**3.12 — Re-theme, don't re-structure** ⭐⭐ 🧵
Take the About Me HTML from 3.7 and, without touching the HTML, create a **second** stylesheet `theme-dark.css` that gives it a completely different look (dark background, light text, different accent colour, different font). Swap which stylesheet is linked to switch themes. This proves structure and style are separate.

**3.13 — Match the mockup** ⭐⭐
Spec (build to these numbers):
```
Page background:      #f4f4f4
Content column:       width 640px, centered, background #ffffff,
                      padding 32px, border 1px solid #e0e0e0
H1:                   font-size 2rem, margin-bottom 8px, color #1a1a1a
Subtitle p:           color #666, margin-top 0, margin-bottom 24px
Body p:               font-size 1rem, line-height 1.7, color #333
Links:                color #0066cc, no underline until hovered
```
Write HTML with sensible content, then hit every number.

### Challenge assignments

**3.14 — Box-model maths (no computer first)** ⭐⭐
On paper, then verify in the browser:
1. An element has `width: 200px; padding: 20px; border: 5px solid; margin: 10px`, default `box-sizing`. What is (a) the width of the visible box, (b) the horizontal space it occupies including margin?
2. Same values but `box-sizing: border-box`. Answer (a) and (b) again.
3. You want a visible box exactly 300px wide with 24px padding and a 3px border, using `content-box`. What `width` do you set?

<details><summary>Show answers</summary>

1. content-box: visible box = 200 + 20+20 + 5+5 = **250px**; with margin = 250 + 10 + 10 = **270px**.
2. border-box: visible box = **200px** (padding and border eat into it); with margin = **220px**.
3. `width: 300 − 24 − 24 − 3 − 3 = 246px`.
</details>

**3.15 — Style the blog homepage** ⭐⭐⭐ 🧵
Full CSS pass over your Class 2 blog homepage: centred content column, styled `<header>`/`<nav>` (nav links laid out with `display: inline-block` and spacing — no Flexbox yet), article previews with padding and a bottom border as a separator, a visually distinct `<aside>`, a styled `<footer>`. Consistent spacing scale throughout (pick e.g. 8 / 16 / 32px and only use those).

**3.16 — Recreate a real site's typography** ⭐⭐⭐
Pick a blog or news site you like. Using dev tools, read its `font-family`, `font-size`, `line-height`, and text `color` for headings and body. Recreate *just the reading experience* (a heading + 4 paragraphs) to match. You're training your eye and your dev-tools habit.

### Debug-it

**3.17 — CSS that isn't working** ⭐⭐

**(a)** The stylesheet has no effect at all:
```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```
…and the file on disk is named `style.css`.
<details><summary>Show answer</summary>Filename mismatch: `styles.css` vs `style.css`. The browser silently fails to load a missing stylesheet — check the Network tab. Rename one to match.</details>

**(b)** `margin` isn't applying:
```css
p {
  margin 20px;
}
```
<details><summary>Show answer</summary>Missing colon: `margin: 20px;`. One malformed declaration is dropped; a missing semicolon can also break the *next* rule.</details>

**(c)** The heading is red, but you wanted it from this rule which says blue:
```css
h1 { color: blue; }
#title { color: red; }
```
```html
<h1 id="title">Hello</h1>
```
<details><summary>Show answer</summary>Not a bug — specificity. `#id` (100) beats element selector (1), so red wins. To make blue win you'd need equal-or-higher specificity, e.g. `#title { color: blue; }`.</details>

**(d)** The box is wider than its container and causes a scrollbar:
```css
.card { width: 100%; padding: 30px; border: 2px solid; }
```
<details><summary>Show answer</summary>With default `content-box`, `width: 100%` + padding + border exceeds 100%. Add `box-sizing: border-box` (commonly applied to everything via `*, *::before, *::after { box-sizing: border-box; }`).</details>

**(e)** Descendant selector hits too much:
```css
nav a { color: white; }
```
…and it's also recolouring links in the `<footer>` nav you didn't mean to touch.
<details><summary>Show answer</summary>`nav a` matches links in *every* `<nav>`. Scope it: give the header nav an `id` (`#main-nav a { … }`) or the footer nav its own overriding rule.</details>

### Written questions

1. Why teach external CSS as the default instead of inline `style=""` or a `<style>` block?
2. In your own words: what are the four parts of the box model, from the inside out?
3. What is the practical difference between `margin` and `padding`? Give a case where only one of them is correct.
4. What does `box-sizing: border-box` change, and why do many people set it globally?
5. Put these selectors in order of specificity: `.menu li a`, `a`, `#logo`, `nav a`.
6. When would you use `rem` vs `px` vs `%`?
7. What's the difference between `display: none` and just making something the same colour as the background?
8. `color` vs `background-color` — which one is the text, which one is behind it?

---
---

# Class 4 — CSS Layout: Flexbox

**In scope (adds to Class 3):** `display: flex`, `flex-direction`, main axis vs cross axis, `justify-content`, `align-items`, `align-self`, `flex-wrap`, `gap`, `flex-grow`, `flex-shrink`, `flex-basis`, the `flex` shorthand, `order`.
**Still out of scope:** CSS Grid, media queries (that's next class — build these at a comfortable desktop width for now), `position`.

### Warm-up drills

**4.1 — Turn it on** ⭐
A `<div>`-free container (`<section>`) with 3 child `<p>`s. Add `display: flex`. Observe them going from stacked to side-by-side. Now add `gap: 16px`. Do it from memory 3 times.

**4.2 — justify-content tour** ⭐
Five copies of a flex row with 3 boxes. Set each copy to a different `justify-content`: `flex-start`, `flex-end`, `center`, `space-between`, `space-around` (bonus: `space-evenly`). Label each. Learn what each looks like.

**4.3 — align-items tour** ⭐
A flex row, tall container (`height: 200px`), 3 boxes of *different* heights. Cycle `align-items` through `stretch`, `flex-start`, `center`, `flex-end`, `baseline`. Note which one makes them equal height and why.

**4.4 — Axis flip** ⭐
Same 3 boxes. Toggle `flex-direction` between `row` and `column`. Write one sentence: when direction is `column`, which property now controls vertical distribution — `justify-content` or `align-items`?

**4.5 — Perfect centring** ⭐
Centre a single 100×100 box both horizontally and vertically inside a `400×300` container using exactly three declarations on the container. Memorise this — you'll use it forever.

**4.6 — gap vs margin** ⭐
Lay out 4 cards in a row with even spacing using `gap`. Then do it again using `margin` on the children instead. Note the annoyance at the edges with margin. Keep `gap`.

### Core assignments

**4.7 — Navbar** ⭐⭐ 🧵
`class-4/navbar/`: a site header with the brand/logo text on the left and 4 nav links pushed to the right, vertically centred, with even spacing between links. Use Flexbox on the `<nav>` (or `<header>`). Requirements:
- [ ] brand left, links right (`justify-content: space-between`)
- [ ] links evenly spaced from each other (`gap`)
- [ ] everything vertically centred (`align-items: center`)
- [ ] some `padding` on the bar and a `background-color`

**4.8 — Three-card feature row** ⭐⭐ 🧵
Three equal-width feature cards in a row, `gap` between them, equal height even though their text length differs. Each card: an emoji or image "icon", an `<h3>`, a `<p>`, and an `<a>` "Learn more" pinned to the bottom of the card (hint: card is itself `display: flex; flex-direction: column`, and the link gets `margin-top: auto`).

**4.9 — Media object** ⭐⭐
The classic "image on the left, text block on the right" pattern: a fixed-width image, then a flexible text column that takes the remaining space (`flex: 1`), vertically top-aligned, with a `gap` between. Build three stacked media objects (a mini "reviews" list).

**4.10 — Button / toolbar group** ⭐⭐
A toolbar: a row of 5 buttons left-aligned, plus one "Delete" button pushed to the far right (`margin-left: auto` on that one child). All vertically centred, consistent `gap`, consistent button padding.

**4.11 — Pricing table** ⭐⭐ 🧵
Three pricing plans side by side, equal height, `gap` between. The middle one is "featured" — slightly wider or visually lifted (bigger padding / different background). Each plan: title, big price, a `<ul>` of features, a call-to-action button at the bottom (again `margin-top: auto`).

**4.12 — Sidebar layout** ⭐⭐
A page split into a fixed 240px sidebar and a flexible main area (`flex: 1`) filling the rest, full viewport height (`min-height: 100vh` on the flex container). Sidebar has a vertical nav (`flex-direction: column`, `gap`). Main area has a heading and paragraphs.

**4.13 — Contact form → two columns** ⭐⭐ 🧵
Per the course homework: take your Class 3 contact form and lay the fields out in two columns using Flexbox + `flex-wrap` — e.g. name and email share a row, subject spans full width, message spans full width, and the layout still looks acceptable when the window is narrow (fields wrap to one column). Use `flex-basis` / `flex-grow` on the field wrappers.

### Challenge assignments

**4.14 — Flexbox puzzles** ⭐⭐⭐
Reproduce each of these arrangements. Container is a flex row unless stated; boxes are equal size unless stated.
1. All boxes clustered in the centre with equal gaps between them, but the first box stuck to the left edge and the last stuck to the right edge. *(one box gets `margin-right: auto`? experiment)*
2. A row of 6 boxes that wraps to a second row when the container narrows, with equal `gap` on both axes, and the wrapped row also centred.
3. Three boxes: left one top-aligned, middle centred, right one bottom-aligned — all in the same row. *(hint: `align-self`)*
4. A row where one box is visually first but is last in the HTML. *(hint: `order`)*
5. Two boxes that always split the container 1/3 and 2/3 regardless of width. *(hint: `flex-grow` 1 and 2, `flex-basis: 0`)*

**4.15 — Rebuild the blog homepage layout with Flexbox** ⭐⭐⭐ 🧵
Take your Class 3 blog homepage. Convert: the nav to a flex row, the main+aside into a two-column flex layout (`main` flexible, `aside` fixed ~280px), and each article preview into a flex row (thumbnail + text). Keep it readable at desktop width.

**4.16 — Card grid without Grid** ⭐⭐⭐
Lay out 9 cards, 3 per row, evenly spaced, using only Flexbox + `flex-wrap` + `gap`. Get the wrapping math right so you never end up with a lonely stretched card on the last row (hint: fixed `flex-basis`, and think about what `flex-grow: 0` vs `1` does to the last row).

### Debug-it

**4.17 — Flex not behaving** ⭐⭐

**(a)** `justify-content` does nothing:
```css
.row { display: flex; }
.row .item { justify-content: center; }
```
<details><summary>Show answer</summary>`justify-content` goes on the flex **container**, not the items. Move it to `.row`.</details>

**(b)** Items are in a column, not a row:
```css
.row { display: flex; flex-direction: column; }
```
<details><summary>Show answer</summary>Either `flex-direction: column` was set on purpose elsewhere, or it's inherited from a parent rule. Set `flex-direction: row` (or remove the column rule).</details>

**(c)** `align-items: center` won't vertically centre anything:
```css
.row { display: flex; align-items: center; }
```
…and the row has no explicit height, so it's exactly as tall as its tallest child.
<details><summary>Show answer</summary>Nothing to centre *within* — the container hugs its content. Give the container a `height`/`min-height` taller than the children, then `align-items: center` visibly centres them.</details>

**(d)** The "push to the right" trick isn't working:
```css
.bar { display: flex; }
.bar .spacer { margin-left: auto; }
```
…but `.spacer` is `display: none` / doesn't exist.
<details><summary>Show answer</summary>`margin-left: auto` must be on a real, visible flex child — usually the element you want pushed right (e.g. the last button), not a separate empty spacer that's hidden.</details>

**(e)** Flex children overflow the container instead of shrinking:
```css
.row { display: flex; }
.row img { width: 400px; }
```
<details><summary>Show answer</summary>Flex items won't shrink below their content/`min-width` by default. Add `min-width: 0` (and/or `max-width: 100%`) to the flex child, or let it flex with `flex: 1`.</details>

### Written questions

1. Which Flexbox properties go on the **container** and which go on the **items**? List them.
2. What is the "main axis" and what is the "cross axis"? How does `flex-direction` affect which is which?
3. `justify-content` vs `align-items` — one sentence each.
4. When do you need `flex-wrap`? What happens without it when items don't fit?
5. What does `flex: 1` actually expand to, and what does it do?
6. Why is `gap` usually nicer than putting `margin` on flex children?
7. Give one real layout where Flexbox is clearly the right tool.
8. What does `margin-left: auto` do to a single flex item, and why?

---
---

# Class 5 — CSS Grid & Responsive Design

**In scope (adds to Class 4):** `display: grid`, `grid-template-columns` / `grid-template-rows`, `fr` unit, `repeat()`, `minmax()`, `auto-fit` / `auto-fill`, `gap`, `grid-column` / `grid-row` spanning, `grid-template-areas`, `place-items` / `place-content`, `@media` queries (`min-width` / `max-width`), mobile-first methodology, the viewport `<meta>` tag, relative units for responsiveness (`%`, `vw`, `vh`, `rem`, `clamp()`).
**Still out of scope:** `position: sticky/fixed` deep dives, CSS animations, JS.

### Warm-up drills

**5.1 — First grid** ⭐
A container with 6 children. `display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px`. Watch a 3×2 grid appear. From memory ×3.

**5.2 — fr vs px vs auto** ⭐
One grid, try these column templates one at a time and describe each result: `200px 200px 200px`, `1fr 1fr 1fr`, `1fr 2fr 1fr`, `200px 1fr`, `auto 1fr auto`.

**5.3 — Responsive grid, no media query** ⭐
`grid-template-columns: repeat(auto-fit, minmax(200px, 1fr))`. Put 8 cards in it. Resize the window and watch columns add/remove automatically. Write one sentence on what `minmax(200px, 1fr)` is doing.

**5.4 — Spanning** ⭐
A 4-column grid with 8 items. Make item 1 span 2 columns (`grid-column: span 2`), item 5 span the full width (`grid-column: 1 / -1`), item 8 span 2 rows. Observe how the rest flow around.

**5.5 — Named areas** ⭐
Build a page skeleton with `grid-template-areas` for `header` / `sidebar` / `content` / `footer` (header and footer full width, sidebar + content side by side). Assign each landmark with `grid-area`.

**5.6 — Media query drill** ⭐
One paragraph. Default `font-size: 1rem`. Add `@media (min-width: 600px) { font-size: 1.125rem; }` and `@media (min-width: 900px) { font-size: 1.25rem; }`. Resize and confirm the jumps. Then reason about why `min-width` queries stack cleanly in mobile-first order.

**5.7 — The meta tag** ⭐
Open one of your earlier pages on a phone (or dev-tools device mode) **without** `<meta name="viewport" content="width=device-width, initial-scale=1">`. Then add it. Note the difference. Never forget it again.

### Core assignments

**5.8 — Responsive photo gallery** ⭐⭐ 🧵
`class-5/gallery/`: a gallery of 12 images.
- [ ] `<meta viewport>` present
- [ ] grid with `repeat(auto-fit, minmax(220px, 1fr))` and a `gap`
- [ ] images: `width: 100%`, fixed aspect via `aspect-ratio: 1 / 1` and `object-fit: cover`
- [ ] reflows from ~4 columns on desktop down to 1 column on a phone with **no media query needed**
- [ ] a heading and short intro above the grid, constrained to a readable width

**5.9 — Full page layout with grid-template-areas** ⭐⭐ 🧵
A complete page: `<header>` (full width), `<nav>` sidebar (left, ~220px), `<main>` (fills rest), `<footer>` (full width). Use `grid-template-areas`. Then add a `@media (max-width: 768px)` block that redefines the areas so the sidebar stacks **above** the main content and everything is one column.

**5.10 — Dashboard card grid** ⭐⭐
A stats dashboard: a grid of "stat" cards. On desktop: 4 columns. At `max-width: 1000px`: 2 columns. At `max-width: 600px`: 1 column. Two of the cards ("Revenue chart", "Recent activity") span 2 columns on desktop. Use media queries.

**5.11 — Magazine / bento layout** ⭐⭐
A 12-column grid (or 6) where articles have different sizes: one hero spanning 8 columns and 2 rows, a couple spanning 4, several spanning 3. It should collapse to a single column under 700px.

**5.12 — Calendar month** ⭐⭐
A 7-column grid (`repeat(7, 1fr)`) for the days of a month. A header row of weekday names, then ~35 day cells (some empty for the offset at the start of the month). Cells are square-ish, numbered, with a `gap`. Under 500px, shrink text and padding via a media query rather than changing column count.

**5.13 — Make About Me + Contact responsive** ⭐⭐ 🧵
Per the course homework. Revisit your styled About Me and Contact pages:
- [ ] add/confirm the viewport meta tag
- [ ] give the content a `max-width` and fluid side padding (`padding: 0 clamp(16px, 5vw, 48px)`)
- [ ] the About Me "Things I Like" / "Goals" become a 2-column grid on desktop, 1 column under 640px
- [ ] the contact form's two-column field layout (from Class 4) collapses to one column under 640px
- [ ] images never overflow (`max-width: 100%`)
- [ ] test at 375px, 768px, 1280px

**5.14 — Mobile-first rebuild** ⭐⭐
Pick any page you've built. Delete its layout CSS. Rebuild the CSS **mobile-first**: write the single-column phone layout with *no* media queries first, then add `@media (min-width: …)` blocks that progressively introduce columns. The base rules must never live inside a `max-width` query.

### Challenge assignments

**5.15 — Grid vs Flexbox: choose and justify** ⭐⭐
For each scenario, state whether you'd reach for Grid or Flexbox and why (one line each):
1. A horizontal navbar with logo left, links right.
2. An image gallery that reflows into as many columns as fit.
3. A page-level header / sidebar / content / footer layout.
4. A row of tags/chips of varying widths that wrap.
5. A form where labels align in a column and inputs align in another.
6. Centring a single modal box on the screen.
7. A dashboard where specific cards must occupy specific cells and sizes.
8. A list of buttons in a toolbar, one pushed to the far end.

<details><summary>Show suggested answers</summary>

1. Flexbox (1D row, `space-between`).
2. Grid (`auto-fit` + `minmax`).
3. Grid (2D, `grid-template-areas`).
4. Flexbox (`flex-wrap`, content-sized items).
5. Grid (two aligned tracks) — or Flexbox per row; Grid is cleaner.
6. Either; Grid `place-items: center` is the shortest.
7. Grid (explicit placement/spanning).
8. Flexbox (`margin-left: auto` on the odd one out).
</details>

**5.16 — Reproduce a layout at three breakpoints** ⭐⭐⭐ 🧵
Design (or find) a simple landing page. Implement it so it deliberately changes at 3 sizes:
- **< 640px:** single column, hamburger-style stacked nav (links in a vertical list — no JS, just stacked), hero text centred, one CTA.
- **640–1024px:** 2-column feature section, nav becomes a row.
- **> 1024px:** 3-column features, wider hero with image beside text, constrained `max-width` container centred.

**5.17 — Fluid type with clamp()** ⭐⭐⭐
Build a page whose headings scale smoothly with the viewport using `clamp()` (e.g. `font-size: clamp(1.75rem, 1rem + 4vw, 3.5rem)`) so you need *zero* media queries for typography. Add a small table in the page documenting the min/preferred/max you chose for each level and why.

**5.18 — Convert a Flexbox layout to Grid (and vice-versa)** ⭐⭐⭐
Take your Class 4 pricing table (Flexbox) and rebuild it with Grid. Take your Class 5 gallery (Grid) and rebuild it with Flexbox + `flex-wrap`. Write 3 sentences on which felt more natural for each and why.

### Debug-it

**5.19 — Grid & responsive bugs** ⭐⭐

**(a)** The grid has only one column no matter what:
```css
.grid { display: grid; grid-template: 1fr 1fr 1fr; }
```
<details><summary>Show answer</summary>`grid-template` shorthand with just `1fr 1fr 1fr` sets *rows*, not columns. Use `grid-template-columns: 1fr 1fr 1fr` (or `repeat(3, 1fr)`).</details>

**(b)** `grid-column: 1 / 3` spans only one column:
```css
.item { grid-column: 1 / 3; }
```
…in a grid that only has 2 columns; the author expected it to span "1 through 3 = three columns".
<details><summary>Show answer</summary>Line numbers, not counts. `1 / 3` means from line 1 to line 3 = **2** columns. For 3 columns use `1 / 4` or `1 / span 3`.</details>

**(c)** Mobile styles are overriding desktop unexpectedly:
```css
@media (min-width: 900px) { .col { width: 33%; } }
@media (min-width: 600px) { .col { width: 50%; } }
```
<details><summary>Show answer</summary>Order matters when specificity is equal. At 1000px both queries match; the *later* rule (`50%`) wins. Put `min-width` queries in **ascending** order so the largest matching one comes last.</details>

**(d)** Page looks fine on desktop, zoomed-in and broken on a phone:
<details><summary>Show answer</summary>Missing `<meta name="viewport" content="width=device-width, initial-scale=1">` in `<head>`. Without it, mobile browsers render at ~980px and scale down.</details>

**(e)** `auto-fit` grid collapses all items into a sliver on a wide screen:
```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```
…and there are only 2 items.
<details><summary>Show answer</summary>`auto-fit` collapses empty tracks, letting 2 items stretch across the whole width. If you want them to stay ~200px, use `auto-fill` instead, or cap with `minmax(200px, 300px)`.</details>

### Written questions

1. Grid vs Flexbox in one sentence each — when does each shine?
2. What does the `fr` unit mean? How is `1fr 2fr` different from `33% 66%`?
3. Explain `repeat(auto-fit, minmax(200px, 1fr))` in plain English.
4. `auto-fit` vs `auto-fill` — what's the difference?
5. Why are grid line numbers a common off-by-one trap? How does `span` avoid it?
6. What is "mobile-first" and why does it lead to cleaner media-query stacks?
7. What exactly does the viewport meta tag do?
8. Name three things that make a page responsive *without* any media queries.

---
---

# Class 6 — JavaScript Basics

**In scope (adds to Class 5):** `<script>` tag, `let` / `const`, data types (string, number, boolean, `null`, `undefined`), template literals, operators (arithmetic, comparison `===`/`!==`, logical `&&`/`||`/`!`), `if` / `else if` / `else`, ternary, `for` loop, `while` loop, functions (declaration, parameters, `return`), `console.log`, browser dev-tools Console, arrays (create, index, `.length`, `.push`, loop over), basic string methods (`.toUpperCase`, `.toLowerCase`, `.length`, `.includes`, `.slice`), `Math` (`.round`, `.floor`, `.random`, `.max`).
**Out of scope:** the DOM (`document`, `querySelector`), events — that's Class 7. Everything here runs in the Console or via `console.log`.

> For every assignment: write functions in a `.js` file, load it with `<script src="app.js"></script>` at the end of `<body>`, and check output in the Console. No page interaction yet.

### Warm-up drills

**6.1 — Declare and log** ⭐
Declare a `const` for your name, a `let` for your age, a `const` boolean `isStudent`. `console.log` each, then log a single template-literal sentence using all three.

**6.2 — typeof** ⭐
Log the `typeof` of: `"hi"`, `42`, `true`, `null`, `undefined`, `3.14`, `"7"`, `2 + 2`, `"2" + 2`. Predict each before running; note the two that surprise you.

**6.3 — Arithmetic** ⭐
Given `a = 17`, `b = 5`: log `a + b`, `a - b`, `a * b`, `a / b`, `a % b`, and `a ** 2`. Say in a comment what `%` gave you and why.

**6.4 — Comparisons** ⭐
Predict then verify: `5 == "5"`, `5 === "5"`, `0 === false`, `"" === false`, `10 > 3 && 3 > 5`, `10 > 3 || 3 > 5`, `!(5 > 2)`.

**6.5 — if/else ladder** ⭐
Write a function `describeNumber(n)` that logs "negative", "zero", or "positive". Call it with 5 different values.

**6.6 — Ternary** ⭐
Rewrite `describeNumber`'s positive/negative decision (ignore zero) as a single `return n >= 0 ? "positive-ish" : "negative"`.

**6.7 — for loop** ⭐
Log the numbers 1 to 20. Then log only the even ones. Then log them in reverse, 20 down to 1.

**6.8 — while loop** ⭐
Using `while`, keep halving `100` (integer or float) and logging the result until it drops below `1`.

**6.9 — Array basics** ⭐
Make an array of 5 city names. Log its `.length`, the first and last elements (last via `arr[arr.length - 1]`), `.push` a 6th, then loop with `for` and log `"City 1: Lagos"` style lines.

**6.10 — String methods** ⭐
Given `const s = "Frontend Crash Course"`: log its length, uppercase, lowercase, whether it `.includes("Crash")`, and its first word via `.slice`.

### Core assignments — write these as functions with `return`

**6.11 — The classic ten** ⭐⭐
Implement each. Test each with at least 3 inputs via `console.log`.
1. `add(a, b)` → sum
2. `isEven(n)` → boolean
3. `maxOfTwo(a, b)` → the larger
4. `celsiusToFahrenheit(c)` → °F
5. `circleArea(r)` → area (use `Math.PI`)
6. `absoluteValue(n)` → without using `Math.abs`
7. `average(a, b, c)` → mean of three numbers
8. `secondsToClock(total)` → `"MM:SS"` string
9. `initials(fullName)` → e.g. `"Ada Byron King"` → `"ABK"`
10. `isVowel(char)` → boolean

**6.12 — Grade calculator** ⭐⭐
`letterGrade(score)`: 90+ → "A", 80–89 → "B", 70–79 → "C", 60–69 → "D", below 60 → "F". Guard against scores above 100 or below 0 (return `"invalid"`). Test the boundaries (89, 90, 0, 100, -1, 101).

**6.13 — Ticket pricing** ⭐⭐
`ticketPrice(age, isWeekend)`: base $12. Under 5 → free. 5–17 → half price. 65+ → $8 flat. Weekend adds $3 to any non-free ticket. Return the final number. Test all branches.

**6.14 — FizzBuzz** ⭐⭐
Loop 1 to 100. Multiples of 3 → "Fizz", of 5 → "Buzz", of both → "FizzBuzz", else the number. Then refactor the decision into a function `fizzbuzz(n)` that returns the right value, and keep the loop just for logging.

**6.15 — Loop toolkit** ⭐⭐
Write and test:
1. `sumTo(n)` → 1 + 2 + … + n
2. `factorial(n)`
3. `countVowels(str)`
4. `reverseString(str)` (build it with a loop, not `.reverse()`)
5. `multiplicationTable(n)` → logs the 1×n … 12×n lines
6. `isPrime(n)` → boolean
7. `fibonacci(n)` → the nth Fibonacci number
8. `largestInArray(numbers)` → without `Math.max(...arr)`

**6.16 — Tip / bill splitter** ⭐⭐
`splitBill(total, tipPercent, people)` → returns the amount **each person pays**, rounded to 2 decimals (`Math.round(x * 100) / 100`). Handle `people = 0` gracefully. Log a formatted summary line with a template literal.

**6.17 — Array report** ⭐⭐
Given an array of daily step counts for a week, write functions: `totalSteps(arr)`, `averageSteps(arr)`, `bestDay(arr)` (returns day number 1–7), `daysAboveGoal(arr, goal)` (returns a count). Loop; no fancy array methods required.

**6.18 — Password strength (logic only)** ⭐⭐
`passwordScore(pw)`: start at 0. +1 if length ≥ 8, +1 if it contains a digit, +1 if it contains an uppercase letter, +1 if it contains a lowercase letter, +1 if length ≥ 12. Return `"weak"` (0–2), `"ok"` (3), `"strong"` (4–5). You may loop character by character and use comparisons / `.toUpperCase()` tricks.

**6.19 — Course homework: five logic functions** ⭐⭐ 🧵
Pick any **five** functions from 6.11 / 6.15 you have not fully nailed and rewrite them from scratch in a fresh file, with 3 test calls each. This is the graded homework — keep the file.

### Challenge assignments

**6.20 — Console mini-games (no DOM)** ⭐⭐⭐
1. `rockPaperScissors(playerMove)` — computer picks randomly (`Math.random`), returns `"win"` / `"lose"` / `"draw"`.
2. `guessOutcome(secret, guess)` — returns `"too high"`, `"too low"`, or `"correct"`. Then write a loop that simulates a binary-search player and counts guesses.
3. `rollDice(times)` — rolls two dice `times` times, returns how many rolls totalled 7.

**6.21 — Simple cart total** ⭐⭐⭐
Given two parallel arrays `prices` and `quantities`, write `cartTotal(prices, quantities, taxRate)` that returns `{ subtotal, tax, total }` (log the pieces). Add `applyCoupon(total, code)` where `"SAVE10"` gives 10% off and anything else is a no-op.

**6.22 — Trace the code (predict the Console output)** ⭐⭐⭐
For each snippet, write down what it logs **before** running, then check.

```js
// A
let x = 3;
function bump(n) { n = n + 1; return n; }
bump(x);
console.log(x);
```
```js
// B
const nums = [1, 2, 3];
for (let i = 0; i <= nums.length; i++) {
  console.log(nums[i]);
}
```
```js
// C
let total = 0;
for (let i = 1; i < 5; i++) {
  total += i;
}
console.log(total);
```
```js
// D
console.log(1 + "1");
console.log("5" - 2);
console.log(true + true);
console.log(10 / "a");
```
```js
// E
function mystery(a, b) {
  if (a > b) return "first";
  if (a < b) return "second";
  return "equal";
  console.log("done");
}
console.log(mystery(4, 4));
```

<details><summary>Show answers</summary>

- **A** → `3`. Numbers are passed by value; reassigning `n` inside `bump` doesn't touch `x`. (Also `bump(x)`'s return value is discarded.)
- **B** → `1`, `2`, `3`, `undefined`. The condition `i <= length` runs one iteration too many; `nums[3]` is `undefined`.
- **C** → `10` (1+2+3+4).
- **D** → `"11"`, `3`, `2`, `NaN`.
- **E** → `"equal"`. The `console.log("done")` after `return` is unreachable and never runs.
</details>

### Debug-it

**6.23 — Broken functions** ⭐⭐

**(a)** Always logs `undefined`:
```js
function double(n) {
  n * 2;
}
console.log(double(5));
```
<details><summary>Show answer</summary>No `return`. `return n * 2;`.</details>

**(b)** Throws "Assignment to constant variable":
```js
const count = 0;
for (let i = 0; i < 3; i++) {
  count = count + 1;
}
```
<details><summary>Show answer</summary>`count` is reassigned but declared `const`. Use `let count = 0;`.</details>

**(c)** The `if` always runs, even for `5`:
```js
let n = 5;
if (n = 10) {
  console.log("n is ten");
}
```
<details><summary>Show answer</summary>`=` is assignment, not comparison. `n = 10` sets `n` and evaluates to `10` (truthy). Use `if (n === 10)`.</details>

**(d)** Infinite loop (tab freezes):
```js
let i = 0;
while (i < 5) {
  console.log(i);
}
```
<details><summary>Show answer</summary>`i` never changes. Add `i++;` inside the loop.</details>

**(e)** `countVowels("Sky")` returns `0`, but `countVowels("SKY")` should logically match "sky"… and `countVowels("Apple")` returns `1` not `2`:
```js
function countVowels(str) {
  let count = 0;
  for (let i = 0; i < str.length; i++) {
    if (str[i] === "a" || str[i] === "e" || str[i] === "i" || str[i] === "o" || str[i] === "u") {
      count++;
    }
  }
  return count;
}
```
<details><summary>Show answer</summary>Case sensitivity — `"A"` isn't matched. Lowercase first: `const c = str[i].toLowerCase();` then compare `c`.</details>

**(f)** Off-by-one — misses the last element:
```js
const arr = [10, 20, 30, 40];
for (let i = 0; i < arr.length - 1; i++) {
  console.log(arr[i]);
}
```
<details><summary>Show answer</summary>`i < arr.length - 1` stops before the last index. Use `i < arr.length`.</details>

### Written questions

1. `let` vs `const` — when do you use each? What does `const` actually prevent?
2. `==` vs `===` — show an example where they disagree.
3. What is the difference between a function that `console.log`s a value and one that `return`s it? Why does it matter?
4. What are the parts of a `for` loop's `(…)` header, and when does each run?
5. What is `undefined` and how is it different from `null`?
6. What does `"3" + 4` produce, and why? What about `"3" * 4`?
7. When would you choose a `while` loop over a `for` loop?
8. What is a parameter vs an argument?

---
---

# Class 7 — JavaScript & the DOM

**In scope (adds to Class 6):** `document.querySelector` / `querySelectorAll`, reading/writing `.textContent` and `.value`, `.innerHTML` (and why to be careful), `.style.property`, `.classList` (`.add` / `.remove` / `.toggle` / `.contains`), `.setAttribute` / `.getAttribute`, `addEventListener` for `click`, `input`, `submit`, `change`, `keyup`; the `event` object, `event.target`, `event.preventDefault()`, creating elements (`document.createElement`, `.append`), placing `<script>` correctly (end of body or `defer`).
**Out of scope:** `fetch` / APIs, `localStorage`, modules, frameworks.

### Warm-up drills

**7.1 — Select and log** ⭐
On a page with an `<h1>`, three `<p>`s, and a `<ul>`: log the `<h1>`'s `textContent`, log how many `<p>`s `querySelectorAll` finds, and log the second paragraph's text.

**7.2 — Change text on click** ⭐
A `<button>` and an `<h1>`. Clicking the button changes the `<h1>` text to "Clicked!". Do it from memory 3 times.

**7.3 — Toggle a class** ⭐
A paragraph and a button. Define `.highlight { background: yellow; }` in CSS. The button toggles `.highlight` on the paragraph with `classList.toggle`.

**7.4 — Read an input** ⭐
A text input and a button. On click, `console.log` whatever is currently in `input.value`.

**7.5 — input event** ⭐
A text input and a `<span>`. As you type, the span mirrors the input's value live (`addEventListener("input", …)`).

**7.6 — querySelectorAll loop** ⭐
Five buttons. Loop over them and add a click listener to each that logs `event.target.textContent`.

**7.7 — preventDefault** ⭐
A `<form>` with one input and a submit button. On `submit`, call `event.preventDefault()` and `console.log("would have submitted")`. Confirm the page no longer reloads.

### Core assignments

**7.8 — Counter** ⭐⭐
Buttons: "−", "reset", "+". A number display starting at 0. `+` increments, `−` decrements, "reset" sets it back to 0. Bonus: the number turns red when negative (`classList` + CSS).

**7.9 — Light / dark mode toggle** ⭐⭐ 🧵
Per the course hands-on. A button that toggles a `.dark` class on `<body>`. Define both themes in CSS (light default, `.dark` overrides background/text/link colours). Button label switches between "🌙 Dark" and "☀️ Light".

**7.10 — Contact form "Thank you"** ⭐⭐ 🧵
Per the course hands-on. Take your contact form. On `submit`: `preventDefault`, hide the form (`classList` or `.hidden`), and show a "✅ Thanks, {name} — we'll be in touch." message that includes the value the user typed in the name field.

**7.11 — Live character counter** ⭐⭐
A `<textarea maxlength="200">` and a counter showing "0 / 200". On `input`, update the count. When remaining < 20, the counter turns orange; at 0, red.

**7.12 — Show / hide (accordion)** ⭐⭐ 🧵
An FAQ list: 5 questions as buttons, each with a hidden answer `<div>` beneath. Clicking a question toggles its answer. Bonus: opening one closes the others.

**7.13 — To-do list** ⭐⭐ 🧵
An input + "Add" button + `<ul>`. Adding creates a new `<li>` with the text and a "×" delete button. Clicking "×" removes that `<li>`. Clicking the `<li>` text toggles a `.done` class (strikethrough). Empty input does nothing.

**7.14 — Tab switcher** ⭐⭐
Three tab buttons and three content panels. Clicking a tab shows its panel and hides the others, and marks the clicked tab "active" (class). Only one panel visible at a time.

**7.15 — Image gallery** ⭐⭐ 🧵
A large "main" image and a row of 6 thumbnails. Clicking a thumbnail swaps the main image's `src` (and `alt`) to match, and highlights the active thumbnail.

**7.16 — Live form validation** ⭐⭐
A signup form (name, email, password). On `input`, show inline messages: name must be ≥ 2 chars, email must contain "@" and ".", password must be ≥ 8 chars. The submit button is disabled until all three pass. On successful submit: `preventDefault` + success message.

**7.17 — Colour changer** ⭐⭐
Three range/number inputs or three buttons (or a text input for a hex value). Clicking/typing updates `document.body.style.backgroundColor`. Add a "random colour" button that builds a random hex string with `Math.random`.

**7.18 — Temperature converter UI** ⭐⭐ 🧵
Wire your Class 6 `celsiusToFahrenheit` function to the page: a number input for °C, and as the user types (`input` event) a `<span>` shows the °F result. Add a second row for °F → °C.

**7.19 — Course homework: add interactivity to earlier pages** ⭐⭐ 🧵
Per the course homework — add **one** interactive feature to each of these earlier builds:
- About Me page → a "read more" toggle that expands a hidden bio paragraph.
- Gallery → click an image to enlarge it (toggle a `.big` class).
- Blog homepage → a "filter" that hides articles not matching a typed keyword (compare `input.value` against each article's `textContent` with `.includes`).

### Challenge assignments

**7.20 — Quiz app** ⭐⭐⭐
5 multiple-choice questions rendered on the page. The user picks answers (radio groups). A "Submit" button tallies the score with `preventDefault`, then shows "You scored 4 / 5" and marks each question right/wrong with colour. A "Try again" button resets everything.

**7.21 — Mini shopping cart** ⭐⭐⭐
A list of 4 products, each with an "Add to cart" button. A cart panel shows added items, a quantity per item ("+"/"−"), a live subtotal, and a "Remove" button. Reuse your Class 6 `cartTotal` logic for the maths.

**7.22 — Build the DOM from data** ⭐⭐⭐
Start with an array of objects in JS (e.g. 6 movies with `title`, `year`, `rating`). On page load, loop the array and `createElement` a card for each, appending to a container. Add a button that sorts by rating and re-renders.

**7.23 — Rebuild a component you've used** ⭐⭐⭐
Pick one: an image carousel with prev/next buttons, a star-rating widget (hover + click), or a multi-step form (Next/Back between 3 fieldsets with a progress indicator). Plain JS only.

### Debug-it

**7.24 — DOM bugs** ⭐⭐

**(a)** `Cannot read properties of null (reading 'addEventListener')`:
```html
<head>
  <script src="app.js"></script>
</head>
<body>
  <button id="go">Go</button>
</body>
```
```js
document.querySelector("#go").addEventListener("click", () => console.log("hi"));
```
<details><summary>Show answer</summary>The script runs before the `<button>` exists. Move `<script>` to the end of `<body>`, or add `defer`: `<script src="app.js" defer></script>`.</details>

**(b)** The selector finds nothing:
```js
const box = document.querySelector("box");
```
```html
<div class="box"></div>
```
<details><summary>Show answer</summary>`querySelector` takes a CSS selector. `"box"` looks for a `<box>` tag. Use `".box"` for the class (or `"#box"` for an id).</details>

**(c)** Clicking the button reloads the page and loses everything:
```js
form.addEventListener("submit", () => {
  message.textContent = "Sent!";
});
```
<details><summary>Show answer</summary>The form still does its default submit/reload. Take the event and call it: `form.addEventListener("submit", (e) => { e.preventDefault(); message.textContent = "Sent!"; });`</details>

**(d)** Only the last button works:
```js
const buttons = document.querySelectorAll("button");
buttons.addEventListener("click", () => console.log("clicked"));
```
<details><summary>Show answer</summary>`querySelectorAll` returns a NodeList, which has no `addEventListener`. Loop it: `buttons.forEach(btn => btn.addEventListener("click", …))`.</details>

**(e)** Text shows literally as `<b>hi</b>` on the page:
```js
el.textContent = "<b>hi</b>";
```
<details><summary>Show answer</summary>Not necessarily a bug — `textContent` escapes HTML (that's the safe behaviour). If you truly want bold, use `el.innerHTML = "<b>hi</b>"` — but never do that with untrusted user input.</details>

**(f)** The counter shows `"01"`, `"011"`, `"0111"`:
```js
let count = 0;
btn.addEventListener("click", () => {
  count = count + btn.dataset.step; // step is "1"
  display.textContent = count;
});
```
<details><summary>Show answer</summary>`btn.dataset.step` is the string `"1"`, so `+` concatenates. Convert: `count = count + Number(btn.dataset.step);`</details>

### Written questions

1. What is the DOM? How is it related to but different from the HTML file you wrote?
2. `querySelector` vs `querySelectorAll` — what does each return, and how do you use the result?
3. Why does `<script>` placement matter? Two ways to make sure the DOM exists first.
4. `textContent` vs `innerHTML` — when is each appropriate, and what's the risk with one of them?
5. What does `event.preventDefault()` do? Give two events where you'd want it.
6. What is `event.target`? Why is it useful when one listener covers many elements?
7. Describe three things `classList` lets you do, and why toggling a class is often better than setting `.style` directly.
8. Walk through, in order, what happens from "user clicks button" to "page text changes".

---
---

# Class 8 — Capstone: Portfolio Project

**Goal:** one responsive, interactive personal portfolio page (or small multi-page site) that uses everything: semantic HTML, external CSS with a real layout (Flexbox **and** Grid), responsiveness (mobile-first + at least one media query or fluid technique), and JavaScript interactivity (DOM + events).

You'll deliver **one** main project. The variants and stretch goals below are extra practice, not required.

### The core brief — build this

**8.1 — Personal portfolio** ⭐⭐⭐ 🧵
`class-8/portfolio/` with `index.html`, `style.css`, `app.js`.

Required structure (semantic):
- [ ] `<header>` with your name/logo and a `<nav>` (real in-page anchor links: `#about`, `#projects`, `#contact`)
- [ ] a hero `<section>`: heading, one-line pitch, a call-to-action button/link
- [ ] `<main>` containing:
  - [ ] `#about` — a `<section>` with a short bio and a photo (`<figure>` + `<figcaption>` optional)
  - [ ] `#skills` — a list or grid of skills
  - [ ] `#projects` — **at least 3** project cards in a Grid (title, image/placeholder, description, a link)
  - [ ] `#contact` — a working (non-sending) contact form with proper labels and validation attributes
- [ ] `<footer>` with copyright and 2–3 links

Required CSS:
- [ ] external `style.css`, no inline styles
- [ ] a defined type scale and a small spacing scale, used consistently
- [ ] `box-sizing: border-box` globally
- [ ] the nav laid out with **Flexbox**
- [ ] the projects section laid out with **CSS Grid**
- [ ] responsive: sensible on phone (≤ 400px), tablet (~768px), desktop (≥ 1200px); nav and projects grid both adapt
- [ ] `<meta viewport>` present; no horizontal scrollbar at any width
- [ ] images never overflow their containers

Required JavaScript (`app.js`, loaded with `defer` or at end of body):
- [ ] a light/dark theme toggle that persists visually for the session (class on `<body>`)
- [ ] the contact form: on submit, `preventDefault` and show an inline "thank you, {name}" confirmation
- [ ] **one more** interaction of your choice: a projects filter, a "back to top" button that appears on scroll, an accordion for project details, a mobile nav toggle, an image lightbox, or a typing/count-up animation in the hero

Definition of done:
- [ ] Opens with Live Server with zero Console errors
- [ ] Every nav link jumps to the right section
- [ ] Resize from 320px to 1440px — nothing breaks, overlaps, or overflows
- [ ] A stranger could read it and know who you are and what you can do
- [ ] All code is your own, typed by hand, and you can explain any line if asked

### Milestones (pace yourself over the week)

1. **Content first, no CSS.** Full semantic HTML with real text and placeholder images. It should be readable and correctly structured with zero styling.
2. **Mobile CSS.** Style the single-column phone layout: type, colour, spacing, images. No layout tricks yet.
3. **Layout + responsive.** Add Flexbox nav, Grid projects, media queries / fluid units for tablet and desktop.
4. **JavaScript.** Theme toggle, form handler, your third interaction.
5. **Polish + test.** Cross-width testing, Console clean-up, `alt` text pass, contrast check, spacing consistency, remove dead code.

### Variant briefs — extra reps, pick any

**8.2 — Photographer portfolio** ⭐⭐⭐ — hero is a full-bleed image; `#projects` becomes a masonry-ish responsive gallery (Grid `auto-fit`/`minmax`); JS lightbox to view photos large.
**8.3 — Small-business landing page** ⭐⭐⭐ — for a made-up café/gym/salon: hero with CTA, services grid, hours table, testimonials row (Flexbox), map placeholder, contact form. JS: mobile nav toggle + an FAQ accordion.
**8.4 — Product / app landing page** ⭐⭐⭐ — features grid, a pricing section (3 tiers, Flexbox, middle one featured), FAQ accordion, email capture form. JS: pricing "monthly/yearly" toggle that updates the prices, plus form handler.
**8.5 — Recipe site** ⭐⭐⭐ — a homepage grid of recipe cards + one recipe detail page (semantic `<article>`, ingredients list, ordered steps, a servings scaler in JS that multiplies the ingredient amounts).
**8.6 — Link-in-bio page** ⭐⭐ — single screen, centred column, avatar, name, bio, a stack of big link buttons, a theme toggle, and a "copy my email" button (JS writes to clipboard or just reveals it). Great if you're short on time.

### Stretch goals (only after the core brief is done)

**8.7 — Deploy it** ⭐⭐ — put the site on the web with GitHub Pages (or Netlify drop). Now you have a real URL to share.
**8.8 — Multi-page** ⭐⭐⭐ — split into `index.html`, `projects.html`, `project-detail.html`, `contact.html` with a shared header/footer you copy consistently. Each project card links to a detail page.
**8.9 — Real content pass** ⭐⭐ — replace every "Lorem ipsum" and placeholder image with real writing and real (or properly-licensed) images. Write actual project case studies: problem, what you built, what you learned.
**8.10 — Accessibility pass** ⭐⭐⭐ — keyboard-only navigation works, focus states are visible, colour contrast passes, headings are in order, form errors are announced in text (not just colour), every image has meaningful `alt`.
**8.11 — Performance & polish** ⭐⭐ — compress images, remove unused CSS, add a favicon, set the `<title>` and a `<meta name="description">`, check it loads fast.

### Peer-review rubric (use on your own work and a classmate's)

Score each 0–2 (0 = missing, 1 = partial, 2 = solid):

| Area | Check |
|---|---|
| Semantics | Landmarks used correctly; headings in order; form labels linked |
| CSS structure | External only; consistent type + spacing scale; `border-box` |
| Layout | Flexbox and Grid both used, each where appropriate |
| Responsive | Works 320–1440px; no overflow; nav + grid adapt |
| JavaScript | Theme toggle works; form handled without reload; 3rd interaction works; no Console errors |
| Content | Clear who/what; real-ish copy; all images have `alt` |
| Code quality | Readable, indented, no dead code, hand-written, author can explain it |

14 = ship it. 10–13 = one more polish pass. < 10 = revisit the weakest row against that class's assignments.

### Wrap-up written reflection

1. Which class's material was hardest, and how did you get past it?
2. Show one bug that took you more than 20 minutes. What was the actual cause?
3. Where did you use Flexbox vs Grid, and why each?
4. What would you add or change with another week?
5. What do you want to learn next (frameworks, deeper JS, CSS frameworks)?

---
---

# Spaced-review sets

Repetition beats re-reading. Once a week, do one review set from a **past** class, from a blank file, without notes.

**Review A (after Class 3):**
- Rebuild the About Me page: semantic HTML + a full stylesheet, from scratch, in 45 minutes. Compare to your saved version.

**Review B (after Class 5):**
- From scratch in 60 minutes: a semantic page with a Flexbox navbar, a Grid card section (3 cards), responsive to one media query. Any topic.

**Review C (after Class 7):**
- From scratch in 75 minutes: the above, plus a working theme toggle and a form that shows a thank-you message without reloading.

**Daily 10-minute drills (rotate):**
- Type the HTML skeleton + a semantic body outline from memory.
- Write `display: flex` + centre-a-box from memory.
- Write a `repeat(auto-fit, minmax(…))` responsive grid from memory.
- Write a `for` loop that sums an array from memory.
- Write `querySelector` + `addEventListener("click", …)` that changes text, from memory.

**Flashcard prompts (say the answer out loud):**
- Difference between `<section>` and `<article>`?
- Four parts of the box model, inside out?
- What does `box-sizing: border-box` do?
- Container vs item properties in Flexbox?
- `fr` unit — what is it?
- `auto-fit` vs `auto-fill`?
- `let` vs `const`?
- `==` vs `===`?
- `textContent` vs `innerHTML`?
- What does `event.preventDefault()` do?
