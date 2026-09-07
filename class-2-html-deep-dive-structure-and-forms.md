# Class 2: HTML Deep Dive — Structure & Forms
### A self-guided read-through — read each section, then do the practice before moving on. Keep your Class 1 "About Me" page nearby; you'll rebuild it at the end.

---

## 1. Recap: Where We Are

In Class 1 you learned that **HTML is the skeleton** of a web page. You used tags like `<h1>`, `<p>`, `<a>`, `<img>`, `<ul>`, and `<ol>` to put *content* on the page.

Everything you built still looks plain — no colours, no layout. **That is still expected.** Styling is Class 3.

This class is about writing HTML that is **well organised** and **meaningful**, and about the single most interactive part of plain HTML: **forms**.

Two big ideas today:

1. **Semantic HTML** — using tags that describe *what a piece of content is*, not just *that it exists*.
2. **Forms** — how a web page collects information from a person (names, emails, messages, choices).

---

## 2. A Small Upgrade to the Skeleton

From now on, start your pages like this:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Page</title>
</head>
<body>

</body>
</html>
```

Two new lines, both live in `<head>`:

- `<html lang="en">` — tells browsers and screen readers the page is written in English. Helps accessibility and search engines.
- `<meta charset="UTF-8">` — tells the browser how to read your text so characters like `é`, `₦`, and `—` display correctly. `<meta>` is a self-closing tag that gives the browser information; it never shows anything on the page.

You don't need to fully understand these yet. Just type them at the top of every page.

---

## 3. The Problem Semantic HTML Solves

You *could* build an entire website using only two tags: `<div>` (a generic block) and `<span>` (a generic inline piece). Many old websites did exactly that. The result is called **"div soup"**:

```html
<div>
    <div>My Site</div>
    <div>
        <div><a href="#">Home</a></div>
        <div><a href="#">About</a></div>
    </div>
</div>
<div>
    <div>Welcome to my site</div>
    <div>Here is some text.</div>
</div>
<div>Copyright 2025</div>
```

A browser can display this fine. But **nothing in it has meaning**. It's just nested boxes. This causes real problems:

| Who / what | Why div soup hurts them |
|---|---|
| **Screen reader users** | Assistive software can't announce "this is the main navigation" or "jump to the main content" if nothing is labelled as navigation or main content. |
| **Search engines (SEO)** | Google reads your HTML to understand your page. Meaningful tags help it identify the important content. |
| **You, in six months** | `<header>` tells you instantly what a block is. `<div>` tells you nothing — you have to read all the content to figure it out. |
| **Browser features** | "Reader mode", keyboard shortcuts, and browser extensions rely on semantic tags to work. |

**Semantic HTML** means choosing the tag that matches the *meaning* of the content.

---

## 4. The Semantic Layout Tags

Here are the tags that describe the major regions of a page. Picture a typical website:

```
┌───────────────────────────────────────────┐
│  <header>   — site name / logo            │
│    <nav>    — the main menu               │
├───────────────────────────────────────────┤
│  <main>     — the unique content of THIS  │
│              page                         │
│                                           │
│    <section> — a themed group of content  │
│    <article> — a self-contained piece     │
│    <aside>   — side notes, related links  │
│                                           │
├───────────────────────────────────────────┤
│  <footer>   — copyright, contact, links   │
└───────────────────────────────────────────┘
```

### `<header>`
The introductory area at the top. Usually holds the site name/logo and the main navigation. (A `<header>` can also appear *inside* an `<article>` to hold that article's title and date — but keep it simple for now: one header at the top.)

### `<nav>`
A block of **major navigation links** — the main menu. You do *not* wrap every group of links in `<nav>`; it's for primary navigation.

### `<main>`
The main content of the page — the part that is unique to *this* page and not repeated across the site. **Only one `<main>` per page.** The header, nav, and footer live *outside* it.

### `<section>`
A thematic grouping of content, almost always with its own heading. Think "a chapter" or "a labelled part of the page": an "About" area, a "Skills" area, a "Contact" area.

### `<article>`
A piece of content that would make sense **on its own**, even if you pulled it out of the page: a blog post, a news story, a comment, a product card. If you could imagine it being shared or syndicated by itself, it's an `<article>`.

> **Section vs article — the quick test:**
> Could this stand completely on its own (like a single blog post)? → `<article>`
> Is it a labelled part of a bigger whole? → `<section>`
> Still unsure? Pick one and move on. It's rarely a disaster.

### `<aside>`
Content that is related but not essential: a sidebar, a "related posts" list, a pull quote, an author bio next to an article.

### `<footer>`
The closing area at the bottom: copyright, contact info, secondary links, social links.

### `<div>` and `<span>` — the fallbacks
When **no semantic tag fits** and you just need a plain container (usually to style a group of things later), use:
- `<div>` — a generic **block** (starts on a new line)
- `<span>` — a generic **inline** piece (sits within a line of text)

These have no meaning. That's the point — use them only when meaning isn't available.

### Practice Now
Create `structure-practice/index.html`. Build a page skeleton with **only** these tags (no real content needed yet — one line of placeholder text in each is fine):

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Structure Practice</title>
</head>
<body>

    <header>
        <h1>Site Name</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <article>
            <h2>First Article</h2>
            <p>This could stand on its own.</p>
        </article>

        <section>
            <h2>A Themed Section</h2>
            <p>This is a labelled part of the page.</p>
        </section>

        <aside>
            <h2>Related</h2>
            <p>A side note.</p>
        </aside>
    </main>

    <footer>
        <p>Made by me, 2025.</p>
    </footer>

</body>
</html>
```

