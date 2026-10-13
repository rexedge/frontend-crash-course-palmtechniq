# Assignment 07 — Deploy It

**Type:** Stretch · **Difficulty:** ⭐⭐ · **Time:** ~45 min
**Prereqs:** a finished portfolio ([Assignment 01](01-personal-portfolio.md))
**Build in:** `work/01-personal-portfolio/` — nothing new to write; you're publishing what you have

---

## Goal

Put your portfolio on the web, so that it has a real address you can send to anybody.

> **This reaches outside the course.** Until now everything has run on your own computer. Deploying uses a hosting service, which means an account on somebody else's website, and screens that change from time to time. The steps below are a guide. If a button has moved, follow the service's own instructions, linked in each section.

## What you'll practice

- Checking that a site is self-contained before it leaves your computer
- Publishing a folder of plain files to a hosting service
- Testing the live site, not just the local one

## Instructions

### First: get the folder ready

Whichever service you use, the site has to work as a single folder.

1. The main page **must** be called `index.html`, and it must be at the top of the folder. That's the file a web server hands out when someone visits the address.
2. **Every path is relative.** `images/me.jpg` and `projects/gallery/index.html` work anywhere. A path that starts with `C:\`, or with a `/`, works only on your computer.
3. **Capitals must match exactly.** `images/Photo.JPG` and `images/photo.jpg` are the same file on Windows, and on most Macs. On a web server they are two different files, and the wrong one is a broken picture. Check every `src` and `href` against the real file name.
4. Everything the page needs is inside the folder: your images, and the `projects/` copies.
5. Remove your save-point copies and anything else you don't want made public.

### Then choose one

**Option A — GitHub Pages.** Free, and it gives you an address like `https://your-username.github.io/portfolio/`.

1. Create a free account at [github.com](https://github.com/), if you don't have one.
2. Create a **new repository**. Call it `portfolio`, and make it **public**.
3. Upload the **contents** of your portfolio folder to it, so that `index.html` sits at the top level of the repository. The repository's own "upload files" option does this in the browser.
4. Open the repository's **Settings**, then **Pages**. Choose a branch as the publishing source: your main branch, and its top-level folder.
5. Wait. Publishing can take up to ten minutes. The Pages settings screen then shows your site's address.

GitHub's own guide: [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

**Option B — Netlify Drop.** The quickest route: no account is needed to try it.

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop).
2. Drag your whole portfolio **folder** onto the page.
3. After a moment you're given a web address for the site. Create a free account if you want to keep the site and update it later.

Netlify's own guide: [Create deploys](https://docs.netlify.com/site-deploys/create-deploys/).

### Finally: test the live site

Open the address on your **phone**, not just on your computer, and go through the page as a visitor would.

## Requirements

- [ ] The site is live at a public address
- [ ] The main page is `index.html`, at the top level
- [ ] Every image loads on the live site
- [ ] Every project link works on the live site
- [ ] The theme toggle, the form's thank-you message, and your third interaction all work there
- [ ] You've opened it on a real phone

## Acceptance criteria

- Someone else, on a different device and a different network, can open your address and see your portfolio.
- No broken pictures, and no link that leads to a "not found" page.
- The Console on the live site is as clean as it was locally.

## Hints

<details><summary>Show hint</summary>

- **The address shows a "not found" page, or a list of files.** `index.html` isn't at the top level. You probably uploaded the folder itself, so the page is one level down, at `…/01-personal-portfolio/`.
- **It worked on my computer, but pictures are missing online.** Capital letters, nearly every time: the `src` says `gallery.png`, and the file is called `Gallery.PNG`.
- **The page has no styling online.** The stylesheet's path is wrong for the same reason, or it starts with a `/`.
- **I changed something, and the live site hasn't changed.** The live site is a copy. Upload the changed files again, wait a few minutes, and reload.
</details>

## Stretch (optional)

- Put the live address in your portfolio's footer, and in your social profiles.
- When you learn Git, in a later course, come back and publish by pushing changes instead of uploading files by hand.
