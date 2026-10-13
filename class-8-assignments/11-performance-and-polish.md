# Assignment 11 — Performance & Polish

**Type:** Stretch · **Difficulty:** ⭐⭐ · **Time:** ~1 hr
**Prereqs:** a finished portfolio ([Assignment 01](01-personal-portfolio.md))
**Build in:** `work/01-personal-portfolio/` — make a save point first

---

## Goal

Give your portfolio the finishing touches that separate "it works" from "it's done": pictures that load quickly, a stylesheet with nothing left over, and the small details in the `<head>` that show up on a browser tab and in a search result.

## What you'll practice

- Finding out how heavy a page really is
- Resizing images to the size they're shown at
- Clearing out code that nothing uses
- The `<title>`, a description, and a favicon

## Instructions

1. **Measure first.** Open dev tools, go to the **Network** panel, and reload the page. The bar at the bottom shows how many files were fetched and how much was transferred. Sort the list by size. Write down the total, and the three biggest files.
2. **Shrink the images.** The biggest files will be pictures. A screenshot shown 400 pixels wide doesn't need to be 2,500 pixels wide.
   - Resize each picture to about **twice** the width it's displayed at: a card image shown at 400px should be about 800px wide.
   - Save photos as `.jpg` and screenshots as `.png`, and export them from your image editor at a medium quality setting.
   - Aim for under about 200 KB for each picture.
3. **Remove unused CSS.** Go through `style.css` one selector at a time. For each class or `id`, search your HTML for it. If nothing uses it, delete the rule. Do the same for rules that appear twice.
4. **Remove leftovers from the JavaScript**: every `console.log` you added while debugging, and any function that nothing calls. Keeping `console.log("app.js loaded");` is fine.
5. **Finish the `<head>`:**
   - a `<title>` that says who you are and what you do — it's the text on the browser tab
   - a description, which search engines may show under your title:
     `<meta name="description" content="One or two sentences about you and this site.">`
   - a **favicon**, the tiny picture on the browser tab. Make a small square image, save it in `images/`, and add:
     `<link rel="icon" href="images/favicon.png">`
6. **Measure again.** Reload with the Network panel open, and compare.
7. **Read the code once more**, top to bottom, in all three files. Fix the indentation, and delete any comment that's no longer true.

## Requirements

- [ ] No picture is much wider than twice its displayed width
- [ ] The page's total size is smaller than when you started, and you've written down both numbers
- [ ] Every rule in `style.css` is used by something in the HTML
- [ ] No leftover debugging lines in `app.js`
- [ ] A meaningful `<title>`, a `<meta name="description">`, and a favicon
- [ ] The page looks and works exactly as before, at every width and in both themes

## Acceptance criteria

- The browser tab shows your favicon and your title.
- In the Network panel, no single image is the size of a small video.
- Delete a rule you believed was unused, and nothing on the page changes. (If something does, put it back.)
- The pictures still look sharp on your phone.

## Hints

<details><summary>Show hint</summary>

- **Don't have an image editor?** The photo app that came with your computer can resize and export pictures. So can any free image editor.
- **Why twice the displayed width?** Phone screens, and many laptop screens, pack two or more real pixels into each CSS pixel. A picture exactly as wide as its box looks slightly soft on them.
- **The favicon doesn't show.** Browsers hold on to favicons stubbornly. Check the path, then do a hard reload: `Ctrl + Shift + R` on Windows, `Cmd + Shift + R` on a Mac.
- **Not sure whether a CSS rule is used?** Remember the classes that JavaScript adds — `dark`, `hidden`, `active`. They don't appear in your HTML as typed, but they're very much in use.
</details>

## Stretch (optional)

Decoration, for when everything else is finished. None of it was taught in this course, so look each one up, add it last, and keep it subtle:

- *(stretch — beyond this course)* Rounded corners and soft shadows on the cards: `border-radius` and `box-shadow`.
- *(stretch — beyond this course)* Buttons and links that react when the mouse is over them: the `:hover` selector.
- *(stretch — beyond this course)* A theme change that fades instead of snapping: `transition`.
- *(stretch — beyond this course)* Pictures further down the page that load only when they're needed: the `loading="lazy"` attribute on `<img>`.
