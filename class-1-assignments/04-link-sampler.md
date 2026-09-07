# Assignment 04 — Link Sampler

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~10 min
**Prereqs:** Class 1 §4 (Links)
**Build in:** `work/04-link-sampler/index.html`

---

## Goal

Build a page of eight links to eight real websites, where every link's text describes where it goes.

## What you'll practice

- The `<a>` tag and its `href` **attribute**
- Writing **descriptive link text** (never "click here")
- Full URLs including `https://`

## Instructions

1. Build a valid skeleton.
2. Add an `<h1>` that says `Sites I Use` and one `<p>` of intro text.
3. Add **eight** `<a>` links to eight real websites you actually visit. Put each on its own line (each `<a>` can sit inside its own `<p>`).
4. The **text between `<a>` and `</a>`** must describe the destination — e.g. `The Wikipedia homepage`, `BBC News front page`, `My favourite recipe blog`. Never just `click here` or a bare URL.
5. Save, open in the browser, and click every link to confirm it goes where the text promises.

## Requirements

- [ ] `<h1>` + intro `<p>`
- [ ] 8 `<a>` elements, each with a valid `href` starting `https://`
- [ ] Every link's visible text describes the destination
- [ ] No "click here", no bare URLs as the link text
- [ ] Valid skeleton, all tags closed

## Acceptance criteria

- All 8 links open the correct site.
- If you read only the link text (ignoring everything else), you can still tell what each link is for.

## Hints

<details><summary>Show hint</summary>

`href` is an **attribute** — extra information inside the opening tag: `<a href="https://example.com">Example home page</a>`. The quotes around the URL are required. A missing `https://` makes the browser treat it as a link to a file on your own computer.
</details>

## Stretch (optional)

Add one link that opens in a new browser tab by adding `target="_blank"` to its opening tag. Note how it behaves differently from the others.
