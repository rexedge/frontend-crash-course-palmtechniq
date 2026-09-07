# Class 1: Welcome to the Web + HTML Basics
### A self-guided read-through — read each section, then do the practice before moving on.

---

## 1. What Actually Happens When You Visit a Website?

When you type a website address (like `google.com`) into your browser and hit enter, here's what happens in simple terms:

1. Your browser asks a server somewhere in the world: "Send me this website."
2. The server sends back files — mainly **HTML**, **CSS**, and **JavaScript**.
3. Your browser reads those files and turns them into the page you see.

Think of building a website like building a house:

| Layer | House Analogy | What It Does |
|---|---|---|
| **HTML** | The frame/skeleton (walls, rooms, doors) | Structure and content |
| **CSS** | The paint, furniture, decoration | Styling and layout |
| **JavaScript** | The electricity and plumbing (things that *do* something) | Behavior and interactivity |

This class is about **HTML** — the skeleton. No paint, no electricity yet. Just structure. That's normal — your pages will look plain today, and that's expected.

---

## 2. Setting Up Your Tools

You need two things:

1. **VS Code** — the program (code editor) you'll write your code in.
2. **Live Server extension** — lets you see your page update in the browser instantly as you save.

### Steps:
1. Open VS Code.
2. Click the **Extensions** icon on the left sidebar (looks like 4 squares).
3. Search for **"Live Server"** by Ritwick Dey.
4. Click **Install**.
5. Create a new folder on your computer called `my-first-website`.
6. Open that folder in VS Code (`File → Open Folder`).
7. Inside that folder, create a new file called `index.html`.

> **Why `index.html`?** Browsers automatically look for a file named `index.html` as the "homepage" of a folder. It's a naming convention, not a rule you're forced into, but always use it for your main page.

---

## 3. The HTML Document Skeleton

Every HTML page starts with the same basic structure. Type this into your `index.html` file (typing it yourself, not copy-pasting, helps it stick):

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First Website</title>
</head>
<body>

    <h1>Hello, World!</h1>

</body>
</html>
```

### Let's break down every line:

- `<!DOCTYPE html>` — Tells the browser "this is a modern HTML document." Always the first line, always exactly this.
- `<html>...</html>` — Wraps the *entire* page. Everything else goes inside this.
- `<head>...</head>` — Information *about* the page, not shown on the page itself (like the title in your browser tab, or later, links to CSS files).
- `<title>...</title>` — The text shown in the browser tab.
- `<body>...</body>` — Everything the visitor actually *sees* goes in here. This is where 95% of your work happens.
- `<h1>Hello, World!</h1>` — Your first visible content — a heading.

### Practice Now:
1. Save the file (`Ctrl+S` / `Cmd+S`).
2. Right-click inside the file in VS Code → **"Open with Live Server."**
3. Your browser should open and show "Hello, World!"
4. Change the text inside `<h1>` to your own name. Save. Watch the browser update automatically.

✅ **Checkpoint:** If your browser shows your name, you just wrote and rendered your first HTML page. That's real progress — don't rush past this.

---

## 4. Core HTML Tags You'll Use Constantly

HTML is made of **tags**. Most tags come in pairs: an opening tag `<p>` and a closing tag `</p>`, with content in between. A few tags don't need a closing tag (called "self-closing" or "void" tags) — you'll see examples below.

### Headings
Headings go from most important (`h1`) to least important (`h6`). Use them in order — don't skip from `h1` to `h4`.

```html
<h1>This is the biggest heading</h1>
<h2>This is a bit smaller</h2>
<h3>Smaller still</h3>
```

### Paragraphs
```html
<p>This is a paragraph of text. Use this for any normal body text.</p>
```

### Links
```html
<a href="https://www.google.com">Click here to go to Google</a>
```
- `href` is an **attribute** — extra information given to a tag. `href` tells the link *where* to go.

### Images
```html
<img src="https://via.placeholder.com/150" alt="A placeholder image">
```
- Images are **self-closing** — no `</img>` needed.
- `src` = where the image file is.
- `alt` = a text description, shown if the image fails to load, and read aloud by screen readers. **Never skip `alt`.**

### Lists

Unordered (bullet points):
```html
<ul>
    <li>Milk</li>
    <li>Eggs</li>
    <li>Bread</li>
</ul>
```

Ordered (numbered):
```html
<ol>
    <li>Wake up</li>
    <li>Brush teeth</li>
    <li>Eat breakfast</li>
</ol>
```

---

## 5. Understanding "Nesting"

Tags can go inside other tags — this is called **nesting**. Indentation (spacing) doesn't change how the browser reads it, but it makes your code readable for humans. Always indent nested tags.

```html
<body>
    <h1>My Favorite Foods</h1>
    <p>Here is a list of foods I like:</p>
    <ul>
        <li>Pizza</li>
        <li>Jollof Rice</li>
        <li>Suya</li>
    </ul>
</body>
```

Notice: `<li>` tags are nested inside `<ul>`, and everything is nested inside `<body>`. If you open a tag, always close it before closing the tag it's inside of — closing tags in the wrong order is one of the most common beginner mistakes.

---

## 6. Guided Practice: Build Your "About Me" Page

Now put it together. In your `index.html`, replace everything inside `<body>` with a page about yourself, using **only tags covered above**.

Your page must include:
- [ ] One `<h1>` with your name
- [ ] One `<p>` introducing yourself (2-3 sentences)
- [ ] One `<h2>` heading titled "Things I Like"
- [ ] One `<ul>` with at least 3 `<li>` items
- [ ] One `<h2>` heading titled "A Link"
- [ ] One `<a>` link to any website you like
- [ ] One `<img>` with a valid `src` and a written `alt`

### Example of what the *code* might look like (don't copy this content — write your own):

```html
<body>
    <h1>Ada Lovelace</h1>
    <p>I'm learning to build websites. I like solving puzzles and I'm originally from Lagos.</p>

    <h2>Things I Like</h2>
    <ul>
        <li>Reading</li>
        <li>Coding</li>
        <li>Music</li>
    </ul>

    <h2>A Link</h2>
    <a href="https://www.wikipedia.org">Visit Wikipedia</a>

    <img src="https://via.placeholder.com/200" alt="A placeholder profile picture">
</body>
```

Save often. Check Live Server after every change. If something looks wrong, that's normal — see the troubleshooting section below.

---

## 7. Troubleshooting: When Something Looks Wrong

| Problem | Likely Cause |
|---|---|
| Page is completely blank | Check you saved the file. Check you're editing `index.html`, not a different file. |
| Text isn't showing | Make sure your content is inside `<body>...</body>`, not `<head>`. |
| Image shows a broken icon | Check the `src` link is typed correctly, with no extra spaces. |
| Page looks "messy" or tags seem to not close properly | Check every opening tag `<tag>` has a matching closing tag `</tag>`, and that they close in the reverse order they opened. |
| Live Server won't open | Make sure the extension is installed and you right-clicked the correct file. |

**Rule of thumb:** if something breaks, re-read your code line by line out loud. 90% of beginner bugs are a missing closing tag or a typo.

---

## 8. Self-Check: Can You Answer These?

Try answering without scrolling back up. If you can't, that's a sign to re-read that section.

1. What are the three main languages of the web, and what does each one do?
2. What goes inside `<head>` versus `<body>`?
3. What's the difference between `<ol>` and `<ul>`?
4. Why does every `<img>` need an `alt` attribute?
5. What happens if you close tags in the wrong order?

---

## What's Next
Class 2 builds on this by introducing **semantic HTML** (tags that describe *meaning*, not just structure) and **forms**. Come to Class 2 with your About Me page finished and saved.
