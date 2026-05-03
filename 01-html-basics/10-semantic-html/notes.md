# Notes — Semantic HTML

## Semantic Elements Quick Reference

### Page Structure
| Element | Use For |
|---|---|
| `<header>` | Site header or article header |
| `<nav>` | Navigation links |
| `<main>` | Main page content (one per page) |
| `<article>` | Self-contained content |
| `<section>` | Thematic content group |
| `<aside>` | Sidebar, related content |
| `<footer>` | Page or section footer |

### Content
| Element | Use For |
|---|---|
| `<figure>` | Image, diagram, code block |
| `<figcaption>` | Caption for figure |
| `<time>` | Dates and times |
| `<address>` | Contact information |
| `<mark>` | Highlighted text |
| `<details>` | Expandable content |
| `<summary>` | Heading for details |

## article vs section vs div

| Element | When to Use |
|---|---|
| `<article>` | Could stand alone (blog post, comment, product card) |
| `<section>` | Thematic group that needs a heading |
| `<div>` | No semantic meaning — styling/layout only |

## Heading Hierarchy Rule

```
h1 — Page title (one per page)
  h2 — Major section
    h3 — Subsection
      h4 — Sub-subsection
```

Never skip levels. Do not use h3 without an h2 above it.

## Common Mistakes

- Using `<div>` for everything (div soup)
- Using `<section>` without a heading
- Using `<article>` for non-self-contained content
- Having more than one `<main>` per page
- Using `<header>` and `<footer>` only at the page level (they can be inside `<article>` too)
- Skipping heading levels (h1 → h3, skipping h2)
- Using `<b>` and `<i>` instead of `<strong>` and `<em>`

## Why It Matters

1. **Accessibility** — Screen readers use landmarks to navigate
2. **SEO** — Search engines understand content structure
3. **Readability** — Code is self-documenting
4. **Browser defaults** — Semantic elements have useful built-in behaviors
