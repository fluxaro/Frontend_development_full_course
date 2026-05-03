# Assignment — Style an Article Page Using Only Combinators

## What You Are Building

Style a complete article page using ONLY combinators — no class or ID selectors allowed (except for the page wrapper).

---

## Rules

- You may use ONE class: `.page-wrapper` on the body or main container
- All other styling must use combinators (descendant, child, adjacent sibling, general sibling)
- No inline styles
- No additional classes or IDs

---

## Requirements

### HTML Structure

Create `article-page.html` with:
- `<header>` with `<nav>` containing a `<ul>` with at least 5 links
- `<main>` with an `<article>` containing:
  - `<h1>` title
  - Lead paragraph (first `<p>` after `<h1>`)
  - At least 3 `<h2>` sections
  - Multiple paragraphs per section
  - At least one `<blockquote>`
  - At least one `<ul>` with nested `<ul>`
  - At least one `<ol>`
- `<aside>` with related links
- `<footer>`

### CSS Requirements

Create `article-page.css` using:

**Descendant combinators:**
- `nav a` — navigation links
- `article p` — article paragraphs
- `aside ul li` — sidebar list items

**Child combinators:**
- `nav > ul > li` — top-level nav items
- `article > h2` — direct h2 children of article
- `ul > li` vs nested `ul li` — different styles

**Adjacent sibling:**
- `h1 + p` — lead paragraph
- `h2 + p` — first paragraph after each section heading
- `blockquote + p` — paragraph immediately after blockquote

**General sibling:**
- `h2 ~ p` — all paragraphs in a section
- `blockquote ~ p` — all paragraphs after blockquote

---

## What Good Looks Like

- The lead paragraph (h1 + p) is visually distinct
- Navigation links are styled without classes
- Nested lists look different from top-level lists
- The page is readable and well-structured

---

## Submission

Submit `article-page.html` and `article-page.css`.
