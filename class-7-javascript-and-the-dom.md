# Class 7: JavaScript & the DOM
### A self-guided read-through — read each section, then do the practice before moving on. Have your responsive contact page and About Me page from Class 5 nearby, and your Class 6 functions.

---

## 1. Recap: Where We Are

In Class 6 you learned the language: variables, `if`, loops, arrays, and functions that `return` an answer. Everything you wrote showed up as text in the Console. The page itself never changed.

Today the two halves meet. JavaScript is going to:

- **find** an element on your page,
- **listen** for something the user does to it — a click, some typing, a form being submitted,
- and **change** the page in response.

Find, listen, change. Almost every interactive thing you've ever used on a website is those three steps, repeated. By the end of this class your contact form will say "thank you" without reloading, and your pages will have a light/dark mode button.

One thing stays the same: **keep the Console open.** When something doesn't work today, the page will usually just sit there and do nothing. The reason will be in the Console.

---

## 2. What the DOM Is

When the browser loads your HTML file, it doesn't keep it as text. It reads the text once and builds a live model of the page in its memory: one **object** for every element, arranged like a family tree.

```
document
└── html
    ├── head
    │   └── title
    └── body
        ├── h1
        ├── p
        └── button
```

That model is the **DOM** — the Document Object Model. Four things to know about it:

- The HTML file is the **plan**. The DOM is the **building**. The browser draws the page from the DOM, not from the file.
- JavaScript can read the DOM and change it. When it does, the page on the screen updates straight away.
- Those changes **never touch your `.html` file**. Reload the page, and the browser builds a fresh DOM from the file. Your changes are gone.
- The **Elements** panel in dev tools shows the DOM — the live version — not your file. Watch it while your code runs.

The way in is an object called **`document`**. It stands for the whole page, and it has the tools for finding things inside it.

### Practice Now
Open any page you've built, and open the Console. Type `document.title` and press Enter. Then type this:

```js
document.querySelector("h1").textContent = "I changed this from the Console";
```

Look at the page. Look at the `<h1>` in the Elements panel. Then reload, and watch your change disappear.

---

## 3. Setting Up: Where the Script Goes

Make a folder called `dom-practice/` with three files. You'll use them for every "Practice Now" in this class.

**`index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>DOM Practice</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1 id="main-title">DOM Practice</h1>
    <p class="intro">This paragraph is about to change.</p>
    <button type="button" id="action-button">Click me</button>

    <script src="app.js"></script>
</body>
</html>
```

**`style.css`**

```css
body {
    font-family: system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    padding: 24px;
}

.highlight {
    background-color: #fff3bf;
}

.hidden {
    display: none;
}
```

**`app.js`**

```js
const mainTitle = document.querySelector("#main-title");

console.log(mainTitle);
console.log(mainTitle.textContent);
```

Open it with Live Server. The Console shows the `<h1>` element itself, and then its text: `DOM Practice`.

### Why the script goes at the end of `<body>`
In Class 6 you put `<script>` just before `</body>` out of habit. Now it matters. The browser builds the DOM from the top of the file downwards, and it runs a script the moment it reaches the `<script>` tag. If the script is in the `<head>`, it runs **before the `<h1>` exists**.

Try it. Move the `<script>` line up into the `<head>`, and save:

```
null
Uncaught TypeError: Cannot read properties of null (reading 'textContent')
    at app.js:4:23
```

`null` means "I looked, and there's nothing there". The script went looking for `#main-title` before the browser had built it. You'll see this error more than any other today, so learn to read it: **"Cannot read properties of null" means the element wasn't found.**

There are two ways to fix it:

```html
<!-- 1. At the end of <body> — what this course uses -->
    <script src="app.js"></script>
</body>

<!-- 2. In the <head>, with defer: "wait until the page is built, then run" -->
<head>
    <script src="app.js" defer></script>
</head>
```

Both work. Pick one and stick to it.

> In this class, buttons that only exist for JavaScript get `type="button"` (Class 2). It stops them submitting a form by accident. And use a real `<button>` for anything clickable — it works with the keyboard for free. A clickable `<div>` doesn't.

### Practice Now
Set up the three files. Break it by moving the script into the `<head>`, and read the error. Fix it with `defer`. Then move the script back to the end of `<body>` and take `defer` off again.

✅ **Checkpoint:** You know what `null` means when it turns up in an error, and the two places a script can safely go.

---

## 4. Finding an Element: `querySelector`

`document.querySelector(...)` takes a **CSS selector** — in quotes — and gives you back the **first** element that matches. You already know the selectors, from Class 3:

```js
const mainTitle = document.querySelector("#main-title");    // by id
const intro = document.querySelector(".intro");             // by class
const firstButton = document.querySelector("button");       // by tag name
const navLink = document.querySelector("nav a");            // a descendant
```

Things to notice:

