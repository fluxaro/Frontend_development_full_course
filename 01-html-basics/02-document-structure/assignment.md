# Assignment — My Favorite Movie Page

## What You Are Building

Create a well-structured HTML page about your favorite movie, TV show, book, or game. The focus is correct document structure — every element in the right place.

No CSS. No JavaScript. Pure HTML structure only.

---

## Requirements

### Document Structure

Your HTML file must have:

- `<!DOCTYPE html>` as the first line
- `<html lang="en">` as the root element
- A `<head>` section with all of the following:
  - `<meta charset="UTF-8">`
  - `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
  - `<title>` — should include the movie or show name
  - `<meta name="description">` — a 1–2 sentence description of the page
- A `<body>` section with all visible content

### Semantic Structure

Your body must use semantic elements:
- `<header>` wrapping the main heading and any intro content
- `<main>` wrapping the main content
- `<footer>` at the bottom with your name

### Content

Your page must include:

1. The title as an `<h1>` inside `<header>`
2. At least 3 sections using `<h2>` headings, such as:
   - Overview or Synopsis
   - Why I Love It
   - Cast and Crew
   - My Rating
   - Fun Facts
3. At least 3 paragraphs of real content (not placeholder text)
4. At least one list (`<ul>` or `<ol>`) — for example a cast list or reasons to watch

---

## What Good Looks Like

- The page opens in a browser with no errors
- The heading hierarchy makes sense (h1 → h2, no skipping levels)
- All content is inside `<body>`
- The `<title>` and `<meta description>` are meaningful and specific
- The page passes W3C validation at `https://validator.w3.org/`

---

## Bonus Challenges

- Add a `<nav>` with anchor links to each section
- Add `<article>` wrapping the main review content
- Add `<time>` with a `datetime` attribute for the release year
- Add `<blockquote>` with a famous quote from the movie
- Add `<meta name="author">` with your name

---

## Submission

Save as `movie-page.html` and submit via GitHub or file upload.
