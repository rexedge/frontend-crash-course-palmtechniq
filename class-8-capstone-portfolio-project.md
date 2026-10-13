# Class 8: Capstone — Portfolio Project
### A self-guided read-through — this class is one build, in five milestones. Finish each milestone before you start the next. Have your 🧵 files from Classes 1–7 nearby.

---

## 1. Recap: Where We Are

Seven classes ago you typed `<h1>Hello, World!</h1>` into an empty file. Since then:

- **Class 1** — HTML: headings, paragraphs, links, images, lists.
- **Class 2** — structure that means something: `<header>`, `<nav>`, `<main>`, `<section>`, and forms the browser can check.
- **Class 3** — CSS: selectors, the box model, colour, and type.
- **Class 4** — Flexbox: things in a row, spaced and lined up.
- **Class 5** — Grid, and pages that work on a phone.
- **Class 6** — JavaScript: variables, decisions, loops, functions.
- **Class 7** — the DOM: find, listen, change.

Today there is no new language and no new layout system. There is one small new idea (a link that jumps down the page), and then one job: **put it all together**. You're going to build a portfolio — one page that says who you are, shows what you've made, and lets someone get in touch.

No single line in this class is hard. The hard part is size. This page has three files, a dozen groups of CSS rules, and three JavaScript features living side by side. So the real skill today is working in order, and keeping things tidy as the page grows.

---

## 2. The Brief: What You're Building

One page, seven parts:

```
PHONE                        WIDE SCREEN
+----------------------+     +--------------------------------------------+
| Name          [Dark] |     | Name      About Skills Projects    [Dark]  |
| About Skills ...     |     +--------------------------------------------+
+----------------------+     |           Hi, I'm ...  (the hero)          |
| Hi, I'm ...          |     |             [See my projects]              |
| [See my projects]    |     +--------------------------------------------+
+----------------------+     | About me                                   |
| About me             |     | [photo]   a few sentences about you        |
| [photo]              |     +--------------------------------------------+
| a few sentences      |     | Skills    [skill] [skill] [skill] [skill]  |
+----------------------+     +--------------------------------------------+
| Skills               |     | Projects  [All] [HTML] [CSS] [JavaScript]  |
| [skill] [skill]      |     | [card]        [card]        [card]         |
+----------------------+     | [card]        [card]        [card]         |
| Projects             |     +--------------------------------------------+
| [card]               |     | Contact   (the form)                       |
| [card]               |     +--------------------------------------------+
| ...                  |     | footer                                     |
+----------------------+     +--------------------------------------------+
| Contact (the form)   |
+----------------------+
| footer               |
+----------------------+
```

### Requirements

**Structure**
- [ ] A `<header>` with your name and a `<nav>` whose links jump to the sections of the page
- [ ] A **hero** — the big opening block at the top of a page: one `<h1>`, a one-line pitch, and a link to your projects
- [ ] An **About** section with a short bio and a photo
- [ ] A **Skills** section
- [ ] A **Projects** section with **at least three** cards: a picture, a title, a description, and a link
- [ ] A **Contact** section with a form: a label on every field, and validation attributes
- [ ] A `<footer>` with a copyright line and two or three links

**CSS**
- [ ] One external `style.css`. No `style="…"` attributes in the HTML
- [ ] The `box-sizing` reset, and the `img` reset
- [ ] A short list of font sizes and a short list of spacing values, used everywhere
- [ ] The header laid out with **Flexbox**; the project cards laid out with **Grid**
- [ ] Mobile-first: it works at 320px, and gets better as the screen gets wider
- [ ] No horizontal scrollbar at any width

**JavaScript**
- [ ] A light / dark **theme toggle**
- [ ] The contact form says **thank you**, with the visitor's name, and without reloading
- [ ] **One more** interaction. This lesson builds a projects filter; Section 10 lists other choices
- [ ] No red in the Console

**And**
- [ ] A stranger could read it and know who you are and what you can do
- [ ] Every line is typed by hand, and you can explain any of them

### How to use this lesson

Sections 5 to 9 build a complete example, for a made-up student called Ada. Build it, and get every part working. Then Section 10 is where it becomes **yours**: your words, your colours, your projects, your choices. The example is a worked answer, not the thing you hand in.

---

## 3. Before You Type: Plan and Gather

Ten minutes of planning saves an hour of rearranging.

### Write the words first
Open a plain text file and write, in ordinary sentences:

- your name, and **one line** that says what you do
- three or four sentences about you
- six to eight skills
- **at least three projects**, each with a title and one sentence about it

Words are the hard part of a portfolio, so do them while your head is clear. The code is easier when the content already exists.

### Your projects already exist
You have spent seven classes building them. Any finished page will do. These are good candidates:

| Project | From | What it shows |
|---|---|---|
| About Me page | Classes 1–3 | Semantic HTML and CSS |
| Contact form | Classes 2–5 | Forms, validation, a responsive layout |
| Navbar and feature cards | Class 4 | Flexbox |
| Responsive photo gallery | Class 5 | Grid and media queries |
| Calculator toolkit | Class 6 | Functions and logic |
| To-do list, or any Class 7 build | Class 7 | The DOM and events |

### Set up the folder

```
portfolio/
  index.html
  style.css
  app.js
  images/        <- your photo, and a screenshot of each project
  projects/      <- a copy of each finished project, one folder each
    about-me/
    gallery/
    ...
```

