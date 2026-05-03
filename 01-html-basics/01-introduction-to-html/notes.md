# Notes — Introduction to HTML

## HTML Tag Syntax Cheat Sheet

### Paired Tags (Opening + Closing)
```html
<tagname>content</tagname>

<!-- Examples -->
<h1>Main Heading</h1>
<p>A paragraph of text.</p>
<a href="https://example.com">A link</a>
<div>A division/container</div>
<span>Inline container</span>
<strong>Bold text</strong>
<em>Italic text</em>
```

### Self-Closing Tags (No closing tag needed)
```html
<tagname attribute="value">
<!-- or in XHTML style: <tagname /> -->

<!-- Examples -->
<img src="image.jpg" alt="Description">
<br>          <!-- line break -->
<hr>          <!-- horizontal rule -->
<input type="text">
<meta charset="UTF-8">
<link rel="stylesheet" href="style.css">
```

---

## Attributes Syntax

```html
<tagname attribute="value">

<!-- Single attribute -->
<img src="photo.jpg">

<!-- Multiple attributes -->
<a href="https://google.com" target="_blank" title="Go to Google">Google</a>

<!-- Boolean attributes (no value needed) -->
<input type="checkbox" checked>
<input type="text" disabled>
<video autoplay muted loop>
```

**Rules for attributes:**
- Always go in the **opening tag**, never the closing tag
- Values should be wrapped in **double quotes** `""`
- Attribute names are **lowercase** (best practice)
- Order of attributes doesn't matter

---

## The 5 Essential Tags to Memorize

| Tag | Purpose | Example |
|-----|---------|---------|
| `<h1>` to `<h6>` | Headings (h1 = most important) | `<h1>Title</h1>` |
| `<p>` | Paragraph | `<p>Some text.</p>` |
| `<a>` | Hyperlink | `<a href="url">text</a>` |
| `<img>` | Image | `<img src="img.jpg" alt="desc">` |
| `<div>` | Generic container | `<div>content</div>` |

---

## Document Skeleton

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
  </head>
  <body>
    <!-- Visible content goes here -->
  </body>
</html>
```

---

## Common Beginner Mistakes

### ❌ Forgetting to close tags
```html
<!-- Wrong -->
<p>This paragraph never ends...
<p>This is a new paragraph

<!-- Correct -->
<p>This paragraph ends properly.</p>
<p>This is a new paragraph.</p>
```

### ❌ Wrong nesting order
```html
<!-- Wrong — tags must close in reverse order -->
<strong><em>text</strong></em>

<!-- Correct -->
<strong><em>text</em></strong>
```

### ❌ Missing quotes on attribute values
```html
<!-- Wrong -->
<a href=https://google.com>Google</a>

<!-- Correct -->
<a href="https://google.com">Google</a>
```

### ❌ Using spaces in attribute values without quotes
```html
<!-- Wrong -->
<img alt=my photo>

<!-- Correct -->
<img alt="my photo">
```

### ❌ Putting content outside the body
```html
<!-- Wrong -->
<html>
  <head>...</head>
  <body>...</body>
  <p>This paragraph is outside body!</p>  <!-- ❌ -->
</html>

<!-- Correct — all visible content inside body -->
<html>
  <head>...</head>
  <body>
    <p>This paragraph is inside body.</p>  <!-- ✅ -->
  </body>
</html>
```

### ❌ Multiple `<h1>` tags
```html
<!-- Avoid — only one h1 per page -->
<h1>Main Title</h1>
<h1>Another Main Title</h1>  <!-- ❌ -->

<!-- Correct — use h2 for subheadings -->
<h1>Main Title</h1>
<h2>Subheading</h2>  <!-- ✅ -->
```

### ❌ Skipping heading levels
```html
<!-- Wrong — don't skip from h1 to h4 -->
<h1>Title</h1>
<h4>Subsection</h4>  <!-- ❌ skipped h2 and h3 -->

<!-- Correct — go in order -->
<h1>Title</h1>
<h2>Section</h2>
<h3>Subsection</h3>
```

---

## HTML Comments

Comments are notes in your code that the browser ignores:

```html
<!-- This is a comment — the browser won't display this -->

<!-- 
  Multi-line comment
  Useful for explaining complex sections
  or temporarily hiding code
-->
```

---

## Whitespace in HTML

HTML collapses multiple spaces and line breaks into a single space:

```html
<p>This    has    lots    of    spaces.</p>
<!-- Displays as: "This has lots of spaces." -->

<p>Line 1
Line 2
Line 3</p>
<!-- Displays as: "Line 1 Line 2 Line 3" -->
```

To force a line break, use `<br>`:
```html
<p>Line 1<br>Line 2<br>Line 3</p>
```

---

## Quick Reference: Heading Hierarchy

```
h1 — Page title (one per page)
  h2 — Major section
    h3 — Subsection
      h4 — Sub-subsection
        h5 — Rarely used
          h6 — Rarely used
```

Think of it like a book outline:
- h1 = Book title
- h2 = Chapter
- h3 = Section within chapter
- h4 = Subsection

---

## Useful VS Code Shortcuts

| Shortcut | Action |
|----------|--------|
| `!` then Tab | Generate HTML boilerplate |
| `Ctrl+S` / `Cmd+S` | Save file |
| `Alt+Z` | Toggle word wrap |
| `Ctrl+/` | Toggle comment |
| `Tab` | Indent selected code |
| `Shift+Tab` | Unindent selected code |
