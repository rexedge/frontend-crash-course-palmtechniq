# Assignment 22 — Build the DOM From Data

**Type:** Challenge · **Difficulty:** ⭐⭐⭐ · **Time:** ~1 hr
**Prereqs:** Class 7 §12–13 (creating elements, objects, building the page from data)
**Build in:** `work/22-build-the-dom-from-data/index.html` + `style.css` + `app.js`

---

## Goal

Start with an array of objects, and let JavaScript build every card on the page from it. Then add buttons that re-draw the cards to show only some of them. This is exactly how the projects section of a portfolio can work.

## What you'll practice

- An array of objects as a small table of data
- A loop that turns each object into a card
- A function with a parameter that decides what gets shown
- Emptying a container and building it again

## Instructions

1. In `app.js`, write an array of **six** objects — six films you've seen. Each one has a `title`, a `year`, and a `rating`: your own score out of 10. For example:
   ```js
   const movies = [
       { title: "The first film", year: 2018, rating: 9 },
       { title: "The second film", year: 2001, rating: 7.5 }
   ];
   ```
   Make sure some are rated 8 or more, and some less.
2. In the HTML, all you need is two buttons and an empty container:
   ```html
   <button type="button" id="show-top">Only 8 and above</button>
   <button type="button" id="show-all">Show all</button>

   <section id="movie-cards" class="cards"></section>
   ```
3. Write `showMovies(minimumRating)`:
   - empty the container
   - loop over the array. For each film rated `minimumRating` or more, build an `<article class="card">` with the title in an `<h3>`, and the year and rating in a `<p>`
   - append each card to the container
4. Call `showMovies(0)` at the bottom of the file, so all six appear on load.
5. Connect the buttons: one calls `showMovies(8)`, and the other calls `showMovies(0)`.
6. Lay out `.cards` with Grid — `repeat(auto-fit, minmax(220px, 1fr))` from Class 5 — and style `.card`.

## Requirements

- [ ] The HTML file contains **no** cards — every one is built from the array
- [ ] All the text goes in through `textContent`
- [ ] `showMovies` empties the container before it builds anything
- [ ] One function does both jobs: "show all" and "show the best" differ only in the argument
- [ ] The card grid is responsive, with no media query

## Acceptance criteria

- Six cards appear when the page loads.
- `Only 8 and above` leaves only the films you rated 8 or more. Pressing it twice doesn't double the cards.
- `Show all` brings back all six.
- Add a seventh object to the array and save. A seventh card appears, and you didn't touch the HTML.
- The Elements panel shows real `<article>`, `<h3>`, and `<p>` elements inside the container.

## Hints

<details><summary>Show hint</summary>

The filter is just an `if` inside the loop: `if (movie.rating >= minimumRating) { ... build the card ... }`. Why does `showMovies(0)` show everything? Because every rating is at least 0.

If the cards pile up every time you press a button, the container isn't being emptied. `movieCards.innerHTML = "";` goes at the very start of the function.
</details>

## Stretch (optional)

*(This reaches ahead of Class 7.)* Add a `Sort by rating` button. Arrays have a `.sort()` method that takes a function saying how to compare two items. Look up "JavaScript sort array of objects", and re-draw the cards with the best-rated film first.