Copy each finished project **into** `projects/`. Then every link on your portfolio points at something inside the `portfolio` folder, and the whole site can be moved, zipped, or put online in one piece.

Put one line in `app.js` straight away:

```js
console.log("app.js loaded");
```

It's the reload detector from Class 7, and it also proves the script is connected.

### Three working rules

1. **One milestone at a time.** Don't start styling while the HTML is half-written. Don't start the JavaScript while the layout is broken.
2. **Save often, check the browser after every change** — the page **and** the Console.
3. **Keep a save point.** When a milestone works, copy the whole `portfolio` folder and add the milestone to the copy's name: `portfolio-after-m2`. If you break something badly later on, you have a version that worked.

### Practice Now
Write your content file. Make the folder and its three files. Then sketch your page on paper, twice: once as a phone, once as a wide screen. Boxes and labels are enough.

✅ **Checkpoint:** You have words, a folder, and a sketch — and you haven't written any code yet.

---

## 4. One New Thing: Links That Jump Down the Page

You've used an `id` for three jobs already: connecting a `<label>` to its input (Class 2), styling one element (Class 3), and finding an element from JavaScript (Class 7). Here is a fourth. An `id` is also a **place a link can go**.

```html
<nav>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
</nav>

<section id="about">
    <h2>About me</h2>
</section>

<section id="contact">
    <h2>Contact</h2>
</section>
```

Click `Contact`, and the page jumps down until the section with `id="contact"` is at the top of the window. The address bar gains `#contact` on the end. Nothing is loaded: it's the same page, in a new position.

The rules:

- **The `#` goes in the `href`, not in the `id`.** `href="#contact"` points at `id="contact"`. It's the same `#` that means "id" in CSS and in `querySelector`.
- **They must match exactly, capitals included.** `href="#Contact"` does not find `id="contact"`. The click does nothing at all, and there is no error to tell you why.
- **Leave the `#` out, and it's an ordinary link.** `href="contact"` tries to load a page called `contact`, which doesn't exist.
- **A `#` on its own goes to the top of the page.** That's why the placeholder links you wrote in Class 4, `<a href="#">`, never seemed to go anywhere.
- **An `id` must be unique.** Only one element on the page can be `id="contact"`.

### Practice Now
Make a page with a `<nav>` and three `<section>`s, each with an `id` and enough text to fill the screen (or add `min-height: 100vh` to `section` in a stylesheet). Link to all three. Then break one link on purpose, by changing a capital letter, and see for yourself that nothing happens.

✅ **Checkpoint:** You can write a link that jumps to any part of a page, and you know the two ways it silently fails.

---

## 5. Milestone 1 — Content First

Write the whole page in HTML, with real words, before a single line of CSS. This is the page a screen reader hears and a search engine reads. If it makes sense now, it will make sense to everyone.

