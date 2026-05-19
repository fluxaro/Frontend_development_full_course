# Assignment — Blog with Typography Plugin

## What You Are Building

A complete blog page that uses the `@tailwindcss/typography` plugin's `prose` class to style rich article content. This demonstrates how plugins extend Tailwind beyond its core utilities.

---

## Requirements

Create `blog-with-typography.html` with:

### Page Structure
- A sticky navbar with logo and navigation links
- A hero section with the blog title and metadata
- A main article using `prose` for all body content
- A sidebar with "Related Posts" and "Tags" widgets
- A footer

### Article Content (use `prose` class)
The article must contain:
- An `<h1>` title
- At least two `<h2>` subheadings
- Multiple `<p>` paragraphs
- An unordered `<ul>` list
- An ordered `<ol>` list
- A `<blockquote>`
- An inline `<code>` snippet
- A `<pre><code>` code block

### Prose Variants
- Use `prose-lg` for the article body
- Use `prose-invert` when a dark background is applied
- Use `max-w-none` to let prose fill its container

### Layout
- Two-column layout on desktop: article (2/3) + sidebar (1/3)
- Single column on mobile

---

## What Good Looks Like

- The article content looks like a professional blog post with no custom CSS
- Headings, paragraphs, lists, and code blocks all have beautiful default styling
- The layout is responsive
- The sidebar has real content (not placeholder text)

---

## Submission

Submit `blog-with-typography.html`.
