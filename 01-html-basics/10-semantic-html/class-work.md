# Class Work — Refactor Div Soup to Semantic HTML

## What You Will Do

You will take a page written with non-semantic `<div>` elements and refactor it to use proper semantic HTML. Then you will build a new blog post page from scratch using only semantic elements.

**Time:** 40 minutes

---

## Part 1: Refactor Div Soup (15 minutes)

Here is a page written with `<div>` elements everywhere. Your job is to replace every `<div>` with the correct semantic element.

**The original (bad) code:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Tech Blog</title>
</head>
<body>

  <div class="header">
    <div class="site-title">Tech Blog</div>
    <div class="navigation">
      <div class="nav-item"><a href="/">Home</a></div>
      <div class="nav-item"><a href="/articles">Articles</a></div>
      <div class="nav-item"><a href="/about">About</a></div>
    </div>
  </div>

  <div class="main-content">
    <div class="article">
      <div class="article-header">
        <div class="article-title">Why HTML Matters</div>
        <div class="article-meta">By Alex Johnson | January 15, 2025</div>
      </div>
      <div class="article-body">
        <div class="intro">
          <p>HTML is the foundation of the web...</p>
        </div>
        <div class="section">
          <div class="section-title">The Basics</div>
          <p>Every webpage starts with HTML...</p>
        </div>
      </div>
    </div>

    <div class="sidebar">
      <div class="sidebar-title">Related Articles</div>
      <div class="sidebar-item"><a href="#">CSS Basics</a></div>
      <div class="sidebar-item"><a href="#">JavaScript Intro</a></div>
    </div>
  </div>

  <div class="footer">
    <div class="copyright">Copyright 2025 Tech Blog</div>
  </div>

</body>
</html>
```

**Your task:** Rewrite this using semantic elements. Replace:
- `<div class="header">` → `<header>`
- `<div class="navigation">` → `<nav>` with `<ul>` and `<li>`
- `<div class="main-content">` → `<main>`
- `<div class="article">` → `<article>`
- `<div class="article-header">` → `<header>` (inside article)
- `<div class="article-title">` → `<h1>`
- `<div class="article-meta">` → `<p>` with `<time>`
- `<div class="section">` → `<section>`
- `<div class="section-title">` → `<h2>`
- `<div class="sidebar">` → `<aside>`
- `<div class="sidebar-title">` → `<h2>`
- `<div class="sidebar-item">` → `<li>` inside `<ul>`
- `<div class="footer">` → `<footer>`

---

## Part 2: Build a News Homepage (25 minutes)

Create a file called `news-homepage.html`. Build a news website homepage using ONLY semantic HTML elements. No `<div>` for layout purposes.

### Required Structure

```
<header>
  <h1>Site name</h1>
  <nav> with at least 5 links </nav>
</header>

<main>
  <section> (featured article)
    <article>
      <header>
        <h2>Article title</h2>
        <p>Author and date</p>
      </header>
      <p>Article excerpt...</p>
    </article>
  </section>

  <section> (latest news — at least 3 articles)
    <h2>Latest News</h2>
    <article>...</article>
    <article>...</article>
    <article>...</article>
  </section>

  <aside>
    <h2>Trending Topics</h2>
    <ul>...</ul>
  </aside>
</main>

<footer>
  <nav> (footer links) </nav>
  <p>Copyright</p>
</footer>
```

---

## Checklist

- [ ] No `<div>` used for layout purposes
- [ ] `<header>` used for site header
- [ ] `<nav>` used for navigation with `<ul>` and `<li>`
- [ ] `<main>` wraps the main content
- [ ] `<article>` used for each news article
- [ ] `<section>` used to group related articles
- [ ] `<aside>` used for sidebar content
- [ ] `<footer>` used for the footer
- [ ] `<time>` used for dates with `datetime` attribute
- [ ] Heading hierarchy is correct (h1 → h2 → h3)