**`index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Ada Lovelace — Frontend Developer</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header class="site-header" id="top">
        <p class="brand">Ada Lovelace</p>

        <nav class="site-nav">
            <a href="#about">About</a>
            <a href="#skills">Skills</a>
            <a href="#projects">Projects</a>
            <a href="#contact">Contact</a>
        </nav>

        <button type="button" id="theme-toggle">🌙 Dark</button>
    </header>

    <main>
        <section class="hero">
            <h1>Hi, I'm Ada. I build websites by hand.</h1>
            <p class="pitch">I'm a new frontend developer. I write HTML, CSS, and JavaScript from a blank file, with no templates and no frameworks.</p>
            <a href="#projects" class="button">See my projects</a>
        </section>

        <section id="about">
            <h2>About me</h2>

            <div class="about-layout">
                <img src="https://picsum.photos/seed/ada/400/400" alt="Placeholder for a photo of me">

                <div>
                    <p>I'm originally from Lagos, and I like solving puzzles. Eight classes ago I had never written a line of code.</p>
                    <p>Since then I have built every page on this site myself, typing each line by hand. I care about pages that are easy to read, that work on a phone, and that still make sense to someone who can't see the screen.</p>
                </div>
            </div>
        </section>

        <section id="skills">
            <h2>Skills</h2>

            <ul class="skills">
                <li>Semantic HTML</li>
                <li>Forms and validation</li>
                <li>The box model</li>
                <li>Flexbox</li>
                <li>CSS Grid</li>
                <li>Responsive design</li>
                <li>JavaScript</li>
                <li>The DOM and events</li>
            </ul>
        </section>

        <section id="projects">
            <h2>Projects</h2>

            <div class="filters">
                <button type="button" class="filter active">All</button>
                <button type="button" class="filter">HTML</button>
                <button type="button" class="filter">CSS</button>
                <button type="button" class="filter">JavaScript</button>
            </div>

            <p id="project-count">Showing 6 of 6 projects</p>

            <div class="projects">
                <article class="project">
                    <img src="https://picsum.photos/seed/about-me/600/400" alt="Placeholder for a screenshot of my About Me page">
                    <h3>About Me page</h3>
                    <p class="tag">HTML</p>
                    <p>My first web page, rebuilt with semantic tags so that every part of it says what it is.</p>
                    <a href="projects/about-me/index.html">View the About Me page</a>
                </article>

                <article class="project">
                    <img src="https://picsum.photos/seed/contact/600/400" alt="Placeholder for a screenshot of my contact form">
                    <h3>Contact form</h3>
                    <p class="tag">HTML</p>
                    <p>A form with a label on every field, and validation that the browser does for me.</p>
                    <a href="projects/contact/index.html">View the contact form</a>
                </article>

                <article class="project">
                    <img src="https://picsum.photos/seed/navbar/600/400" alt="Placeholder for a screenshot of my navbar and feature cards">
                    <h3>Navbar and feature cards</h3>
                    <p class="tag">CSS</p>
                    <p>A navigation bar and three equal cards, laid out with Flexbox.</p>
                    <a href="projects/navbar-and-cards/index.html">View the navbar and cards</a>
                </article>

                <article class="project">
                    <img src="https://picsum.photos/seed/gallery/600/400" alt="Placeholder for a screenshot of my photo gallery">
                    <h3>Responsive photo gallery</h3>
                    <p class="tag">CSS</p>
                    <p>Twelve photos in a grid that goes from one column on a phone to five on a wide screen.</p>
                    <a href="projects/gallery/index.html">View the gallery</a>
                </article>

                <article class="project">
                    <img src="https://picsum.photos/seed/calculator/600/400" alt="Placeholder for a screenshot of my calculator toolkit">
                    <h3>Calculator toolkit</h3>
                    <p class="tag">JavaScript</p>
                    <p>Eight small functions that add, divide, round, and average. Open the Console to see them run.</p>
                    <a href="projects/calculator/index.html">View the calculator toolkit</a>
                </article>

                <article class="project">
                    <img src="https://picsum.photos/seed/todo/600/400" alt="Placeholder for a screenshot of my to-do list">
                    <h3>To-do list</h3>
                    <p class="tag">JavaScript</p>
                    <p>Add a task, tick it off, or delete it. Every item is built by JavaScript.</p>
                    <a href="projects/to-do-list/index.html">View the to-do list</a>
                </article>
            </div>
        </section>

        <section id="contact">
            <h2>Contact</h2>
            <p>Have a project in mind, or just want to say hello? Send me a message.</p>

            <form id="contact-form">
                <div class="field">
                    <label for="name">Full name</label>
                    <input type="text" id="name" name="name" required>
                </div>

                <div class="field">
                    <label for="email">Email address</label>
                    <input type="email" id="email" name="email" required>
                </div>

                <div class="field">
                    <label for="message">Message</label>
                    <textarea id="message" name="message" rows="5" required minlength="10"></textarea>
                </div>

                <button type="submit">Send message</button>
            </form>

            <p id="thanks" class="thanks hidden"></p>
        </section>
    </main>

    <footer class="site-footer">
        <p>© 2026 Ada Lovelace. Built by hand, with no frameworks.</p>

        <div class="footer-links">
            <a href="https://github.com/">GitHub</a>
            <a href="https://www.linkedin.com/">LinkedIn</a>
            <a href="#top">Back to top</a>
        </div>
    </footer>

    <script src="app.js"></script>
</body>
</html>
```

Type it by hand — don't paste. It's long, so go a section at a time: save, look at the browser, then start the next section.

### What to notice

- **One `<h1>`**, in the hero. Every section has an `<h2>`, and every project card has an `<h3>`. Read only the headings, top to bottom, and you get the outline of the page.
- **Every image has an `alt`.** While the pictures are placeholders, the `alt` says so honestly. When you swap in your own, describe what's really in them.
- **Every link says where it goes.** `View the gallery`, not `Click here`. Someone who hears only the list of links should still know which is which.
- **Four of the ids are places to jump to**: `about`, `skills`, `projects`, and `contact` match the four links in the `<nav>`. A fifth, `top`, sits on the header for the `Back to top` link in the footer.
- **The picture addresses** use `picsum.photos/seed/…`. The word after `seed/` picks the photo, so each card keeps the same picture every time you reload.
- **A few things are waiting for JavaScript**: the theme button, the four filter buttons, the line that says `Showing 6 of 6 projects`, and an empty paragraph with the class `hidden`. They do nothing yet. They're in the HTML now so that you can style them along with everything else.

### Test it

| Do this | You should see |
|---|---|
| Open `index.html` with Live Server | A plain page in the browser's default font: black on white, everything in one column |
| Look at the Console | `app.js loaded`, and no red |
| Click each of the four links at the top | The page jumps to that section, and the address gains `#about`, `#skills`, `#projects`, or `#contact` |
| Click `Back to top`, at the bottom | You're back at the top |
| Narrow the window to phone width | The photos are wider than the screen. That's expected: Milestone 2 fixes it |
| Click `🌙 Dark`, or a filter button | Nothing happens. That's expected too |

✅ **Checkpoint:** With no CSS at all, your page can be read from top to bottom and makes complete sense. Copy the folder as `portfolio-after-m1`.

---

## 6. Milestone 2 — Base Styles

Now the look — but only the parts that apply **everywhere**: the resets, the fonts, the colours, the spacing, and the form fields. No layout yet. At the end of this milestone the page will still be one long column, but a good-looking one.

### Decide your scales first
A page looks "designed" when it uses a few sizes, again and again, instead of a new number every time. So before any rules, choose:

- a **type scale** — four or five font sizes
- a **spacing scale** — four or five distances for every margin, padding, and gap
- a **palette** — five or six colours