- The `#` and the `.` matter, exactly as they do in CSS. `"intro"` with no dot looks for an `<intro>` tag.
- Store the element in a `const`, so you find it once and use it many times.
- If nothing matches, you get `null` — and the error from Section 3 as soon as you try to use it.
- If several elements match, you get the **first** one only. (Section 11 is about getting all of them.)

For elements your JavaScript needs, an **`id`** is the most reliable hook: there can only be one of each on a page. Classes are for styling groups; ids are for "this exact element".

> You'll see `document.getElementById("main-title")` in other people's code. It does the same job as `querySelector("#main-title")`. One tool is enough for this course.

### Practice Now
In `app.js`, find the title, the paragraph, and the button, each in its own `const`, and log all three. Then log `document.querySelector(".does-not-exist")` and see what you get. Finally, hover over one of the logged elements in the Console and watch the page.

---

## 5. Changing What It Says: `textContent`

Every element has a `textContent` property: the text inside it. You can read it, and you can replace it.

```js
const intro = document.querySelector(".intro");

console.log(intro.textContent);   // This paragraph is about to change.

intro.textContent = "Changed by JavaScript!";
```

Save, and the paragraph on the page is different — even though your HTML file still has the old words.

### `innerHTML` — and why to be careful
`textContent` treats everything you give it as plain text. If you put tags in it, the tags show up on the page as text:

```js
intro.textContent = `Visit <a href="https://example.com">this page</a>.`;
// The page shows:  Visit <a href="https://example.com">this page</a>.
```

`innerHTML` reads the string as **HTML** and builds real elements from it:

```js
intro.innerHTML = `Visit <a href="https://example.com">this page</a>.`;
// The page shows:  Visit this page.   — with a working link
```

That's powerful, and it's exactly why it's risky. If the string includes something **a user typed**, whatever they typed gets treated as HTML too. A visitor could type tags into your form and break your layout, or do something much worse.

The rule for this course:

- **`textContent` for text. Always, for anything a user typed.**
- `innerHTML` only for HTML that **you** wrote yourself in the code.
- One safe and handy use: `element.innerHTML = "";` empties an element completely.

### Practice Now
Change the `<h1>` to your own name with `textContent`. Then put the same tag-filled string into the paragraph twice — once with `textContent`, once with `innerHTML` — and compare what appears on the page and in the Elements panel.

---

## 6. Events: Making Something Happen on a Click

So far your code runs once, when the page loads. An **event** is something that happens later: a click, a key press, a form being submitted. You tell the browser: "when *this* happens to *that* element, run *this function*."

```js
const intro = document.querySelector(".intro");
const actionButton = document.querySelector("#action-button");

function changeIntro() {
    intro.textContent = "You clicked the button!";
}

actionButton.addEventListener("click", changeIntro);
```

`addEventListener` takes two things:

1. The **name of the event**, as a string: `"click"`.
2. The **function to run** when it happens: `changeIntro`.

Nothing happens when the page loads. The browser keeps hold of your function and **calls it for you**, every time the button is clicked.

### No brackets!
Look closely: it's `changeIntro`, not `changeIntro()`. You're handing over the function itself, for the browser to call later. With brackets, you'd be calling it **right now**, as the page loads — once — and the button would do nothing afterwards:

```js
actionButton.addEventListener("click", changeIntro);     // ✅ "here's the function — call it on a click"
actionButton.addEventListener("click", changeIntro());   // ❌ runs once at page load; the click does nothing
```

There's no error for the second one. It's one of the most common bugs in this class.

### The short way: arrow functions
Most of the time the function is only needed in that one place. So you can write it right there, without a name:

```js
actionButton.addEventListener("click", () => {
    intro.textContent = "You clicked the button!";
});
```

`() => { ... }` is an **arrow function**. It's a function, just written differently:

- `()` — the parameters go here, exactly like the brackets after a function's name.
- `=>` — the arrow. Read it as "does this".
- `{ ... }` — the body.

Watch the ending: `});`. The `}` closes the function, the `)` closes `addEventListener(`, and the `;` ends the statement.

Both styles do the same thing. Use an arrow function for short code that's used in one place. Use a named function when the code is long, or when two different events need to run it.

### Remembering things between clicks
The function runs afresh on every click. To remember something from one click to the next, keep it in a variable **outside** the function:

```js
let clicks = 0;

actionButton.addEventListener("click", () => {
    clicks++;
    intro.textContent = `You have clicked ${clicks} times.`;
});
```

