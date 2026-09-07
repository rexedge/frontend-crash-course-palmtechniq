# Assignment 13 — Match the Mockup

**Type:** Core · **Difficulty:** ⭐⭐ · **Time:** ~35 min
**Prereqs:** Class 3 §6–8
**Build in:** `work/13-match-the-mockup/index.html` + `style.css`

---

## Goal

Reproduce a given visual spec exactly — hit every number.

## What you'll practice

- Translating a spec sheet into precise CSS
- Killing default margins (`margin-top: 0`) to control spacing
- A first taste of `a:hover` (a *pseudo-class* — small addition to the lesson)

## The spec

```
Page background:      #f4f4f4
Content column:       width 640px, centred, background #ffffff,
                      padding 32px, border 1px solid #e0e0e0
H1:                   font-size 2rem, margin-bottom 8px, color #1a1a1a
Subtitle p:           color #666, margin-top 0, margin-bottom 24px
Body p:               font-size 1rem, line-height 1.7, color #333
Links:                color #0066cc, no underline until hovered
```

## Instructions

1. Write `index.html` with sensible content: an `<h1>`, one subtitle `<p>` right under it, then 3–4 body `<p>` with a couple of `<a>` links in the text. Wrap the lot in one container element for the "content column".
2. Write `style.css` to hit **every value** in the spec.
3. For "no underline until hovered":
   ```css
   a { color: #0066cc; text-decoration: none; }
   a:hover { text-decoration: underline; }
   ```

## Requirements

- [ ] Every number and colour in the spec matched exactly
- [ ] The content column is centred (`margin: 0 auto` + the set `width`)
- [ ] The subtitle `<p>` has `margin-top: 0` so it sits tight under the `<h1>`
- [ ] Links are unstyled-underline by default, underlined on hover

## Acceptance criteria

- Inspect each element in dev tools → Computed: the values read back exactly as specced.
- No horizontal scrollbar; the white column sits centred on the grey page.
- Hovering a link adds the underline; moving away removes it.

## Hints

<details><summary>Show hint</summary>

Browsers put default `margin` on `<h1>` and `<p>`. When the spec gives an exact `margin-bottom` and a `margin-top: 0`, you must set both — otherwise the default top margin of the next element (or margin collapse) throws your spacing off.
</details>