Write them in a comment at the top of the stylesheet. From then on, that comment is your menu: when you need a size, you pick one from it. If you find yourself typing `13px` or `22px`, stop and pick the nearest value on the menu.

**`style.css`** — the first part

```css
/*
    Portfolio styles

    Type scale:     0.875rem   1rem   1.25rem   1.75rem   (the h1 is fluid)
    Spacing scale:  8px   16px   24px   48px
    Colours:        text #222222      page #f7f7f5      surface #ffffff
                    border #dddddd    accent #1a56db
*/

/* ---------- Resets ---------- */

*, *::before, *::after {
    box-sizing: border-box;
}

img {
    max-width: 100%;
    height: auto;
    display: block;
}

/* ---------- Base: the light theme is the default ---------- */

body {
    margin: 0;
    font-family: system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    font-size: 1rem;
    line-height: 1.6;
    color: #222222;
    background-color: #f7f7f5;
}

h1,
h2,
h3 {
    margin: 0 0 16px 0;
    line-height: 1.2;
}

h1 {
    font-size: clamp(2rem, 1.25rem + 4vw, 3.25rem);
}

h2 {
    font-size: 1.75rem;
}

h3 {
    font-size: 1.25rem;
}

p {
    margin: 0 0 16px 0;
}

a {
    color: #1a56db;
}

main {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 clamp(16px, 5vw, 48px);
}

section {
    padding: 48px 0;
}

/* ---------- Base: form fields and buttons ---------- */

label {
    display: block;
    margin-bottom: 8px;
    font-weight: 700;
}

input,
textarea,
button {
    font-family: system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    font-size: 1rem;
}

input,
textarea {
    width: 100%;
    padding: 8px;
    border: 1px solid #999999;
    color: #222222;
    background-color: #ffffff;
}

button,
.button {
    display: inline-block;
    padding: 8px 16px;
    border: 1px solid #1a56db;
    font-weight: 700;
    color: #ffffff;
    background-color: #1a56db;
    text-decoration: none;
    cursor: pointer;
}

/* The quieter buttons: the theme toggle and the project filters */
#theme-toggle,
.filter {
    border: 1px solid #999999;
    color: #222222;
    background-color: #ffffff;
}
```

### What to notice

- **Both resets come first**: `box-sizing` from Class 3, and the `img` reset from Class 5. That one `img` rule is what stops the photos sticking out past a phone screen.
- **The comma means "and"** (Class 3). `h1, h2, h3` is one rule for three selectors. `button, .button` gives real buttons and the hero **link** the same look, because the link has `class="button"`.
- **Why the theme and filter buttons aren't blue.** `button` and `.filter` both set a `background-color`. `.filter` wins, because a class is more specific than an element (Class 3). `#theme-toggle` wins for the same reason: an `id` beats both.
- **Every margin and padding is 8, 16, 24, or 48 pixels.** Check for yourself. (The side padding on `main` slides between 16 and 48 with `clamp()`.)
- **Form fields don't inherit your font.** That's why `input, textarea, button` get the `font-family` again.

### Test it

| Do this | You should see |
|---|---|
| Save, and look at the page | A warm off-white page, a clean font, and a centred column with space at the sides |
| Look at the header | Still three plain lines at the very left edge. It has no rules of its own yet |
| Look at the buttons | `See my projects` and `Send message` are solid blue. The theme and filter buttons are white with a grey border |
| Narrow the window to 375px | No photo is wider than the screen any more |
| Look at the skills | Still a bulleted list. That's right: no layout yet |

✅ **Checkpoint:** A tidy one-column page, at any width, with no layout CSS at all. Copy the folder as `portfolio-after-m2`.

---

## 7. Milestone 3 — Layout and Responsive

Now each part of the page gets its own rules, in the same order as the HTML: header, hero, about, skills, projects, contact, footer. Then one media query at the end.

Write the phone layout first. That's mobile-first, from Class 5: the base rules describe a narrow screen, and the media query **adds** to them when there's room.

**`style.css`** — the second part. Add it underneath the first.

```css
/* ---------- Header ---------- */

.site-header {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    gap: 16px;
    padding: 16px clamp(16px, 5vw, 48px);
    background-color: #ffffff;
    border-bottom: 1px solid #dddddd;
}

.brand {
    margin: 0;
    font-size: 1.25rem;
    font-weight: 700;
}

/* Phones: the links get a row of their own, under the name and the button */
.site-nav {
    order: 1;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
}

.site-nav a {
    font-weight: 700;
    text-decoration: none;
}

/* ---------- Hero ---------- */

.hero {
    text-align: center;
}

.pitch {
    max-width: 36rem;
    margin: 0 auto 24px auto;
    font-size: 1.25rem;
}

/* ---------- About ---------- */

.about-layout {
    display: grid;
    gap: 24px;
}

.about-layout img {
    width: 240px;
    aspect-ratio: 1 / 1;
    object-fit: cover;
}

/* ---------- Skills ---------- */

.skills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin: 0;
    padding: 0;
    list-style: none;
}

.skills li {
    padding: 8px 16px;
    background-color: #ffffff;
    border: 1px solid #dddddd;
}

/* ---------- Projects ---------- */

.filters {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 16px;
}

.projects {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 24px;
}

.project {
    display: flex;
    flex-direction: column;
    padding: 16px;
    background-color: #ffffff;
    border: 1px solid #dddddd;
}

.project img {
    width: 100%;
    margin-bottom: 16px;
    aspect-ratio: 3 / 2;
    object-fit: cover;
}

.project h3 {
    margin-bottom: 8px;
}

.tag {
    margin-bottom: 8px;
    font-size: 0.875rem;
    font-weight: 700;
    color: #555555;
}

.project a {
    margin-top: auto;
    font-weight: 700;
}

/* ---------- Contact ---------- */

#contact-form {
    max-width: 32rem;
}

.field {
    margin-bottom: 16px;
}

/* ---------- Footer ---------- */

.site-footer {
    padding: 24px clamp(16px, 5vw, 48px);
    text-align: center;
    background-color: #ffffff;
}

.footer-links {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 16px;
}

/* ---------- From 700px: there is room to spread out ---------- */

@media (min-width: 700px) {
    .site-nav {
        order: 0;
        width: auto;
    }

    .about-layout {
        grid-template-columns: 240px 1fr;
    }
}
```