If `let clicks = 0;` were inside the function, it would be reset to 0 on every click. (It's the same rule as the running total in Class 6: make it outside, change it inside.)

### The recipe
Every interactive feature you build today has the same three steps:

1. **Find** the elements, and keep them in `const`s at the top of the file.
2. **Listen** for an event on one of them.
3. **Change** the page inside the function.

### Practice Now
Make the button change the paragraph's text when it's clicked — first with a named function, then rewritten as an arrow function. Then build the click counter above. Finally, put brackets after the function's name on purpose and watch what goes wrong.

✅ **Checkpoint:** You can make a click change the page, and you can explain why the function is passed without brackets.

---

## 7. Changing How It Looks: `classList` and `style`

The best way to change how an element looks is **not** to set its colours from JavaScript. It's to write the look in your CSS as a class, and let JavaScript switch that class on and off.

Your `style.css` already has `.highlight`. Now:

```js
actionButton.addEventListener("click", () => {
    intro.classList.toggle("highlight");
});
```

Click once: the paragraph gets a yellow background. Click again: it's gone. Watch the `class` attribute change in the Elements panel as you click.

| Method | What it does |
|---|---|
| `element.classList.add("highlight")` | adds the class (does nothing if it's already there) |
| `element.classList.remove("highlight")` | removes it |
| `element.classList.toggle("highlight")` | adds it if it's missing, removes it if it's there |
| `element.classList.contains("highlight")` | gives back `true` or `false` |

> **No dot here.** It's `classList.add("highlight")`, not `classList.add(".highlight")`. `querySelector` needs the dot, because its string could be any kind of selector. `classList` only ever deals with classes, so the dot would become part of the name — and you'd get a class called `.highlight` that your CSS never matches. There's no error to warn you.

### Showing and hiding
One class does a lot of work in this class:

```css
.hidden {
    display: none;
}
```

`classList.add("hidden")` makes an element vanish. `classList.remove("hidden")` brings it back. Put the `.hidden` rule at the **bottom** of your stylesheet, so it wins over any other `display` rule with the same strength (the cascade, Class 3).

### `style` — for one-off values
You can also set a CSS property directly:

```js
intro.style.color = "crimson";
intro.style.backgroundColor = "#fff3bf";
intro.style.fontSize = "1.5rem";
```

Two differences from CSS:

- Property names are in **camelCase**: `background-color` becomes `backgroundColor`, and `font-size` becomes `fontSize`. (A hyphen means minus in JavaScript.)
- Values are **strings**, with their units: `"1.5rem"`, not `1.5`.

### Which one?
Use **classes** almost always. The look stays in your stylesheet, where it belongs, and one class can change ten properties at once. Use **`style`** only when the value is worked out by the code — a random colour, or a width that comes from a number.

### Practice Now
Make the button toggle `.highlight` on the paragraph. Add a second button that hides and shows the paragraph with `.hidden`. Then use `classList.contains` so the second button's own text switches between `Hide` and `Show`.

---

## 8. Attributes and Form Values

### Attributes
You can read and change any attribute — `src`, `alt`, `href` — with two methods:

```html
<img id="photo" src="https://picsum.photos/300/200?random=1" alt="Placeholder photo 1">
```

```js
const photo = document.querySelector("#photo");

console.log(photo.getAttribute("alt"));   // Placeholder photo 1

photo.setAttribute("src", "https://picsum.photos/300/200?random=2");
photo.setAttribute("alt", "Placeholder photo 2");
```

`setAttribute` takes the attribute's name and its new value. Change an image's `src`, and the picture on the page changes. Remember to change the `alt` as well.

### What the user typed: `.value`
For form controls, the thing you want is what the user has typed or chosen **right now**. That's the `value` property:

```html
<label for="quantity">Quantity</label>
<input type="number" id="quantity" value="2">

<input type="checkbox" id="gift">
<label for="gift">This is a gift</label>

<button type="button" id="order-button">Order</button>
<p id="summary"></p>
```

```js
const quantityInput = document.querySelector("#quantity");
const giftCheckbox = document.querySelector("#gift");
const orderButton = document.querySelector("#order-button");
const summary = document.querySelector("#summary");

orderButton.addEventListener("click", () => {
    const quantity = Number(quantityInput.value);
    const total = quantity * 1500;

    summary.textContent = `${quantity} items, total ${total}. Gift: ${giftCheckbox.checked}`;
    orderButton.disabled = true;
});
```

Three properties to know:

| Property | On | What it holds |
|---|---|---|
| `.value` | inputs, textareas, selects | what's typed or chosen — **always a string** |
| `.checked` | checkboxes and radio buttons | `true` or `false` |
| `.disabled` | buttons and inputs | `true` greys it out so it can't be used; `false` switches it back on |

### `.value` is always a string
Even for `type="number"`. This is the `+` trap from Class 6, and here's where it bites:

```js
console.log(quantityInput.value + 1);           // "21" — joined
console.log(Number(quantityInput.value) + 1);   // 3
```

Convert with `Number()` before you do any maths. And watch out for one surprise: `Number("")` is `0`, not `NaN`. An empty box quietly turns into zero, so check for an empty string **first** if zero would be a wrong answer.

### Read it when you need it
Read `.value` **inside** the function that runs on the event. If you read it at the top of the file, you get whatever was in the box when the page loaded — usually nothing — and that's the value your code is stuck with.

### `.trim()` — tidy up what people type
People leave spaces at the start and the end of what they type. `.trim()` gives back the string without them:

```js
const typed = "   Ada  ";

console.log(typed.trim());            // "Ada"
console.log("   ".trim() === "");     // true
```

So the way to ask "did they actually type anything?" is `input.value.trim() === ""`.

### Practice Now
Add an `<img>` to your practice page, and make a button swap its `src` and `alt` to a different photo. Then build the order example above. Try it with the quantity box emptied — what total do you get, and why?

---

## 9. More Events, and the `event` Object

`click` is one event. Here are the five you need for this course:

| Event | When it happens | Usually on |
|---|---|---|
| `click` | the element is clicked (or a button is pressed with the keyboard) | buttons — anything |
| `input` | the value changes — on **every** keystroke | text inputs, textareas |
| `change` | the user settles on a choice | selects, checkboxes, radio buttons |
| `submit` | a form is submitted, by its button or by the Enter key | the `<form>` itself |
| `keyup` | a key is let go | inputs |

Here's `input` in action — a line of text that follows what you type:

```html
<label for="nickname">Nickname</label>
<input type="text" id="nickname">

<p>Hello, <span id="preview">stranger</span>!</p>
```

```js
const nicknameInput = document.querySelector("#nickname");
const preview = document.querySelector("#preview");

nicknameInput.addEventListener("input", () => {
    preview.textContent = nicknameInput.value;
});
```

### The `event` object
When the browser calls your function, it passes in one argument: an object full of details about what just happened. To use it, give your function a parameter. Everybody calls it `event`:

```js
nicknameInput.addEventListener("input", (event) => {
    preview.textContent = event.target.value;
});
```

| | What it is |
|---|---|
| `event.target` | the element the event happened **to** — here, the input |
| `event.key` | for keyboard events: which key, such as `"Enter"`, `"Escape"`, or `"a"` |
| `event.preventDefault()` | "don't do what you'd normally do" — the next section is all about this |

`event.key` lets you react to one particular key:

```js
nicknameInput.addEventListener("keyup", (event) => {
    if (event.key === "Escape") {
        nicknameInput.value = "";
        preview.textContent = "stranger";
    }
});
```

Yes — you can **set** `.value` as well as read it. That's how you empty a box.

`event.target` doesn't look very useful yet, because you already have `nicknameInput` in a variable. It becomes essential in Section 11, when one function looks after many elements.

### Practice Now
Build the nickname example. Then add a `<select>` with three options and a paragraph underneath, and use the `change` event to show `You picked …` whenever the choice changes. Finally, log `event` itself from inside one of your functions and open it up in the Console — look at how much is in there.

---

## 10. Forms: `submit` and `preventDefault`

Back in Class 2 you were told: "When you submit, the page will just reload and clear. In Class 7 you'll handle submissions properly." This is that moment.

Sending the data and reloading the page is the form's **default** behaviour. To handle the form yourself, you listen for the `submit` event **on the form**, and tell the browser not to do its usual thing:

```html
<form id="signup-form">
    <label for="email">Email address</label>
    <input type="email" id="email" name="email" required>

    <button type="submit">Sign up</button>
</form>

<p id="result"></p>
```

```js
const signupForm = document.querySelector("#signup-form");
const emailInput = document.querySelector("#email");
const result = document.querySelector("#result");

signupForm.addEventListener("submit", (event) => {
    event.preventDefault();

    const email = emailInput.value.trim();

    result.textContent = `Thanks! We'll write to ${email}.`;
    emailInput.value = "";
});
```

Line by line:

- `"submit"` on the **form** — not `"click"` on the button. A form can be submitted by pressing Enter in a field as well, and `submit` catches both.
- `(event)` — you need the event object this time, so the function takes it as a parameter.
- `event.preventDefault();` — goes **first**. It cancels the reload. Everything after it is your own replacement for what the browser would have done.
- Then the usual: read the value, change the page.

`preventDefault` isn't only for forms. Call it in a **link's** `click` event, and the browser doesn't follow the link — useful when an `<a>` should open something on the page instead of going somewhere else.

### The browser still checks the form for you
Your Class 2 validation attributes — `required`, `type="email"`, `minlength` — are checked **before** the `submit` event happens. If a field fails, the browser shows its error bubble, and your function doesn't run at all. So inside your function, you can trust that the built-in rules have passed.

### How to tell whether the page reloaded
Put `console.log("app.js loaded");` on the first line of your file. If that line appears again when you submit, the page reloaded: your `preventDefault` is missing, or isn't being reached. Another sign is a `?email=…` appearing on the end of the address in the address bar.

### Practice Now
Build the sign-up form. Submit it empty, then with `hello` (not an email), then with a real-looking address. Next, delete the `preventDefault` line and submit again — watch the Console and the address bar. Put the line back.

✅ **Checkpoint:** You can explain what `preventDefault` prevents, and why you listen for `submit` on the form and not `click` on the button.

---

## 11. Working With Many Elements: `querySelectorAll` and `forEach`

`querySelector` gives you the first match. `querySelectorAll` gives you **all** of them, as a list.

```html
<section class="swatches">
    <button type="button" class="swatch">Red</button>
    <button type="button" class="swatch">Green</button>
    <button type="button" class="swatch">Blue</button>
