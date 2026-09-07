# Assignment 16 — Recreate a Real Site's Typography

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~45 min
**Prereqs:** Class 3 §8 (typography); comfort with dev tools
**Build in:** `work/16-recreate-typography/index.html` + `style.css`

---

## Goal

Use dev tools to read a real site's text styling, then reproduce *just the reading experience* closely enough that it feels the same.

## What you'll practice

- Reading `font-family`, `font-size`, `line-height`, `color` off a live page with dev tools
- Matching a look by measurement, not by guessing
- Building your dev-tools habit

## Instructions

1. Pick a blog or news article page whose text you find pleasant to read.
2. With dev tools, inspect its **heading** and its **body paragraphs**. Note down:
   - `font-family` (the actual resolved font)
   - `font-size` and `line-height`
   - text `color`
   - max text width / measure (how wide the paragraph column is)
3. In your own `index.html`, write a heading + 4 real paragraphs of placeholder-ish prose.
4. In `style.css`, reproduce **only the typography and the column width** — same sizes, line height, colour, family (use a close system fallback if it's a licensed webfont), same reading width.
5. Put your notes (the measured values) in a comment at the top of `style.css`.

## Requirements

- [ ] Measured values recorded in a CSS comment
- [ ] Your page's heading + body match the source on `font-size`, `line-height`, `color`, and column width
- [ ] Font family matches or uses a defensible close fallback
- [ ] No attempt to copy the source's layout, colours-beyond-text, or images — typography only

## Acceptance criteria

- Put your page and the real one side by side: the *reading feel* (size, rhythm, line length) is clearly the same.
- You can name each value you set and where you read it from.

## Hints

<details><summary>Show hint</summary>

In dev tools, the **Computed** tab shows the final resolved values (e.g. `font-size: 18px`, `line-height: 28.8px`), which is more reliable than the authored rules in the Styles tab. Divide line-height by font-size to get the unitless ratio to reuse.
</details>