### Five decisions worth understanding

**1. The header is one flex row that's allowed to wrap.** On a phone there isn't room for the name, four links, and a button side by side. So the nav gets `width: 100%`, which forces it onto a line of its own, and `order: 1`, which moves it after the button (everything else is `order: 0`). The result is two neat rows: name and button, then links. From 700px, the media query puts both values back, and `justify-content: space-between` spreads the three items across one row.

That's `order` used the way Class 4 said to use it: a small visual tweak, with the HTML still in a sensible order.

**2. Flexbox for rows, Grid for the grid.** The header, the skills, the filter buttons, and the footer links are all "things in a line that may wrap": Flexbox. The project cards need columns that line up in every row: Grid.

**3. The cards use `auto-fill`, not `auto-fit`.** In Class 5 you saw the difference: with `auto-fit`, a few cards stretch to fill the whole row. That matters here, because in Milestone 4 a filter will hide some cards. With `auto-fill`, the two cards that remain keep their normal width instead of ballooning into two huge slabs.

**4. Each card is its own small flex column.** `margin-top: auto` on the link pushes it to the bottom of the card, so the links line up across a row even when one description is longer. That's the pinned-link pattern from Class 4.

**5. There is only one media query.** The header and the About section need one, because they change shape. The cards don't: `auto-fill` and `minmax()` work out the columns by themselves.

`list-style: none` on the skills takes the bullets off the list. You met it in the Class 3 assignments.

### Test it
Switch on the device toolbar in dev tools, and check these widths:

| Width | What you should see |
|---|---|
| 320px | Nothing sticks out, and there's no horizontal scrollbar. Name and theme button on one row; the four links on a row beneath |
| 375px | The same layout. One column of project cards. The photo above the bio |
| 768px | Name, links, and button on **one** row. The photo **beside** the bio. Two columns of cards |
| 1024px | Three columns of cards |
| 1280px | Three columns still, in a centred column that stops growing at 1100px |

Then drag the window slowly from narrow to wide. Find the exact width where the header changes. It should be 700px.

✅ **Checkpoint:** A responsive page with a Flexbox header and a Grid of cards, and nothing clickable works yet. Copy the folder as `portfolio-after-m3`.

---

## 8. Milestone 4 — JavaScript

Three features. Build them **one at a time**, and get each one working before you start the next.

### First, the classes JavaScript will switch
Your JavaScript sets no colours and no sizes. It only adds and removes class names. So every one of those looks has to exist in the CSS first.

**`style.css`** — the third part. Add it at the very end.

```css
/* ---------- Classes that JavaScript switches ---------- */

.active {
    border: 1px solid #222222;
    color: #ffffff;
    background-color: #222222;
}

.thanks {
    max-width: 32rem;
    padding: 16px;
    border: 1px solid #5aa46b;
    background-color: #e6f4ea;
}

/* Dark theme: only the colours change */
.dark {
    color: #eeeeee;
    background-color: #121212;
}

.dark a {
    color: #8ab4f8;
}

.dark .button {
    color: #ffffff;
}

.dark .site-header {
    background-color: #1e1e1e;
    border-bottom: 1px solid #333333;
}

.dark .site-footer {
    background-color: #1e1e1e;
}

.dark .project,
.dark .skills li {
    background-color: #1e1e1e;
    border: 1px solid #333333;
}

.dark .tag {
    color: #bbbbbb;
}

.dark input,
.dark textarea,
.dark #theme-toggle,
.dark .filter {
    border: 1px solid #555555;
    color: #eeeeee;
    background-color: #1e1e1e;
}

.dark .active {
    border: 1px solid #eeeeee;
    color: #121212;
    background-color: #eeeeee;
}

.dark .thanks {
    background-color: #1e3a29;
}

/* Keep this last, so it wins over any display rule above it */
.hidden {
    display: none;
}
```

Three rules in there are fixing problems you would otherwise hit:

- **`.dark .button`** — without it, `.dark a` turns the hero link's white text pale blue, on a blue button. `.dark a` is a class plus an element, so it beats `.button` on its own. Adding `.dark` in front of `.button` makes that one stronger again.
- **`.dark .active`** — without it, `.dark .filter` would paint the chosen filter the same as the others. It has to come **after** `.dark .filter`, because the two are equally strong and the later one wins.
- **`.hidden` is last** — a project card is `display: flex`. If `.hidden` came before `.project` in the file, the card's own `display` would win and the card would never disappear.