Open it with Live Server. It will look like a plain vertical stack of text — **that's correct**. The value is in the structure, which you can see in the browser's "Elements" dev tools panel (right-click → Inspect).

✅ **Checkpoint:** If your page has exactly one `<main>`, and your `<header>`/`<nav>`/`<footer>` are *outside* it, you've got the shape right.

---

## 5. Semantic HTML Is Still Just HTML

Important: these new tags behave **exactly like `<div>`** visually. They don't add colour, spacing, or layout. They only add *meaning*. Everything you learned in Class 1 still applies — headings, paragraphs, lists, links, and images all go *inside* these regions as normal.

```html
<main>
    <section>
        <h2>About Me</h2>
        <p>I'm learning web development.</p>
        <ul>
            <li>I like puzzles</li>
            <li>I'm from Lagos</li>
        </ul>
    </section>
</main>
```

---

## 6. Tables — For Data, Not Layout

A **table** displays information that genuinely belongs in a grid of rows and columns: a schedule, a price list, a comparison, a set of results.

> **The one rule:** use tables for **tabular data only**. Never use a table to position things on a page. (People did this in the 1990s. It was a mistake. Layout is Classes 4 and 5.)

### The table tags

| Tag | Meaning |
|---|---|
| `<table>` | Wraps the whole table |
| `<caption>` | The table's title (goes first, inside `<table>`) |
| `<thead>` | Groups the header row(s) |
| `<tbody>` | Groups the body rows |
| `<tr>` | Table row |
| `<th>` | A **header** cell (bold + centered by default) |
| `<td>` | A **data** cell |

The `scope` attribute on `<th>` tells screen readers whether a header labels a **column** (`scope="col"`) or a **row** (`scope="row"`).

### Example

```html
<table>
    <caption>Weekly Class Schedule</caption>
    <thead>
        <tr>
            <th scope="col">Day</th>
            <th scope="col">Topic</th>
            <th scope="col">Room</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">Monday</th>
            <td>HTML Basics</td>
            <td>A1</td>
        </tr>
        <tr>
            <th scope="row">Wednesday</th>
            <td>Forms &amp; Tables</td>
            <td>A2</td>
        </tr>
        <tr>
            <th scope="row">Friday</th>
            <td>CSS Basics</td>
            <td>B3</td>
        </tr>
    </tbody>
</table>
```