</section>

<p id="choice">Nothing chosen yet.</p>
```

```js
const swatches = document.querySelectorAll(".swatch");

console.log(swatches.length);   // 3
console.log(swatches[0]);       // the first button
```

The list works like an array: it has a `.length`, and indexes that start at 0. If nothing matches, you get an empty list (length 0), not `null`.

### A list is not an element
You can't add a listener to the whole list:

```js
swatches.addEventListener("click", ...);
// ❌ TypeError: swatches.addEventListener is not a function
```

You have to go through the list and deal with each element in turn.

### `forEach` — "for each one, do this"
You could use the `for` loop from Class 6, and it works. But lists have a shorter way built in:

```js
// The Class 6 way
for (let i = 0; i < swatches.length; i++) {
    console.log(swatches[i].textContent);
}

// The forEach way — the same result
swatches.forEach((swatch) => {
    console.log(swatch.textContent);
});
```

`forEach` takes a function, and runs it once for every item in the list, passing the item in. You choose the parameter's name: use the singular of the list's name — `swatches` and `swatch` — and the code reads like a sentence. There's no counter to get wrong. (Arrays have `forEach` too.)

### Clear them all, then mark the one
Here's the pattern for "only one can be selected at a time". Add `.selected { border: 3px solid #222222; }` to your CSS, then:

```js
const swatches = document.querySelectorAll(".swatch");
const choice = document.querySelector("#choice");

swatches.forEach((swatch) => {
    swatch.addEventListener("click", () => {
        swatches.forEach((other) => {
            other.classList.remove("selected");
        });

        swatch.classList.add("selected");
        choice.textContent = `You chose ${swatch.textContent}.`;
    });
});
```

Read it from the outside in. The outer `forEach` gives every button its own click listener. When one is clicked, the inner `forEach` takes `selected` off **all** of them, and then the clicked one gets it back. You'll use "clear them all, then mark the one" for tabs, galleries, and menus.

### Partners: the same index in two lists
`forEach` can also hand you the **index**, as a second parameter. That's how you link an item in one list to its partner in another:

```html
<button type="button" class="question">What is the DOM?</button>
<p class="answer hidden">The browser's live model of the page.</p>

<button type="button" class="question">What is an event?</button>
<p class="answer hidden">Something that happens on the page, like a click.</p>
```

```js
const questions = document.querySelectorAll(".question");
const answers = document.querySelectorAll(".answer");

questions.forEach((question, i) => {
    question.addEventListener("click", () => {
        answers[i].classList.toggle("hidden");
    });
});
```

Question 0 opens answer 0, and question 1 opens answer 1. It's the "parallel arrays" idea from Class 6, with elements instead of numbers.

### One function, many elements: `event.target`
If every button should run the **same named function**, that function needs a way to know which button was clicked. That's `event.target`:

```js
function announce(event) {
    console.log(`You clicked: ${event.target.textContent}`);
}

swatches.forEach((swatch) => {
    swatch.addEventListener("click", announce);
});
```

You can go one step further and put a **single** listener on the parent. A click on a child is also a click on everything it sits inside, so the parent hears about it — and `event.target` is the child that was actually clicked:

```js
const taskList = document.querySelector("#tasks");

taskList.addEventListener("click", (event) => {
    if (event.target.classList.contains("task")) {
        event.target.classList.toggle("done");
    }
});
```

The `if` is there because a click on the list's own padding would have the list itself as the target.

### Practice Now
Build the three swatch buttons, with "clear them all, then mark the one". Then make each swatch also change the page's background: `document.body.style.backgroundColor = swatch.textContent;` — the words `Red`, `Green`, and `Blue` are real CSS colour names. (`document.body` is a shortcut straight to the `<body>` element.)

---

## 12. Creating and Removing Elements

JavaScript can build brand-new elements and add them to the page. It takes three steps:

```html
<ul id="shopping-list"></ul>
```

```js
const shoppingList = document.querySelector("#shopping-list");

const item = document.createElement("li");   // 1. create it — it isn't on the page yet
item.textContent = "Bread";                  // 2. fill it in
shoppingList.append(item);                   // 3. put it on the page, inside the list
```

- `document.createElement("li")` makes an empty `<li>`. It exists only in memory, and nobody can see it.
- You set it up the same way as any other element: `textContent`, `classList`, `setAttribute`, even `addEventListener`.
- `parent.append(child)` adds it as the **last** thing inside the parent. Only now does it appear.

To take an element off the page, call `.remove()` on it.

Put those together in a function, and you can add as many items as you like — each one with its own button that removes it:

```js
function addItem(text) {
    const item = document.createElement("li");
    item.textContent = text;

    const deleteButton = document.createElement("button");
    deleteButton.textContent = "Remove";
    deleteButton.addEventListener("click", () => {
        item.remove();
    });

    item.append(deleteButton);
    shoppingList.append(item);
}

addItem("Bread");
addItem("Milk");
addItem("Eggs");
```

Each time `addItem` runs, it makes a new `item` and a new `deleteButton`, and that button's function remembers **its own** `item`. Click the second `Remove`, and only the milk goes.

Two things to watch:

- **Set the text first, then append the children.** Setting `textContent` replaces *everything* inside an element. If you appended the button and then set the text, the button would be wiped out.
- **This is the safe way to show what a user typed.** Because the text goes in through `textContent`, it's always treated as text — never as HTML. That's why you build elements this way instead of gluing user input into an `innerHTML` string.

### Practice Now
Build the shopping list above. Then add a text input and an `Add` button to the page, so that clicking `Add` calls `addItem` with whatever is in the box, and then empties the box. Don't add anything if the box is empty or holds only spaces.

---

## 13. Objects: Data With Names

You've been using objects for two classes without making a fuss about it. `console.log`, `Math.PI`, `word.length`, `event.target`, `intro.classList` — every one of those is "an object, a dot, and a name". The whole DOM is made of objects.

An **object** is a bundle of named values. Each named value is a **property**. You can make your own:

```js
const project = {
    title: "Photo Gallery",
    topic: "CSS Grid",
    classNumber: 5
};

console.log(project.title);         // Photo Gallery
console.log(project.classNumber);   // 5

project.topic = "Grid and responsive design";   // change a property
```

Curly braces, then `name: value` pairs with commas between them. You read a property with a dot. Ask for one that doesn't exist, and you get `undefined`.

### Array or object?
- An **array** is an ordered list of similar things. You get at them by **position**: `cities[0]`.
- An **object** is one thing, with several facts about it. You get at them by **name**: `project.title`.

Put them together — an **array of objects** — and you have a table of data: each object is a row.

### Building the page from data
This is where the last three sections come together. Describe your content once, as data, and let a loop build the HTML:

```html
<section id="projects" class="cards"></section>
```

```js
const projects = [
    { title: "About Me", topic: "HTML and CSS" },
    { title: "Photo Gallery", topic: "CSS Grid" },
    { title: "Calculator Toolkit", topic: "JavaScript" }
];

const projectsSection = document.querySelector("#projects");

projects.forEach((project) => {
    const card = document.createElement("article");
    card.classList.add("card");

    const heading = document.createElement("h3");
    heading.textContent = project.title;

    const description = document.createElement("p");
    description.textContent = `Built with ${project.topic}.`;

    card.append(heading);
    card.append(description);
    projectsSection.append(card);
});
```

Three cards appear on the page. To add a fourth, you add one line to the array — you don't write any more HTML. Style `.cards` and `.card` in your CSS with Grid or Flexbox, exactly as if you'd typed the cards by hand.

### Practice Now
Type in the example, and add two projects of your own to the array. Then give each object a third property, `classNumber`, and show it on the card as well. Check the result in the Elements panel: the HTML is all there, and you didn't write any of it.

---

## 14. Guided Practice: A Theme Toggle and a "Thank You" Form

This is the main build for Class 7, in two parts on one page: a button that switches the page between light and dark, and a contact form that thanks the visitor by name without reloading.

Work on a **copy of your own contact page** from Class 5 if you can. Your form has more fields than the one below, but the JavaScript is the same. If you don't have it to hand, use this small version.

### Requirements
- [ ] The script is loaded at the end of `<body>`
- [ ] **Part A:** a `type="button"` button in the header that toggles a `dark` class on `<body>`
- [ ] Both themes live in the **CSS**. The JavaScript only switches the class — it sets no colours
- [ ] The button's own text switches between `🌙 Dark` and `☀️ Light`
- [ ] **Part B:** the form is handled on its `submit` event, with `preventDefault`
- [ ] On submit, the form disappears and a message appears that includes the name the visitor typed
- [ ] The message goes in with `textContent`, not `innerHTML`
- [ ] The browser's own validation (`required`, `type="email"`, `minlength`) still works
- [ ] No red in the Console

**`index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Contact</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header class="site-header">
        <p class="brand">My Site</p>
        <button type="button" id="theme-toggle">🌙 Dark</button>
    </header>

    <main>
        <h1>Get in touch</h1>

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
    </main>

    <script src="app.js"></script>
</body>
</html>
```

Two things were added for JavaScript's benefit: an `id` on the form, and an empty, hidden paragraph that's waiting for the thank-you message.

**`style.css`**

```css
/* Reset */
*, *::before, *::after {
    box-sizing: border-box;
}

/* Page — the light theme is the default */
body {
    margin: 0;
    font-family: system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    line-height: 1.6;
    color: #222222;
    background-color: #f4f4f4;
}

.site-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px clamp(16px, 5vw, 48px);
    background-color: #ffffff;
    border-bottom: 1px solid #dddddd;
}

.brand {
    margin: 0;
    font-weight: 700;
}

main {
    max-width: 30rem;
    margin: 0 auto;
    padding: 24px clamp(16px, 5vw, 48px);
}

/* Form */
.field {
    margin-bottom: 16px;
}

label {
    display: block;
    margin-bottom: 4px;
}

input,
textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #999999;
    font-family: system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    font-size: 1rem;
    color: #222222;
    background-color: #ffffff;
}

button {
    padding: 10px 16px;
    border: none;
    font-size: 1rem;
    color: #ffffff;
    background-color: #1a56db;
    cursor: pointer;
}

.thanks {
    padding: 16px;
    border: 1px solid #5aa46b;
    background-color: #e6f4ea;
}

/* Dark theme — only the colours change */
.dark {
    color: #eeeeee;
    background-color: #121212;
}

.dark .site-header {
    background-color: #1e1e1e;
    border-bottom: 1px solid #333333;
}

.dark input,
.dark textarea {
    border: 1px solid #555555;
    color: #eeeeee;
    background-color: #1e1e1e;
}

.dark .thanks {
    background-color: #1e3a29;
}

/* Keep this last, so it wins over any display rule above it */
.hidden {
    display: none;
}
```

The dark theme is nothing new: it's a class, plus descendant selectors (Class 3). `.dark` will sit on the `<body>`, so `.dark input` means "any input inside a dark page".

**`app.js`**

```js
console.log("app.js loaded");

// ---------- Part A: the theme toggle ----------

const themeToggle = document.querySelector("#theme-toggle");

themeToggle.addEventListener("click", () => {
    document.body.classList.toggle("dark");

    if (document.body.classList.contains("dark")) {
        themeToggle.textContent = "☀️ Light";
    } else {
        themeToggle.textContent = "🌙 Dark";
    }
});

// ---------- Part B: the "thank you" message ----------

const contactForm = document.querySelector("#contact-form");
const nameInput = document.querySelector("#name");
const thanks = document.querySelector("#thanks");

contactForm.addEventListener("submit", (event) => {
    event.preventDefault();

    const visitorName = nameInput.value.trim();

    thanks.textContent = `✅ Thanks, ${visitorName} — we'll be in touch.`;

    contactForm.classList.add("hidden");
    thanks.classList.remove("hidden");
});
```

Type it by hand — don't paste. Build Part A first, and get it working before you start Part B. Save, then check the page **and** the Console after every few lines.

### Test it

| Do this | You should see |
|---|---|
| Load the page | `app.js loaded` in the Console, once. A light page, with a button that says `🌙 Dark` |
| Click the theme button | The page, header, and inputs turn dark. The button now says `☀️ Light`. In the Elements panel, `<body>` has `class="dark"` |
| Click it again | Back to light; the button says `🌙 Dark` again |
| Click `Send message` with every field empty | The browser's own "fill in this field" bubble. Nothing else changes |
| Type a name, an email, and a message shorter than 10 characters, then send | The browser complains about the message. Still nothing else changes |
| Fill everything in properly, and send | The form disappears. A green box says `✅ Thanks, Ada Lovelace — we'll be in touch.` with the name you typed |
| Look at the Console and the address bar | `app.js loaded` still appears only **once**, and the address has no `?name=…` on the end. The page did not reload |