The dark theme needs no new ideas: it's a class on `<body>`, plus descendant selectors.

### Part 1: the theme toggle

**`app.js`**

```js
console.log("app.js loaded");

// ---------- 1. The theme toggle ----------

const themeToggle = document.querySelector("#theme-toggle");

themeToggle.addEventListener("click", () => {
    document.body.classList.toggle("dark");

    if (document.body.classList.contains("dark")) {
        themeToggle.textContent = "☀️ Light";
    } else {
        themeToggle.textContent = "🌙 Dark";
    }
});
```

This is the toggle from Class 7, unchanged. Save, click the button, and check **every** part of the page in the dark: the header, the skills, the cards, the form fields, the footer. A dark theme with one white box left in it is the most common thing to miss.

### Part 2: the contact form
Add this underneath:

```js
// ---------- 2. The contact form ----------

const contactForm = document.querySelector("#contact-form");
const nameInput = document.querySelector("#name");
const thanks = document.querySelector("#thanks");

contactForm.addEventListener("submit", (event) => {
    event.preventDefault();

    const visitorName = nameInput.value.trim();

    thanks.textContent = `✅ Thanks, ${visitorName}. I'll reply as soon as I can.`;

    contactForm.classList.add("hidden");
    thanks.classList.remove("hidden");
});
```

Also from Class 7. Be honest with yourself about what it does: this form **doesn't send anything anywhere**. Sending a message needs a server, which is outside this course. What you've built is the half that runs in the browser.

### Part 3: the projects filter
This one is new, but every piece of it is something you already know. Add it underneath:

```js
// ---------- 3. The projects filter ----------

const filters = document.querySelectorAll(".filter");
const projects = document.querySelectorAll(".project");
const tags = document.querySelectorAll(".project .tag");
const projectCount = document.querySelector("#project-count");

function showProjects(wanted) {
    let shown = 0;

    projects.forEach((project, i) => {
        if (wanted === "All" || tags[i].textContent.trim() === wanted) {
            project.classList.remove("hidden");
            shown++;
        } else {
            project.classList.add("hidden");
        }
    });

    projectCount.textContent = `Showing ${shown} of ${projects.length} projects`;
}

filters.forEach((filter) => {
    filter.addEventListener("click", () => {
        filters.forEach((other) => {
            other.classList.remove("active");
        });

        filter.classList.add("active");
        showProjects(filter.textContent.trim());
    });
});

showProjects("All");
```

Read it in three pieces.

**The lists.** `projects` is every card. `tags` is the small label inside every card. Each card has exactly one label, so the two lists are the same length and in the same order: `tags[2]` is the label that belongs to `projects[2]`. Those are the "partners by index" from Class 7.

**`showProjects(wanted)`.** One function that makes the page match one word. It goes through the cards. A card stays if the word is `All`, **or** if its label says exactly that word. Otherwise it gets `hidden`. Along the way it counts the cards it kept, and at the end it writes the count onto the page. That's a function with a parameter, a loop, an `if` with `||`, a counter, and a template literal — most of Class 6 in one small function.

**The buttons.** Each filter button gets a click listener. "Clear them all, then mark the one" moves the `active` class. Then the button's own text is passed to `showProjects`. That's the neat part: the word on the button **is** the word being looked for, so a new category needs no new JavaScript — only a new button, and cards with that label.

The last line calls `showProjects("All")` once, as the page loads, so that the count is right from the start.

### Test it

| Do this | You should see |
|---|---|
| Load the page | `app.js loaded` in the Console, once. `Showing 6 of 6 projects`. The `All` button is dark |
| Click `🌙 Dark` | Every part of the page turns dark. The button says `☀️ Light`. In the Elements panel, `<body>` has `class="dark"` |
| Click it again | Back to light |
| Click `CSS` | `Showing 2 of 6 projects`. Only "Navbar and feature cards" and "Responsive photo gallery" remain, at their normal width. `CSS` is the dark button now |
| Click `JavaScript`, then `HTML` | Two different cards each time |
| Click `All` | All six are back |
| Click `Send message` with the form empty | The browser's own "fill in this field" bubble. Nothing else changes |
| Fill in a name, an email, and a message of at least 10 characters, and send | The form disappears. A green box says `✅ Thanks, Ada Lovelace. I'll reply as soon as I can.` with the name you typed |
| Look at the Console and the address bar | `app.js loaded` appears only **once**, and there's no `?name=…` on the address. The page did not reload |

### Now break it, then fix it
Do these one at a time, and undo each one afterwards. Each is a mistake you're likely to make by accident on your own portfolio.

1. In `style.css`, move the `.hidden` rule up, so that it sits above `.project`. Click `CSS`. Read the count, then look at the cards.
2. In `index.html`, change one `<p class="tag">JavaScript</p>` to `Javascript`. Click the `JavaScript` filter.
3. In `app.js`, change `"#theme-toggle"` to `"#themeToggle"`. Reload. Try the theme button, then a filter, then send the form.

The third one is the important one. **One red error stops the whole file.** The script gives up at the line that failed, so nothing below it ever runs: no filter, and no `preventDefault` — which is why the form reloads the page again.

✅ **Checkpoint:** Three features, about 65 lines of JavaScript, and not one colour or size in it. Copy the folder as `portfolio-after-m4`.

---

## 9. Milestone 5 — Polish and Test