(`&amp;` is how you write a literal `&` in HTML. It's called an "entity". You'll meet a few of these.)

### Practice Now
In a new file `table-practice/index.html`, build a table of **your** real weekday routine: columns `Time`, `Activity`, `Location`; at least 4 rows. Use `<caption>`, `<thead>`, `<tbody>`, and `scope` correctly.

✅ **Checkpoint:** Your header cells use `<th>` (not `<td>`), and they're wrapped in `<thead>`.

---

## 7. Forms — How a Page Collects Information

A **form** is any part of a page where a person types or chooses something and submits it: a login box, a search bar, a checkout page, a contact form.

Everything goes inside a `<form>` element:

```html
<form>
    <!-- inputs, labels, buttons go here -->
</form>
```

A real form has an `action` (the web address that receives the data) and a `method`. **We are not sending data anywhere in this course**, so you can leave `action` off. When you submit, the page will just reload and clear — that's normal for now. In Class 7 you'll use JavaScript to handle submissions properly.

---

## 8. Inputs and Labels — Always Together

The main control is `<input>`. It's **self-closing** (no closing tag). Its `type` attribute decides what kind of field it is.

**Every input needs a `<label>`.** A label is the visible text that tells the user what the field is for. You connect them like this:

```html
<label for="email">Email address</label>
<input type="email" id="email" name="email">
```

The `for` on the label must **exactly match** the `id` on the input. When they're linked:

- Clicking the label text focuses the input (a bigger, easier click target).
- Screen readers announce "Email address, edit text" instead of just "edit text".

The `name` attribute is the key used when the form's data is sent. Real forms need it; get in the habit of adding it.

### Common input types

| `type=` | Use it for | Nice extras |
|---|---|---|
| `text` | Names, short free text | — |
| `email` | Email addresses | Browser checks for an `@` |
| `password` | Passwords | Characters are hidden |
| `number` | Quantities, ages | Up/down arrows; `min`/`max` |
| `tel` | Phone numbers | Mobile keypads show digits |
| `url` | Web addresses | Browser checks the format |
| `date` | Calendar dates | Shows a date picker |
| `checkbox` | A single yes/no, or a "pick many" group | — |
| `radio` | "Pick exactly one" from a group | — |
| `submit` | The button that sends the form | — |

### Checkboxes and radio buttons

A **checkbox** is an independent on/off switch:

```html
<input type="checkbox" id="newsletter" name="newsletter">
<label for="newsletter">Send me the newsletter</label>
```

**Radio buttons** are a group where only **one** can be chosen. They become one group by sharing the **same `name`**. The `value` says which one was picked:

```html
<fieldset>
    <legend>Preferred contact method</legend>

    <input type="radio" id="by-email" name="contact-method" value="email">
    <label for="by-email">Email</label>

    <input type="radio" id="by-phone" name="contact-method" value="phone">
    <label for="by-phone">Phone</label>
</fieldset>
```

If you give radio buttons **different** `name` values by mistake, the browser treats them as unrelated and lets the user select all of them. This is the #1 radio button bug.

`<fieldset>` draws a box around a group of related controls, and `<legend>` is that group's caption. Use them for radio/checkbox groups.

---

## 9. The Other Form Controls

### `<textarea>` — multi-line text
For long text like a message or a bio. Unlike `<input>`, it has a **closing tag**, and any starting text goes **between the tags**, not in a `value` attribute:

```html
<label for="message">Your message</label>
<textarea id="message" name="message" rows="6"></textarea>
```

`rows` sets how many lines tall it starts.

### `<select>` — a dropdown
```html
<label for="country">Country</label>
<select id="country" name="country">
    <option value="" disabled selected>Choose one</option>
    <option value="ng">Nigeria</option>
    <option value="gh">Ghana</option>
    <option value="ke">Kenya</option>
</select>
```

