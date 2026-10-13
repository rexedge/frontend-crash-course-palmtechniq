# Your Class 8 work goes here

One folder for the portfolio — and this time it has folders of its own:

```
work/
  01-personal-portfolio/
    index.html
    style.css
    app.js
    images/              your photo, and a screenshot of each project
    projects/            a copy of each finished project
      about-me/          index.html  style.css
      gallery/           index.html  style.css
      to-do-list/        index.html  style.css  app.js
      ...
  12-debug-a-broken-portfolio/
    notes.md
  13-peer-review/
    review.md
  14-wrap-up-reflection/
    reflection.md
```

## Why the projects are copied in

Your portfolio links to your projects. A link can only reach a file that exists at that path, so
copy each finished project **into** `projects/`. Then the whole site lives in one folder: you can
move it, zip it, or put it online in one piece.

Good places to copy from:

| Project | Copy from |
|---|---|
| About Me page | `class-5-assignments/work/13-responsive-about-me-and-contact/about-me/` |
| Contact form | `class-7-assignments/work/10-contact-form-thank-you/` |
| Navbar | `class-4-assignments/work/07-navbar/` |
| Feature cards | `class-4-assignments/work/08-three-card-feature-row/` |
| Blog homepage | `class-4-assignments/work/15-blog-homepage-with-flexbox/` |
| Photo gallery | `class-5-assignments/work/08-responsive-photo-gallery/` |
| Logic functions | `class-6-assignments/work/19-five-logic-functions/` |
| To-do list | `class-7-assignments/work/13-to-do-list/` |
| Temperature converter | `class-7-assignments/work/18-temperature-converter-ui/` |

Use the newest version of each one. After copying, open the copy with Live Server and check that
it still works from its new home.

A link from the portfolio to a project is a relative path, as in Class 1:

```html
<a href="projects/gallery/index.html">View the gallery</a>
```

## The three starting files

**`index.html`** — the skeleton you know, with the stylesheet in the `<head>` and the script at the
end of `<body>`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Your Name — what you do</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!-- header, main, footer -->

    <script src="app.js"></script>
</body>
</html>
```

**`style.css`** — your scales in a comment, then the two resets, and `.hidden` as the last rule:

```css
/*
    Type scale:     …
    Spacing scale:  …
    Colours:        …
*/

*, *::before, *::after {
    box-sizing: border-box;
}

img {
    max-width: 100%;
    height: auto;
    display: block;
}

/* ...your other rules... */

/* Keep this last */
.hidden {
    display: none;
}
```

**`app.js`** — one line to begin with:

```js
console.log("app.js loaded");
```

## Save points

When a milestone works, copy the whole portfolio folder and add the milestone to the copy's name:

```
work/
  01-personal-portfolio/
  01-personal-portfolio-after-m1/
  01-personal-portfolio-after-m2/
  ...
```

If you break something badly, you have a version that worked. Delete the copies when the
portfolio is finished.

## Working with dev tools

Open `index.html` with the **Live Server** extension, and keep these in view:

- **Console** — any red message stops the rest of `app.js`, so fix the first one first.
- **Elements** — watch `class="dark"` appear on `<body>`, and `hidden` appear on the cards.
- **The device toolbar** — test at 320px, 375px, 768px, 1024px, 1280px, and 1440px. Then do it
  again in dark mode.

## Notes on particular assignments

**Assignments 02–06** are whole sites of their own. Give each one you build its own folder, set up
the same way as the portfolio.

**Assignment 08** turns one page into several. Work on a **copy** of your finished portfolio:
`work/08-multi-page/`.

**Assignments 09, 10 and 11** improve the portfolio you already have. Work in
`work/01-personal-portfolio/` itself — after making a save point.

**Assignment 12** has eight broken snippets. You don't need to build them all: reproduce the ones
you can't explain, in a copy of your own portfolio.
