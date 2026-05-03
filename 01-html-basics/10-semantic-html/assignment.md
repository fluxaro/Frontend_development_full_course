# Assignment — News Website Homepage

## What You Are Building

Create an HTML page called `news-homepage.html` — a complete news website homepage using only semantic HTML elements. No `<div>` for layout purposes.

No CSS. No JavaScript. Pure semantic HTML only.

---

## Requirements

### Page Structure

Your page must use all of these semantic elements:
- `<header>` — site header with logo/name and navigation
- `<nav>` — navigation with `<ul>` and `<li>` structure
- `<main>` — wrapping all main content
- `<article>` — at least 5 news articles
- `<section>` — at least 2 sections grouping related articles
- `<aside>` — sidebar with trending topics or related links
- `<footer>` — site footer with links and copyright

### Content Requirements

**Header:**
- Site name as `<h1>`
- Navigation with at least 5 category links

**Featured Article Section:**
- One large featured article with `<article>` containing:
  - `<header>` with `<h2>` title and author/date
  - `<p>` excerpt (at least 3 sentences)
  - `<footer>` with tags or category

**Latest News Section:**
- `<h2>` heading
- At least 4 articles, each with title, author, date, and excerpt

**Aside:**
- `<h2>` heading
- A list of trending topics or popular articles

**Footer:**
- Footer navigation with `<nav>` and `<ul>`
- Copyright notice with `<small>` and `<time>`

### Semantic Requirements

- All dates must use `<time datetime="...">` with proper ISO format
- Author names must use `<address>` or `<strong>`
- Article categories must use `<mark>` or appropriate semantic element
- At least one `<figure>` with `<figcaption>` (for an image description)

---

## What Good Looks Like

- Zero `<div>` elements used for layout
- Heading hierarchy is correct throughout (h1 → h2 → h3, no skipping)
- All `<article>` elements have their own `<header>` and `<footer>`
- The page makes sense when read by a screen reader
- The page passes W3C validation

---

## Bonus Challenges

- Add a `<details>` and `<summary>` element for an expandable FAQ section
- Add `<address>` for the editorial contact information
- Add `aria-label` to the navigation elements to distinguish them
- Add a `<search>` element (HTML5.3) wrapping a search form

---

## Submission

Save as `news-homepage.html` and submit via GitHub.
