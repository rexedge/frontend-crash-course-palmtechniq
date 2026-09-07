# Assignment 05 — Image Sampler

**Type:** Warm-up · **Difficulty:** ⭐ · **Time:** ~15 min
**Prereqs:** Class 1 §4 (Images)
**Build in:** `work/05-image-sampler/index.html`

---

## Goal

Put five images on a page, each with a **written, specific** `alt` description and a caption paragraph.

## What you'll practice

- The self-closing `<img>` tag and its `src` and `alt` attributes
- Writing `alt` text that actually describes the image
- That `<img>` needs no closing tag

## Instructions

1. Build a valid skeleton with an `<h1>` like `Five Pictures`.
2. Add **five** `<img>` elements. For `src`, use a placeholder image URL such as `https://picsum.photos/300/200` (each reload gives a different photo) — or any real image URL you like.
3. Give each image an `alt` that **describes what the image shows**, specifically: `A misty pine forest at sunrise`, not `image1` or `photo`.
4. Under each image, add a `<p>` caption.
5. Save and view. Then **break one on purpose**: change one `src` to a nonsense URL, save, and see the `alt` text appear in place of the broken image.

## Requirements

- [ ] 5 `<img>` elements, each with both `src` and `alt`
- [ ] Every `alt` is a specific description, not a placeholder word
- [ ] A `<p>` caption under each image
- [ ] One image deliberately broken at the end, to see the `alt` fallback (then fix it)
- [ ] Valid skeleton

## Acceptance criteria

- Four images load; the deliberately-broken one shows its `alt` text instead.
- Reading only the `alt` values, someone who can't see the images knows roughly what each one is.

## Hints

<details><summary>Show hint</summary>

`<img>` is a **void** (self-closing) tag — there is no `</img>`. Format: `<img src="URL-here" alt="a real description here">`. Both attribute values need quotes.
</details>

## Stretch (optional)

Add a sixth `<img>` that is **decorative only** (a divider line, a pattern). For a purely decorative image the correct `alt` is empty: `alt=""`. Write a `<p>` explaining why empty is right here but wrong for the others.