The page works. This is the milestone that makes it look like somebody cared.

**Test every width**
- [ ] 320px, 375px, 768px, 1024px, 1280px, 1440px: nothing overlaps, and nothing sticks out
- [ ] No horizontal scrollbar at any of them
- [ ] Do it all again **in dark mode**

**Test every click**
- [ ] Every link in the nav and the footer goes somewhere real
- [ ] Every project link opens that project
- [ ] The Console is clean: no red, and no leftover `console.log("clicked")` from debugging

**Read it like a stranger**
- [ ] The `<title>` says who you are. It's what shows on the browser tab
- [ ] Read only the headings. Do they outline the page?
- [ ] Read every `alt` out loud. Does it describe the picture?
- [ ] No "Lorem ipsum", and no "Placeholder", anywhere

**Read the code like a stranger**
- [ ] Every size and distance comes from your scales
- [ ] No rule is in the stylesheet twice, and no rule is left over from an idea you dropped
- [ ] The indentation is consistent in all three files
- [ ] No `style="…"` in the HTML, and no colours in the JavaScript

**The best test of all:** hand your phone to someone who has never seen the page. Say nothing. Watch what they tap, where they hesitate, and what they miss. You'll learn more in two minutes than in an hour of looking at it yourself.

### Practice Now
Go down the list and fix what you find. Expect to find something: everybody does.

✅ **Checkpoint:** Every box above is ticked, in both themes.

---

## 10. Make It Yours

So far you have Ada's portfolio. Now turn it into yours. All of these must change:

- **The words.** Your name, your pitch, your bio, your skills — from the content file you wrote in Section 3.
- **The projects.** Your own finished pages, copied into `projects/`, with a screenshot of each in `images/`. Most computers have a screenshot shortcut: `Windows + Shift + S` on Windows, `Cmd + Shift + 4` on a Mac. Write a real `alt` for each one, and change the filter buttons and the tags to categories that suit your work.
- **The look.** Choose your own palette and rewrite the comment at the top of `style.css`. Then change every colour to match — in **both** themes.
- **At least one layout decision.** Put the photo on the right. Give the hero a background colour. Make the skills a grid. Move the theme button into the footer. Anything, as long as you decided it.

### Your third interaction
The brief asks for one more interaction "of your choice", and the filter was mine. Keep it if it suits your projects, or swap it for one of these. You've already built every one of them:

| Interaction | What it is | Where you built it |
|---|---|---|
| **Projects filter** | Buttons that show one category of card | This lesson, Section 8 |
| **Project details** | A `More details` button on each card that shows and hides an extra paragraph | Class 7, Assignment 12 |
| **Mobile menu** | A `Menu` button that shows and hides the nav on a phone | A toggle (Class 7) plus a media query (Class 5) |
| **Screenshot gallery** | One big picture of a project, and thumbnails that swap it | Class 7, Assignment 15 |

The capstone brief in the assignments folder says how to build each one.

Some popular ideas need things this course never taught, so treat them as *(stretch)* goals for after the page is finished: a "back to top" button that appears as you scroll, a pop-up image viewer that covers the page, a typing animation in the hero, and a theme that's still dark after a reload.

---

## 11. Show and Tell: Reviewing Your Work

Finished work is meant to be shown. If you're in a class, you'll present for about ten minutes. If you're learning alone, do the same thing for a friend — or out loud, to yourself. It still works.

### How to present
1. **Show the page** (2 minutes). Open it at phone width, then widen it. Switch the theme. Use your third interaction. Send the form.
2. **Show one piece of code you're proud of** (3 minutes). Explain it line by line: what it does, and why you wrote it that way.
3. **Show one bug** (2 minutes). What you saw, what you tried, and what the cause turned out to be.
4. **Take questions and feedback** (3 minutes).

### How to review someone else's work
Score each row from 0 to 2: **0** is missing, **1** is partly there, **2** is solid.

| Area | What to check |
|---|---|
| Semantics | The landmarks are used correctly, the headings are in order, and every form label is linked to its field |
| CSS structure | One external stylesheet, a consistent type and spacing scale, and the `box-sizing` reset |
| Layout | Flexbox and Grid are both used, each where it fits |
| Responsive | It works from 320px to 1440px, with no overflow; the nav and the cards both adapt |
| JavaScript | The theme toggle works, the form is handled without a reload, the third interaction works, and the Console is clean |
| Content | It's clear who this is and what they can do; real words; every image has an `alt` |
| Code quality | Readable, indented, nothing left over, typed by hand — and the author can explain it |

**14** is ready to share. **10 to 13** needs one more polish pass. **Below 10**: find the weakest row, and go back to that class's assignments.

When you give feedback, give **two things that work well and one thing to change**, and be specific. "The cards line up nicely at every width" helps. "Looks good" doesn't.

Then score your **own** page with the same table, honestly, before anyone else does.

---

## 12. The Whole Course on One Page

Look at what's in the file you just built:

| Class | The idea | Where it is in your portfolio |
|---|---|---|
| 1 | HTML basics | Every heading, paragraph, link, image, and list |
| 2 | Semantic structure and forms | `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`; the contact form and its validation |
| 3 | CSS and the box model | Every colour, font, margin, padding, and border; the centred column |
| 4 | Flexbox | The header, the skills, the filter buttons, the inside of each card |
| 5 | Grid and responsive design | The project cards, the About section, `clamp()`, the media query |
| 6 | JavaScript basics | `showProjects`: a function, a loop, an `if`, a counter, a template literal |
| 7 | The DOM and events | The theme toggle, the form, the filter: find, listen, change |
| 8 | Putting it together | The nav links — and the fact that it all works at once |

