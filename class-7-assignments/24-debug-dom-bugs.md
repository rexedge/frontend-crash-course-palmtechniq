# Assignment 24 — Debug: DOM Bugs

**Type:** Debug · **Difficulty:** ⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 7 §15 (troubleshooting)
**Build in:** `work/24-debug-dom-bugs/` — one folder per case (`a/`, `b/`, …)

---

## Goal

Each case is broken or behaving unexpectedly. Reproduce it, **fix it**, and write one sentence explaining the cause in your own words. Try before opening the answer.

Start each one in the Console. Is there a red message? Read all of it. If there isn't, put `console.log("got here");` inside the function and find out whether it runs at all.

---

## (a) `Cannot read properties of null (reading 'addEventListener')`

```html
<head>
    <meta charset="UTF-8">
    <title>My Page</title>
    <script src="app.js"></script>
</head>
<body>
    <button type="button" id="go">Go</button>
</body>
```

```js
const goButton = document.querySelector("#go");

goButton.addEventListener("click", () => {
    console.log("hi");
});
```

<details><summary>Show answer</summary>

The script is in the `<head>`, so it runs **before** the browser has built the `<button>`. `querySelector` finds nothing and gives back `null`, and `null` has no `addEventListener`. Move the `<script>` tag to the end of `<body>`, or add `defer` to it: `<script src="app.js" defer></script>`.
</details>

---

## (b) `Cannot read properties of null (reading 'classList')`

```html
<div class="box">A box</div>

<script src="app.js"></script>
```

```js
const box = document.querySelector("box");

box.classList.add("open");
```

<details><summary>Show answer</summary>

This time the script is in the right place — the selector is wrong. `querySelector` takes a CSS selector, and `"box"` with no dot means "a `<box>` tag". There isn't one, so the result is `null`. For a class, write `".box"`.
</details>

---

## (c) "Sent!" flashes for an instant, then the form is empty again

```js
const form = document.querySelector("#contact-form");
const message = document.querySelector("#message");

form.addEventListener("submit", () => {
    message.textContent = "Sent!";
});
```

<details><summary>Show answer</summary>

The function runs — and then the form does what forms do by default: it reloads the page, which throws your change away. Take the event as a parameter and cancel the default first:

```js
form.addEventListener("submit", (event) => {
    event.preventDefault();
    message.textContent = "Sent!";
});
```
</details>

---

## (d) `buttons.addEventListener is not a function`

```js
const buttons = document.querySelectorAll("button");

buttons.addEventListener("click", () => {
    console.log("clicked");
});
```

<details><summary>Show answer</summary>

`querySelectorAll` gives back a **list** of elements, and a list has no `addEventListener` — only the elements inside it do. Go through the list and add the listener to each one:

```js
buttons.forEach((button) => {
    button.addEventListener("click", () => {
        console.log("clicked");
    });
});
```
</details>

---

## (e) The page shows the tags as text, instead of a link

```js
const footerNote = document.querySelector("#footer-note");

footerNote.textContent = `<a href="#top">Back to top</a>`;
```
…the page literally shows `<a href="#top">Back to top</a>`.

<details><summary>Show answer</summary>

Strictly, this isn't a bug: `textContent` treats whatever you give it as plain text, and that's the safe behaviour. Because **you** wrote this HTML yourself, it's fine to switch to `footerNote.innerHTML = …` here. Never do that with anything a user typed.
</details>

---

## (f) The running total shows `05`, then `055`, then `0555`

```html
<label for="amount">Amount</label>
<input type="number" id="amount" value="5">
<button type="button" id="add-button">Add</button>

<p id="total">0</p>
```

```js
const amountInput = document.querySelector("#amount");
const addButton = document.querySelector("#add-button");
const totalDisplay = document.querySelector("#total");

let total = 0;

addButton.addEventListener("click", () => {
    total = total + amountInput.value;
    totalDisplay.textContent = total;
});
```

<details><summary>Show answer</summary>

`.value` is always a **string** — even from a `type="number"` input. So `0 + "5"` joins instead of adding, giving `"05"`, and it gets longer on every click. Convert it first: `total = total + Number(amountInput.value);`.
</details>

---

## (g) The message is already there when the page loads, and clicking does nothing

```js
const helloButton = document.querySelector("#hello-button");
const greeting = document.querySelector("#greeting");

function showGreeting() {
    greeting.textContent = "Hello there!";
}

helloButton.addEventListener("click", showGreeting());
```

<details><summary>Show answer</summary>

The brackets. `showGreeting()` **calls** the function straight away, while the page is loading — that's why the message is already there. `addEventListener` is then handed whatever the function returned, which is `undefined`, so there's nothing to run on a click. Pass the function itself, without brackets: `helloButton.addEventListener("click", showGreeting);`.
</details>

---

## (h) It always says "You typed: " and nothing else

```js
const nameInput = document.querySelector("#name");
const showButton = document.querySelector("#show-button");
const output = document.querySelector("#output");

const typed = nameInput.value;

showButton.addEventListener("click", () => {
    output.textContent = `You typed: ${typed}`;
});
```

<details><summary>Show answer</summary>

`nameInput.value` is read **once**, at the top of the file, when the page has just loaded and the box is empty. `typed` holds that empty string for ever. Read the value inside the function, so it's read afresh on every click:

```js
showButton.addEventListener("click", () => {
    output.textContent = `You typed: ${nameInput.value}`;
});
```
</details>

---

## Requirements

- [ ] All 8 cases reproduced, fixed, and checked in the browser
- [ ] A one-sentence cause for each, in your own words (not copied)
- [ ] For each case, a note of whether the Console showed a red message or stayed silent

## Acceptance criteria

- Every fixed case behaves as intended: the `Go` button logs `hi`; the box gets its class; `Sent!` stays on the page; every button logs `clicked`; the link is a real link; the total goes `5`, `10`, `15`; the greeting appears only after a click; and the output shows what was typed.
- You noticed that only **three** of the eight gave a red error message. The other five just did the wrong thing, quietly.
