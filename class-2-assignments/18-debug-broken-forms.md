# Assignment 18 — Debug: Broken Forms

**Type:** Debug · **Difficulty:** ⭐⭐ · **Time:** ~30 min
**Prereqs:** Class 2 §7–11
**Build in:** `work/18-debug-broken-forms/` — one file per snippet (`a.html`, `b.html`, …)

---

## Goal

Each snippet below has one or more bugs. For each: put it in a file, reproduce the problem in the browser, **fix it**, and write one sentence explaining the cause in your own words. Try before opening the answer.

---

## (a) Clicking the label doesn't focus the input

```html
<form>
  <label for="uname">Username</label>
  <input type="text" id="username" name="username">
</form>
```

<details><summary>Show answer</summary>

`for="uname"` doesn't match `id="username"`. Make them identical — e.g. `for="username"`, or change the `id` to `uname`. The `for`/`id` link is an exact string match.
</details>

---

## (b) Both radio buttons can be selected at the same time

```html
<form>
  <input type="radio" id="ship-standard" name="ship"> <label for="ship-standard">Standard</label>
  <input type="radio" id="ship-express" name="express"> <label for="ship-express">Express</label>
</form>
```

<details><summary>Show answer</summary>

Radios only behave as one group when they share the same `name`. Here one is `name="ship"` and the other `name="express"`. Set **both** to `name="delivery"` (or any single shared name).
</details>

---

## (c) The field is meant to be optional but the form still won't submit without it

```html
<form>
  <label for="nickname">Nickname</label>
  <input type="text" id="nickname" name="nickname" required="false">
  <button type="submit">Save</button>
</form>
```

<details><summary>Show answer</summary>

`required` is a **boolean attribute** — its mere presence means "required", regardless of the value. `required="false"` is still required. To make it optional, **remove the attribute entirely**.
</details>

---

## (d) The table headers aren't announced as headers / the structure is wrong

```html
<table>
  <tr><td>Day</td><td>Topic</td></tr>
  <tbody>
    <tr><td>Mon</td><td>HTML</td></tr>
    <tr><td>Wed</td><td>Forms</td></tr>
  </tbody>
</table>
```

<details><summary>Show answer</summary>

The header row uses `<td>` (data cells) and isn't wrapped in `<thead>`. Fix:
```html
<thead>
  <tr><th scope="col">Day</th><th scope="col">Topic</th></tr>
</thead>
```
</details>

---

## (e) Pressing the button does nothing — the form never submits

```html
<form>
  <label for="q">Question</label>
  <textarea id="q" name="q"></textarea>
  <button type="button">Send</button>
</form>
```

<details><summary>Show answer</summary>

`type="button"` is an inert button that does nothing without JavaScript. Inside a form you want `type="submit"` (or just `<button>Send</button>`, which defaults to submit).
</details>

---

## (f) The textarea won't show its starting text

```html
<form>
  <label for="bio">Bio</label>
  <textarea id="bio" name="bio" value="Write something about yourself"></textarea>
</form>
```

<details><summary>Show answer</summary>

`<textarea>` has no `value` attribute. Starting text goes **between the tags**:
```html
<textarea id="bio" name="bio">Write something about yourself</textarea>
```
(For a real hint that disappears on typing, use `placeholder` instead.)
</details>

---

## (g) The dropdown starts on a real option instead of a prompt

```html
<label for="plan">Plan</label>
<select id="plan" name="plan">
  <option value="basic">Basic</option>
  <option value="pro">Pro</option>
  <option value="team">Team</option>
</select>
```

<details><summary>Show answer</summary>

Add a placeholder option first, `disabled` so it can't be re-chosen and `selected` so it shows initially:
```html
<option value="" disabled selected>Choose a plan</option>
```
Combine with `required` on the `<select>` to force a real choice.
</details>

---

## Requirements

- [ ] All 7 snippets fixed in separate files and verified in the browser
- [ ] A one-sentence cause written for each, in your own words (not copied from the answer)

## Acceptance criteria

- Every fixed form behaves correctly: labels focus fields, radio groups are exclusive, required/optional is right, tables have real headers, buttons submit, textarea/select show the right initial state.