Nothing on that page came from a template, a library, or a framework. You can open any of the three files, point at any line, and say what it does. That is what "I built this" means.

---

## 13. Troubleshooting

| Problem | Likely cause |
|---|---|
| A nav link does nothing | The `href` and the `id` don't match exactly: a typo, a capital letter, or a `#` typed into the `id`. |
| A nav link shows "Cannot GET" or a "not found" page | The `#` is missing from the `href`, so the browser went looking for another page. |
| Nothing interactive works at all | Look at the Console. One red error near the top of `app.js` stops everything below it. Fix the first error first. |
| The form reloads the page again | Either `event.preventDefault()` is missing, or an error earlier in the file stopped the script before it reached the form's listener. |
| The count changes, but the cards don't disappear | `.hidden` isn't the last rule in the stylesheet, so `.project { display: flex; }` is beating it. |
| A filter shows no cards | The button's text and the tags' text don't match exactly. `Javascript` is not `JavaScript`. |
| The wrong cards are hidden | A card is missing its `.tag`, or has two, so the lists no longer line up by index. |
| One part of the page stays white in dark mode | That part has its own `background-color`, and no `.dark …` rule. Or the selector is backwards: `.dark .project` is right; `.project .dark` is not. |
| The chosen filter looks the same as the others in dark mode | `.dark .active` is missing, or it's above `.dark .filter`. |
| The hero button's text changes colour in dark mode | `.dark a` is beating `.button`. Add `.dark .button`. |
| The page scrolls sideways on a small phone | Test at 320px, not only 375px. Usually a `minmax()` minimum, a fixed `width` in `px`, or an image without the reset. |
| The header is a mess between 600px and 800px | Your links and name need more room than Ada's. Move the breakpoint: change `700px` to a width where everything fits. |
| A project link opens "not found" | The path is wrong, or the project isn't inside `portfolio/projects/`. A link can only reach files that exist at that path. |
| The cards are different heights, or the links don't line up | `display: flex; flex-direction: column;` is missing from `.project`, or `margin-top: auto` is missing from the link. |
| Everything resets when I reload, including the theme | That's normal. JavaScript changes the DOM, not your file, and nothing is saved between visits. |

---

## 14. Self-Check: Can You Answer These?

These cover the whole course. Try without scrolling back.

1. What is the job of each of the three languages: HTML, CSS, and JavaScript?
2. Why choose `<nav>`, `<main>`, and `<section>` over a page full of `<div>`s?
3. Name the four parts of the box model, from the inside out. What does `box-sizing: border-box` change?
4. Two rules set the same property on the same element. What decides which one wins?
5. When do you reach for Flexbox, and when for Grid? Give one example of each from your portfolio.
6. What does "mobile-first" mean? Which kind of media query does it use?
7. Explain `repeat(auto-fill, minmax(260px, 1fr))` in plain English. Why does the portfolio use `auto-fill` and not `auto-fit`?
8. `let` or `const` — how do you decide? And what's the difference between `=` and `===`?
9. What are the three steps of almost every interactive feature? Name them for your theme toggle.
10. How does `<a href="#contact">` know where to go? Give two reasons it might do nothing.

---

## 15. Homework

1. **Finish your own portfolio** (the course deliverable). Work through Section 10, then go back through Section 9. It's done when:
   - [ ] Every requirement in Section 2 is ticked
   - [ ] The words, the projects, and the colours are yours
   - [ ] It has a theme toggle, a thank-you form, and a third interaction of your choice
   - [ ] It works from 320px to 1440px, in both themes, with a clean Console
   - [ ] You can explain any line in any of the three files

2. **Score it** with the table in Section 11. Fix the weakest row, and score it again.

3. **Write a short reflection**, in a text file, in your own words:
   - Which class was hardest, and how did you get past it?
   - Describe one bug that took you more than 20 minutes. What was the actual cause?
   - Where did you use Flexbox, where did you use Grid, and why?
   - What would you add or change with another week?
   - What do you want to learn next?

4. *(Optional)* **Put it online**, so that it has an address you can send to people. This uses a service that isn't part of the course; the assignments folder has a walk-through.

For the full capstone brief, five other kinds of site to build, stretch goals, and a debugging exercise on a broken portfolio, see the **Class 8** section of [`assignments.md`](assignments.md).

---

## What's Next

That's the crash course. You can build a responsive, interactive page from an empty folder, and you know why each line is there.

Everything from here is built on what you now know. The fuller PalmTechnIQ path goes on in three steps:

- **CSS frameworks** — ready-made sets of classes, so you write less CSS for common patterns. They only make sense once you understand the box model, Flexbox, and Grid. You do.
- **A deeper dive into JavaScript** — the things this course left out on purpose: more ways to work with arrays, saving data in the browser, timers, and fetching data from a server.
- **Frontend frameworks** — tools for building large applications out of small pieces. They take care of "find, listen, change" for you, which is why you needed to do it by hand first.

Before any of that, keep building. Rebuild something from an earlier class without looking. Make a page for a friend. Show someone your portfolio.

You built this.
