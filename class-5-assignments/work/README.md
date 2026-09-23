# Your Class 5 work goes here

One folder per assignment, usually with both `index.html` and `style.css`:

```
work/
  01-first-grid/                        index.html  style.css
  08-responsive-photo-gallery/          index.html  style.css
  09-page-layout-with-grid-areas/       index.html  style.css
  13-responsive-about-me-and-contact/
    about-me/                           index.html  style.css
    contact/                            index.html  style.css
  ...
```

Every `index.html` from this class on has the viewport tag in its `<head>`:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

Open `index.html` with the **Live Server** extension, and keep two dev-tools features open:

- **The device toolbar** (`Ctrl+Shift+M`, Mac `Cmd+Shift+M`) — choose **Responsive** and type a
  width, or pick a phone from the list. Check 375px, 768px, and 1280px every time.
- **The grid overlay** — in the Elements panel, click the small `grid` badge next to any grid
  container. The **Layout** tab has a setting to show line numbers. Use it whenever a span lands
  somewhere unexpected.

**Assignment 13** makes two earlier pages responsive. Copy them in first:
- `class-3-assignments/work/07-style-about-me/` → `work/13-responsive-about-me-and-contact/about-me/`
- `class-4-assignments/work/13-contact-form-two-columns/` → `work/13-responsive-about-me-and-contact/contact/`

**Assignment 18** converts two earlier layouts. Copy them in first:
- `class-4-assignments/work/11-pricing-table/` → `work/18-flexbox-to-grid-and-back/pricing-grid/`
- `work/08-responsive-photo-gallery/` → `work/18-flexbox-to-grid-and-back/gallery-flex/`

**Assignments 07 and 14** start from a page you've already built. Copy it into the new folder
first so the original stays safe.
