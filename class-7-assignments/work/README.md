# Your Class 7 work goes here

One folder per assignment, with three files — the structure, the look, and the behaviour:

```
work/
  02-change-text-on-click/       index.html  style.css  app.js
  09-light-dark-mode-toggle/     index.html  style.css  app.js
  13-to-do-list/                 index.html  style.css  app.js
  19-interactivity-on-earlier-pages/
    about-me/                    index.html  style.css  app.js
    gallery/                     index.html  style.css  app.js
    blog/                        index.html  style.css  app.js
  ...
```

## The starter page

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>02 — Change text on click</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>02 — Change text on click</h1>

    <!-- your elements go here -->

    <script src="app.js"></script>
</body>
</html>
```

The `<script>` tag goes at the **end of `<body>`**, after every element your code needs to find.

Two things to put in every `style.css` this class:

```css
*, *::before, *::after {
    box-sizing: border-box;
}

/* ...your other rules... */

/* Keep this last */
.hidden {
    display: none;
}
```

And one line worth putting at the top of every `app.js`:

```js
console.log("app.js loaded");
```

If that line shows up a second time when you click something, the page reloaded — and you've
probably forgotten `event.preventDefault()`.

## Working with dev tools

Open `index.html` with the **Live Server** extension, and keep two panels in view:

- **Console** — red messages, and your own `console.log`s. If a click does nothing, put
  `console.log("clicked");` on the first line of the function and try again.
- **Elements** — the live DOM. Watch the `class` attribute flash as your code adds and removes
  classes, and watch new elements appear as you create them.

## Notes on particular assignments

**Assignment 10** adds the "thank you" message to your real contact form. Copy it in first:
- `class-5-assignments/work/13-responsive-about-me-and-contact/contact/` → `work/10-contact-form-thank-you/`

**Assignment 18** uses a function you've already written. Copy `celsiusToFahrenheit` from:
- `class-6-assignments/work/11-the-classic-ten/app.js`

**Assignment 19** (the homework) adds a feature to pages you built earlier. Copy them in first:
- `class-5-assignments/work/13-responsive-about-me-and-contact/about-me/` → `work/19-interactivity-on-earlier-pages/about-me/`
- `class-5-assignments/work/08-responsive-photo-gallery/` → `work/19-interactivity-on-earlier-pages/gallery/`
- `class-4-assignments/work/15-blog-homepage-with-flexbox/` → `work/19-interactivity-on-earlier-pages/blog/`

**Assignment 21** reuses your cart maths. Copy `cartSubtotal` (and the others, if you want tax) from:
- `class-6-assignments/work/21-simple-cart-total/app.js`

**Assignment 24** has eight broken snippets. Give each one its own small folder — `a/`, `b/`, … —
with whatever HTML the snippet needs.

**Assignments 09, 12, 13, 15, 18 and 19 are marked 🧵.** Keep them: the theme toggle, the
accordion, and the gallery are all things you can drop straight into your Class 8 portfolio.