### Now break it, then fix it
Do these one at a time, and undo each one afterwards.

1. Delete `event.preventDefault();`, and submit the form.
2. Change `"#contact-form"` to `"contact-form"` (no `#`), and read the Console.
3. Change `classList.toggle("dark")` to `classList.toggle(".dark")`. Click the button, and look at `<body>` in the Elements panel.

### Acceptance criteria
- Every row of the test table behaves as described.
- `app.js` contains no colour values. Both themes are entirely in `style.css`.
- The thank-you message is written with `textContent`. Try typing `<h1>Hi</h1>` as your name: it must appear as plain text, not as a giant heading.
- The form's fields, labels, and validation attributes are unchanged from before.
- You can explain what went wrong in each of the three "break it" experiments.

✅ **Checkpoint:** Two real features, in about 25 lines of JavaScript — and both are just find, listen, change.

---

## 15. Troubleshooting

| Problem | Likely cause |
|---|---|
| `Cannot read properties of null (reading '…')` | `querySelector` found nothing. A typo in the selector, a missing `.` or `#`, or the script is running before the element exists (it's in the `<head>` without `defer`). |
| Clicking does nothing, and there's no error | Put `console.log("clicked");` on the first line of the function. If it never appears: the listener is on the wrong element; the event name is wrong (it's `"click"`, not `"onclick"` or `"Click"`); or you wrote `addEventListener("click", doThing())` with brackets. |
| `….addEventListener is not a function` | You called it on a `querySelectorAll` list. Use `forEach`, and add the listener to each element. |
| The class is added, but nothing looks different | Check the element in the Elements panel. Is the class really there? If it shows as `.dark` with a dot, take the dot out of `classList.add(".dark")`. If the class is right, the CSS rule is missing, misspelled, or being beaten by another rule. |
| `.hidden` doesn't hide the element | A later rule sets `display` on it and wins. Move `.hidden` to the bottom of the stylesheet. |
| A style set from JS does nothing | The property name must be camelCase (`backgroundColor`), and the value must be a string with its unit (`"20px"`). A misspelled property is ignored without an error. |
| The page flashes and the form empties on submit | The page reloaded. `event.preventDefault()` is missing, you forgot the `(event)` parameter, or you're listening for `click` on the button instead of `submit` on the form. |
| Numbers get joined: `510` instead of `15` | `.value` is a string. Wrap it: `Number(input.value)`. |
| An empty box counts as `0` | `Number("")` is `0`. Check `input.value.trim() === ""` before converting. |
| The value is always empty, or always the same | You read `.value` once, at the top of the file. Read it **inside** the function that runs on the event. |
| Tags appear on the page as text | You used `textContent` — which is correct for anything a user typed. Use `innerHTML` only for HTML you wrote yourself. |
| A new element never appears | You created it but never appended it. `createElement` alone doesn't put it on the page. |
| The button inside my new element vanished | You set `textContent` *after* appending the button. Setting the text replaces everything inside. Set the text first, or put the text in its own `<span>`. |
| The counter goes back to the start on every click | The variable is declared inside the function. Move it outside, above the listener. |
| Everything resets when I reload | That's normal. JavaScript changes the DOM, not your file. |

