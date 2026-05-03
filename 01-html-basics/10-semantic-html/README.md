# 10 — Semantic HTML

## What Is This Lesson About?

Semantic HTML means using HTML elements for their intended purpose — choosing elements based on what the content *means*, not how it looks. A `<nav>` is for navigation. An `<article>` is for a self-contained piece of content. A `<button>` is for actions.

---

## Why Semantic HTML Matters

**1. Accessibility:** Screen readers use semantic elements to help visually impaired users navigate. A screen reader can jump directly to the `<main>` content, skip the `<nav>`, or list all `<article>` elements on the page.

**2. SEO:** Search engines understand semantic HTML better. A `<h1>` inside an `<article>` carries more weight than a `<div>` with a class.

**3. Maintainability:** Code is easier to read and maintain when elements describe their purpose.

**4. Browser defaults:** Semantic elements come with useful default behaviors (e.g., `<button>` is keyboard-focusable by default).

---

## Semantic vs Non-Semantic

```html
<!-- Non-semantic (div soup) -->
<div class="header">
  <div class="nav">
    <div class="nav-item"><a href="/">Home</a></div>
  </div>
</div>
<div class="main">
  <div class="article">
    <div class="title">My Blog Post</div>
    <div class="content">...</div>
  </div>
</div>
<div class="footer">...</div>

<!-- Semantic (correct) -->
<header>
  <nav>
    <ul>
      <li><a href="/">Home</a></li>
    </ul>
  </nav>
</header>
<main>
  <article>
    <h1>My Blog Post</h1>
    <p>...</p>
  </article>
</main>
<footer>...</footer>
```

---

## The Semantic Elements

### Page Structure

| Element | Purpose |
|---|---|
| `<header>` | Introductory content — site header or article header |
| `<nav>` | Navigation links |
| `<main>` | The main content of the page (only one per page) |
| `<article>` | Self-contained content that makes sense on its own |
| `<section>` | A thematic grouping of content |
| `<aside>` | Content tangentially related to the main content (sidebar) |
| `<footer>` | Footer for the page or a section |

### Content Elements

| Element | Purpose |
|---|---|
| `<figure>` | Self-contained content like images, diagrams, code |
| `<figcaption>` | Caption for a `<figure>` |
| `<time>` | A date or time |
| `<address>` | Contact information |
| `<mark>` | Highlighted/relevant text |
| `<details>` | Expandable/collapsible content |
| `<summary>` | The visible heading for `<details>` |

---

## article vs section vs div

| Element | Use When |
|---|---|
| `<article>` | Content that could stand alone (blog post, news article, comment, product card) |
| `<section>` | A thematic group of content that needs a heading |
| `<div>` | No semantic meaning — use only for styling/layout purposes |

**Rule of thumb:** If you can give it a heading, use `<section>`. If it could be syndicated or shared independently, use `<article>`. If it is just a styling wrapper, use `<div>`.

---

## A Complete Semantic Page Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Blog</title>
</head>
<body>

  <header>
    <h1>My Blog</h1>
    <nav>
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/about">About</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <article>
      <header>
        <h2>Article Title</h2>
        <p>By <strong>Author</strong> on <time datetime="2025-01-15">January 15, 2025</time></p>
      </header>

      <section>
        <h3>Introduction</h3>
        <p>...</p>
      </section>

      <section>
        <h3>Main Content</h3>
        <p>...</p>
      </section>

      <footer>
        <p>Tags: HTML, Web Development</p>
      </footer>
    </article>

    <aside>
      <h2>Related Articles</h2>
      <ul>
        <li><a href="#">Article 1</a></li>
      </ul>
    </aside>
  </main>

  <footer>
    <p>Copyright 2025 My Blog</p>
  </footer>

</body>
</html>
```
