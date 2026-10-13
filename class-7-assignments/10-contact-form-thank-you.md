# Assignment 10 — Contact Form "Thank You"

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~40 min · 🧵 keep this file
**Prereqs:** Class 5 Assignment 13 (responsive contact page) done; Class 7 §10, §14 Part B
**Build in:** `work/10-contact-form-thank-you/index.html` + `style.css` + `app.js`

---

## Goal

Make the contact form you've been building since Class 2 finally *do* something: on submit, the form disappears and the page thanks the visitor by name — without reloading. This is the other half of the Class 7 hands-on.

## What you'll practice

- The `submit` event and `event.preventDefault()`
- Reading a field's `.value`, and tidying it with `.trim()`
- Showing and hiding with a `.hidden` class
- Writing a user's text into the page safely

## Instructions

1. Copy your responsive contact page in — [work/README.md](work/README.md) has the folder.
2. In the HTML, make three small additions:
   - an `id` on the `<form>`
   - an empty paragraph after the form: `<p id="thanks" class="thanks hidden"></p>`
   - the `<script>` tag at the end of `<body>`
3. In the CSS: add a `.thanks` rule (padding, a border, a background colour), and `.hidden { display: none; }` as the **last** rule in the file.
4. In `app.js`, listen for `submit` on the form. In the function:
   - call `event.preventDefault()`
   - read the name field's value, and `.trim()` it
   - set the paragraph's `textContent` to `✅ Thanks, {name} — we'll be in touch.` with the real name in it
   - add `hidden` to the form, and remove `hidden` from the paragraph
5. Test it with the table in the lesson (Class 7 §14, "Test it").

## Requirements

- [ ] The listener is on the form, for `submit`
- [ ] `event.preventDefault()` comes first in the function
- [ ] The message includes the name the visitor typed, with spaces trimmed off both ends
- [ ] The message is written with `textContent`, not `innerHTML`
- [ ] Every field, label, and validation attribute from Classes 2–5 is unchanged

## Acceptance criteria

- Submitting with empty required fields shows the browser's own error bubble. The form stays where it is.
- A valid submit hides the form and shows the message, with the right name.
- The page doesn't reload: `app.js loaded` is in the Console once, and the address has no `?name=…` on the end.
- Typing `<h1>Hi</h1>` as the name shows those characters as plain text.
- The two-column layout from Class 5 still works at 375px, 768px, and 1280px.

## Hints

<details><summary>Show hint</summary>

If the form won't hide, look at it in the Elements panel after you submit. If `hidden` is in its class list but it's still visible, another rule is setting `display` on the form and winning. Move `.hidden` to the very bottom of `style.css`.
</details>

## Stretch (optional)

`required` is satisfied by a name made only of spaces — try it. Your message would then read `Thanks,  — we'll be in touch.` Fix it: if the trimmed name is empty, show `✅ Thanks — we'll be in touch.` instead.
