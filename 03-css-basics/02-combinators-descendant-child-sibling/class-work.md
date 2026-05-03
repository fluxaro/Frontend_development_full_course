# Class Work — Style a Navigation Menu with Combinators

## What You Will Build

A navigation menu and article page styled entirely using combinators — no extra classes needed.

**Time:** 35 minutes

---

## Step 1 — Create the HTML

Create `combinators-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Combinators Demo</title>
  <link rel="stylesheet" href="combinators.css">
</head>
<body>

  <header>
    <nav>
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/about">About</a>
          <ul>
            <li><a href="/about/team">Team</a></li>
            <li><a href="/about/history">History</a></li>
          </ul>
        </li>
        <li><a href="/blog">Blog</a></li>
        <li><a href="/contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <article>
      <h1>Understanding CSS Combinators</h1>
      <p>This is the lead paragraph — it should look different from the rest.</p>
      <p>This is a regular paragraph.</p>

      <h2>Descendant Combinator</h2>
      <p>The first paragraph after this heading.</p>
      <p>The second paragraph after this heading.</p>

      <blockquote>
        <p>A quote inside a blockquote.</p>
      </blockquote>
      <p>This paragraph comes after the blockquote.</p>
      <p>So does this one.</p>

      <h2>Child Combinator</h2>
      <ul>
        <li>Direct child item
          <ul>
            <li>Nested item (not a direct child)</li>
          </ul>
        </li>
        <li>Another direct child item</li>
      </ul>
    </article>
  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `combinators.css`:

```css
/* Reset */
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: sans-serif;
  color: #333;
  line-height: 1.6;
}

/* ---- DESCENDANT COMBINATOR ---- */
/* All links inside nav */
nav a {
  color: white;
  text-decoration: none;
  padding: 8px 16px;
  display: block;
}

/* All paragraphs inside article */
article p {
  margin-bottom: 1rem;
  color: #555;
}

/* ---- CHILD COMBINATOR ---- */
/* Only direct li children of the top-level nav ul */
nav > ul > li {
  display: inline-block;
  position: relative;
  background: #2c3e50;
}

/* Only direct li children of nested ul */
nav > ul > li > ul > li {
  display: block;
  background: #34495e;
}

/* Only direct p children of blockquote */
blockquote > p {
  font-style: italic;
  color: #666;
  border-left: 4px solid #3498db;
  padding-left: 16px;
}

/* ---- ADJACENT SIBLING COMBINATOR ---- */
/* The first p immediately after h1 (lead paragraph) */
h1 + p {
  font-size: 1.2rem;
  color: #2c3e50;
  font-weight: 500;
}

/* The first p immediately after h2 */
h2 + p {
  color: #2980b9;
}

/* ---- GENERAL SIBLING COMBINATOR ---- */
/* All p elements after a blockquote */
blockquote ~ p {
  font-style: italic;
  color: #888;
}

/* ---- LAYOUT ---- */
header {
  background: #2c3e50;
  padding: 0 20px;
}

main {
  max-width: 800px;
  margin: 40px auto;
  padding: 0 20px;
}

h1 { font-size: 2rem; margin-bottom: 1rem; }
h2 { font-size: 1.5rem; margin: 2rem 0 1rem; color: #2c3e50; }
```

---

## Checklist

- [ ] Descendant combinator used for nav links and article paragraphs
- [ ] Child combinator used for direct nav items
- [ ] Adjacent sibling used for lead paragraph after h1
- [ ] General sibling used for paragraphs after blockquote
- [ ] The nested nav items look different from top-level items
