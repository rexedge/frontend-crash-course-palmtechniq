# Your Class 3 work goes here

One folder per assignment. Most need **two** files — `index.html` and `style.css`:

```
work/
  01-wire-up-a-stylesheet/    index.html  style.css
  02-selector-targeting/      index.html  style.css
  07-style-about-me/          index.html  style.css
  08-style-contact-form/      index.html  style.css
  12-re-theme-dont-re-structure/  index.html  style.css  theme-dark.css
  ...
```

Link the stylesheet in the HTML `<head>`:

```html
<link rel="stylesheet" href="style.css">
```

Open `index.html` with the **Live Server** extension. Keep the browser dev tools open
(right-click → Inspect) — the **Elements** panel shows the box model diagram, and the
**Styles** panel shows every rule hitting the selected element with the losing ones struck through.

**Assignments 07 and 08** style the pages you built in Class 2. Copy them in first:
- `class-2-assignments/work/07-semantic-about-me/index.html` → `work/07-style-about-me/index.html`
- `class-2-assignments/work/11-contact-form/index.html` → `work/08-style-contact-form/index.html`

You only add a `style.css` — **do not change the HTML** (except adding the `<link>` line).