---

## 16. Self-Check: Can You Answer These?

Try without scrolling back.

1. What is the DOM? Why do your changes disappear when you reload?
2. What does `querySelector` give you when nothing matches? What error does that lead to?
3. Why does the `<script>` tag go at the end of `<body>`? What's the other way to solve the same problem?
4. `textContent` or `innerHTML` — which is the safe choice for something a user typed, and why?
5. In `button.addEventListener("click", handleClick)`, why is there no `()` after `handleClick`?
6. Write a click listener for an element called `plusButton` that adds 1 to a variable called `count`, using an arrow function.
7. Name three things `classList` can do. Why is switching a class usually better than setting `.style`?
8. What type is `input.value`? What must you do before using it in a sum?
9. What does `event.preventDefault()` do on a form's `submit` event? Why listen on the form instead of the button?
10. What does `querySelectorAll` give you, and how do you add a click listener to every element in it?

---

## 17. Homework

1. **Add one new interactive feature to an earlier page** (the course homework). Work on a copy. Pick one of these — or do all three:
   - **About Me:** a `Read more` button that shows and hides an extra paragraph of your bio. The button's text switches between `Read more` and `Read less`.
   - **Photo gallery (Class 5):** click any photo to make it bigger, and click again to shrink it — by toggling a class.
   - **Blog homepage:** a text box that filters the posts as you type, hiding every `<article>` that doesn't contain the word.

   Whichever you choose:
   - [ ] The look is in the CSS, as a class; the JavaScript only switches classes
   - [ ] Anything clickable is a real `<button>` (or was already something clickable)
   - [ ] The script is at the end of `<body>`, and there's no red in the Console
   - [ ] The page still works at 375px, 768px, and 1280px

2. **Finish the guided practice on your own contact page**, if you used the small version above.

3. *(Optional)* Add the theme toggle to your About Me page as well. You'll need a `.dark` section in that page's stylesheet.

For a lot more practice on this class — counters, accordions, a to-do list, tabs, live form validation, a quiz, and debugging exercises with answers — see the **Class 7** section of [`assignments.md`](assignments.md).

---

## What's Next

Class 8 is the **capstone**: one responsive, interactive portfolio page that uses everything from the last seven classes — semantic HTML, a Flexbox navbar, a Grid of project cards, mobile-first media queries, and JavaScript for the theme toggle and the contact form. Nearly every piece of it is something you've already built. Gather your 🧵 files.