The first `<option>` here is a placeholder: `disabled` (can't be chosen) and `selected` (shown first). Each real option's `value` is what gets sent.

### `<button>` — the action
```html
<button type="submit">Send</button>
```

- `type="submit"` — sends the form (this is the default for a `<button>` inside a `<form>`).
- `type="button"` — does **nothing** on its own; it waits for JavaScript (Class 7).
- `type="reset"` — clears the form back to its starting state.

If a "button" isn't submitting your form, check its `type`.

---

## 10. Basic Validation Attributes

The browser can check a field **before** the form submits, and show a built-in error message. You turn this on with attributes — no JavaScript needed.

| Attribute | Works on | What it checks |
|---|---|---|
| `required` | almost all | The field can't be empty |
| `minlength` / `maxlength` | text, `textarea` | Minimum / maximum number of characters |
| `min` / `max` | `number`, `date`, `range` | Smallest / largest allowed value |
| `pattern` | text-like inputs | The value must match a rule (a "regular expression") |
| `placeholder` | text-like inputs | Shows faint hint text — **not** validation, and **not** a label |

`required` is a **boolean attribute**: it's either present or not. Writing `required="false"` still means *required* — to make a field optional, remove the attribute entirely.

Type itself is a check too: `type="email"` rejects `hello`, `type="url"` rejects `not a link`, `type="number"` rejects letters.

### Examples

```html
<!-- must be filled, 3 to 15 characters -->
<input type="text" id="username" name="username" required minlength="3" maxlength="15">

<!-- a number from 1 to 8 -->
<input type="number" id="guests" name="guests" min="1" max="8">

<!-- exactly 11 digits, with a hint showing the format -->
<input type="tel" id="phone" name="phone" pattern="[0-9]{11}" placeholder="08012345678">
```

`pattern="[0-9]{11}"` means "eleven characters, each one a digit 0–9". You don't need to master patterns now — just know the attribute exists.

> **Placeholder is not a label.** Placeholder text disappears as soon as the user types, and screen readers may skip it. Always keep a real `<label>`; use `placeholder` only for an *extra* format hint.

### Practice Now
Build one field of each kind in a scratch file and **try to break each rule**: submit empty `required` fields, type letters into a `number`, type a too-short value into a `minlength` field. Read every error bubble the browser shows you.

---

## 11. Guided Practice: Build a Contact Form Page

This is the main build for Class 2. Create `contact-form/index.html`.

Combine **both** of today's topics: a **semantic page structure** with a **form** inside it.

### Requirements checklist

**Structure**
- [ ] The upgraded skeleton (`lang`, `<meta charset>`, `<title>`)
- [ ] A `<header>` with a site name (`<h1>`) and a `<nav>` containing a `<ul>` of 3 links
- [ ] One `<main>`
- [ ] Inside `<main>`: a `<section>` with an `<h2>` like "Get in touch" and a short `<p>` of intro text
- [ ] Inside `<main>`: the `<form>`
- [ ] A `<footer>` with a `<p>` and one link — placed **outside** `<main>`

**The form** (no `action` needed)
- [ ] **Full name** — `type="text"`, `required`
- [ ] **Email** — `type="email"`, `required`
- [ ] **Subject** — `type="text"` (optional field)
- [ ] **Message** — `<textarea>`, `required`, `minlength="10"`
- [ ] **How did you hear about us?** — a `<select>` with a disabled placeholder option and 3 real options
- [ ] **Preferred contact method** — a `<fieldset>` + `<legend>` with 2–3 radio buttons sharing one `name`
- [ ] **Consent** — a `type="checkbox"` that is `required`, with its label
- [ ] A **submit** `<button>`
- [ ] **Every** input, textarea, and select has a `<label>` whose `for` matches the control's `id`

### A partial example (write your own content; fill in the rest)

```html
<main>
    <section>
        <h2>Get in touch</h2>
        <p>Have a question? Fill in the form and we'll reply by email.</p>
    </section>

    <form>
        <p>
            <label for="name">Full name</label>
            <input type="text" id="name" name="name" required>
        </p>

        <p>
            <label for="email">Email address</label>
            <input type="email" id="email" name="email" required>
        </p>

        <p>
            <label for="message">Message</label>
            <textarea id="message" name="message" rows="6" required minlength="10"></textarea>
        </p>

        <fieldset>
            <legend>Preferred contact method</legend>
            <input type="radio" id="reply-email" name="reply-method" value="email">
            <label for="reply-email">Email</label>
            <input type="radio" id="reply-phone" name="reply-method" value="phone">
            <label for="reply-phone">Phone</label>
        </fieldset>

        <p>
            <input type="checkbox" id="consent" name="consent" required>
            <label for="consent">I agree to be contacted about my message.</label>
        </p>

        <p>
            <button type="submit">Send message</button>
        </p>
    </form>
</main>
```

(The `<p>` tags around each field are just there to force each one onto its own line while we have no CSS. That's a fine, old-fashioned trick for now.)

Test it: click each **label** and confirm the matching field gets focus. Submit with empty required fields and read the errors. Try selecting both radio buttons — you shouldn't be able to.

✅ **Checkpoint:** Every field is reachable by clicking its label text, and the form refuses to submit while a `required` field is empty.

---

## 12. Troubleshooting

| Problem | Likely cause |
|---|---|
| Clicking a label doesn't focus its field | `for` on the label doesn't exactly match the `id` on the input (typo, capitalisation, or missing). |
| All radio buttons can be selected at once | The radios have different `name` values. Give every radio in the group the **same** `name`. |
| The form reloads and clears when I submit | That's the default behaviour with no JavaScript. Expected until Class 7. |
| `required` seems ignored | Check spelling; remove any `="false"`; make sure the field is actually inside the `<form>`. |
| My `<select>` shows a real option first instead of "Choose one" | Add a first `<option value="" disabled selected>Choose one</option>`. |
| Text I put in `value=""` on a `<textarea>` doesn't show | `<textarea>` has no `value` attribute — put starting text *between* `<textarea>` and `</textarea>`. |
| The button doesn't submit | It needs `type="submit"` (or no `type`) and must be **inside** the `<form>`. |
| Page still looks completely unstyled | Correct. Styling is Class 3. Structure and meaning come first. |
| "Elements" panel shows tags nested wrong | An earlier tag wasn't closed. Read your code top to bottom; each opening tag needs a matching close, in reverse order. |

---

## 13. Self-Check: Can You Answer These?

Try without scrolling back.

1. Name five semantic layout elements and say what content belongs in each.
2. What's the quick test for choosing `<section>` vs `<article>`?
3. How many `<main>` elements should a page have, and what goes *outside* it?
4. What two things does linking a `<label>` to an `<input>` (via `for`/`id`) do for the user?
5. When is a `<table>` the right tool? Give one wrong use of tables.
6. Why must all radio buttons in one group share the same `name`?
7. Where does a `<textarea>`'s starting text go — in an attribute or between the tags?
8. Name three validation attributes and what each one checks. Why is `placeholder` not one of them?

---

## 14. Homework

1. **Rebuild your Class 1 "About Me" page using semantic tags.**
   Save it as a **new** file (e.g. `about-me-semantic/index.html`) so you can compare it to the original.
   - Wrap the top in `<header>` (your name in `<h1>`, plus a small `<nav>`).
   - Put the biography, "Things I Like", and "Goals" each in their own `<section>` with an `<h2>`.
   - Add a `<footer>` with a line about yourself and a link.
   - The **content stays the same** — only the structure becomes meaningful.

2. **Finish the contact form page** from Section 11 if you didn't complete it in the read-through.

3. *(Optional)* Keep the routine **table** from Section 6.

For a lot more practice on this class — warm-up drills, extra builds, and debugging exercises with answers — see the **Class 2** section of [`assignments.md`](assignments.md).

---

## What's Next

Class 3 is **CSS Basics** — finally, colour, spacing, and typography. Your pages will start to *look* like something. The single most important concept there is the **box model**, so come in with your semantic About Me page and your contact form ready to style.
