# 02 — Document Structure

## The Anatomy of an HTML Document

Every HTML page follows the same fundamental structure. Think of it like a letter: there's an envelope (the `<html>` element), a header with the address and subject (the `<head>`), and the actual letter content (the `<body>`).

---

## The Four Essential Parts

### 1. `<!DOCTYPE html>`

```html
<!DOCTYPE html>
```

This is a **declaration**, not a tag. It must be the very first line of every HTML file.

- Tells the browser: "This is an HTML5 document"
- Without it, browsers enter **quirks mode** — an old compatibility mode that renders pages inconsistently
- Always include it, always on line 1

### 2. `<html>`

```html
<html lang="en">
  ...
</html>
```

The **root element** — it wraps everything else on the page.

- `lang="en"` declares the language of the page
- This helps screen readers pronounce content correctly
- It helps search engines understand what language your content is in
- Use the correct language code: `"es"` for Spanish, `"fr"` for French, `"pt"` for Portuguese, etc.

### 3. `<head>`

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title</title>
</head>
```

The **metadata section** — contains information *about* the page, not content *for* the page.

Nothing in `<head>` is directly visible on the page (except the `<title>` which appears in the browser tab).

**What goes in `<head>`:**
- `<meta>` tags (charset, viewport, description, etc.)
- `<title>` — the page title shown in the browser tab
- `<link>` — links to CSS stylesheets, favicons
- `<script>` — JavaScript files (often placed at end of body instead)
- `<style>` — embedded CSS styles

### 4. `<body>`

```html
<body>
  <h1>Hello World</h1>
  <p>All visible content goes here.</p>
</body>
```

The **content section** — everything users see and interact with goes here.

- Headings, paragraphs, images, links, forms, tables — all go in `<body>`
- There is only one `<body>` per page

---

## Head vs Body: What Goes Where?

| Goes in `<head>` | Goes in `<body>` |
|-----------------|-----------------|
| `<title>` | `<h1>` to `<h6>` |
| `<meta charset>` | `<p>` |
| `<meta viewport>` | `<img>` |
| `<meta description>` | `<a>` |
| `<link rel="stylesheet">` | `<ul>`, `<ol>`, `<li>` |
| `<link rel="icon">` | `<table>` |
| `<script src="...">` | `<form>` |
| `<style>` | `<div>`, `<span>` |

---

## Why Structure Matters

1. **Browser rendering** — Browsers expect this structure. Deviating from it causes unpredictable rendering.

2. **SEO** — Search engines read the `<title>` and `<meta>` tags in `<head>` to understand and index your page.

3. **Accessibility** — Screen readers use the document structure to navigate content.

4. **Maintainability** — A consistent structure makes code easier to read and maintain.

5. **Validation** — Valid HTML is more likely to work correctly across all browsers.

---

## Indentation and Readability

HTML doesn't require indentation, but it makes code much easier to read:

```html
<!-- Hard to read — no indentation -->
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>My Page</title>
</head>
<body>
<h1>Hello</h1>
<p>World</p>
</body>
</html>

<!-- Easy to read — proper indentation -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My Page</title>
  </head>
  <body>
    <h1>Hello</h1>
    <p>World</p>
  </body>
</html>
```

Use **2 spaces** per indent level (standard in HTML/CSS/JS).

---

## Validating Your HTML

The W3C provides a free HTML validator:
👉 **https://validator.w3.org/**

You can paste your HTML or provide a URL. It will tell you about any errors or warnings. Valid HTML is more reliable and accessible.

---

## Complete Minimal HTML5 Document

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document Title</title>
  </head>
  <body>
    <h1>Page Heading</h1>
    <p>Page content goes here.</p>
  </body>
</html>
```

Memorize this structure. Every HTML file you ever write starts here.
