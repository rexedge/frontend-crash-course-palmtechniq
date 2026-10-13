# Your Class 6 work goes here

One folder per assignment, each with an `index.html` and an `app.js`:

```
work/
  01-declare-and-log/        index.html  app.js
  11-the-classic-ten/        index.html  app.js
  19-five-logic-functions/   index.html  app.js
  22-trace-the-code/         answers.md  index.html  app.js
  ...
```

There's no `style.css` this class. The page stays almost empty — all your output goes to the
Console.

## The starter page

Every `index.html` this class is the same few lines. Type it out each time (it's good practice),
and change the `<title>` and `<h1>` to match the assignment:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>01 — Declare and log</title>
</head>
<body>
    <h1>01 — Declare and log</h1>
    <p>Nothing to see on the page. Open the Console.</p>

    <script src="app.js"></script>
</body>
</html>
```

The `<script>` tag goes at the **end of `<body>`**, and it needs its closing `</script>`.

## Working in the Console

Open `index.html` with the **Live Server** extension, then open the Console: `F12` and click
**Console**, or go straight there with `Ctrl+Shift+J` (Mac `Cmd+Option+J`).

- **Every save re-runs the whole file.** Live Server reloads the page, and `app.js` runs again
  from the top.
- **Each line of output shows where it came from** — `app.js:12` on the right. Click it to jump
  to that line.
- **Red means stop and read.** The message tells you the kind of error, the detail, and the file
  and line. Fix the first red message first.
- **Nothing in the Console at all?** Check that the file name in `src="app.js"` matches the real
  file exactly, and that you actually **called** your functions and logged the results.
- **The tab has frozen?** That's an infinite loop. Close the tab, fix the loop in VS Code, and
  open the page with Live Server again.

## Notes on particular assignments

**Assignment 19** (the homework) starts from an empty folder. Don't copy from Assignments 11 or
15 — rewriting from scratch is the whole point.

**Assignments 22 and 24** are answered in a text file first (`answers.md`). For 22, write your
predictions down *before* you run anything.

**Assignment 23** has eight broken snippets. Give each one its own file — `a.js`, `b.js`, … —
and point the `<script src>` at the one you're working on.

**Keep Assignments 11 and 21.** Class 7 connects `celsiusToFahrenheit` (from 11) and your cart
functions (from 21) to real pages.
