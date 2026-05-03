# 00 — Ways to Add CSS: Inline, Internal, External

## What Is This Lesson About?

CSS (Cascading Style Sheets) is the language that styles HTML. There are three ways to add CSS to an HTML page. Understanding each method — and when to use it — is the foundation of everything in CSS.

---

## Method 1: Inline CSS

CSS written directly on an HTML element using the `style` attribute.

```html
<h1 style="color: blue; font-size: 32px;">Hello World</h1>
<p style="color: gray; margin: 0;">This is a paragraph.</p>
```

**When to use:**
- Quick testing or debugging
- Dynamically applied styles via JavaScript
- Email HTML (email clients strip `<style>` tags)

**Pros:** Highest specificity, no external files needed  
**Cons:** Hard to maintain, cannot reuse styles, mixes content with presentation

---

## Method 2: Internal CSS (Embedded)

CSS written inside a `<style>` tag in the `<head>` section.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Page</title>
  <style>
    h1 {
      color: blue;
      font-size: 32px;
    }

    p {
      color: gray;
      line-height: 1.6;
    }
  </style>
</head>
<body>
  <h1>Hello World</h1>
  <p>This is a paragraph.</p>
</body>
</html>
```

**When to use:**
- Single-page websites
- Quick prototypes
- When you cannot use external files

**Pros:** Styles apply to the whole page, no extra HTTP request  
**Cons:** Cannot reuse across multiple pages, page file gets large

---

## Method 3: External CSS (Recommended)

CSS written in a separate `.css` file, linked from the HTML.

**HTML file:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Page</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Hello World</h1>
  <p>This is a paragraph.</p>
</body>
</html>
```

**style.css:**
```css
h1 {
  color: blue;
  font-size: 32px;
}

p {
  color: gray;
  line-height: 1.6;
}
```

**When to use:** Always — for any real project

**Pros:** Reusable across all pages, browser caches the file, clean separation of concerns  
**Cons:** Extra HTTP request (negligible with HTTP/2)

---

## Comparison Table

| Method | Location | Reusable? | Best For |
|---|---|---|---|
| Inline | `style=""` attribute | No | Quick fixes, JS-applied styles |
| Internal | `<style>` in `<head>` | Same page only | Single-page sites, prototypes |
| External | Separate `.css` file | All pages | Every real project |

---

## The Cascade

When multiple methods apply styles to the same element, the order of priority is:

1. Inline styles (highest priority)
2. Internal styles
3. External styles
4. Browser defaults (lowest priority)

This is part of the "Cascading" in CSS — styles cascade down from multiple sources.

---

## CSS Syntax

```css
selector {
  property: value;
  property: value;
}
```

```css
h1 {
  color: blue;
  font-size: 32px;
  font-weight: bold;
}
```

- **Selector** — which HTML element(s) to style
- **Property** — what to change (color, font-size, margin, etc.)
- **Value** — what to change it to
- **Declaration** — one property: value pair
- **Rule** — the complete selector + declarations block
