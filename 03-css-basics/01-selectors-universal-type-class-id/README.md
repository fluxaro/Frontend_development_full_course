# 01 — CSS Selectors: Universal, Type, Class, and ID

## What Is This Lesson About?

Selectors are how you tell CSS which HTML elements to style. This lesson covers the four fundamental selector types that form the basis of all CSS styling.

---

## The Four Basic Selectors

### 1. Universal Selector `*`

Selects every element on the page.

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

**Use for:** CSS resets, applying a property to everything.

---

### 2. Type Selector (Element Selector)

Selects all elements of a specific HTML tag.

```css
h1 {
  font-size: 2.5rem;
  color: #1a1a2e;
}

p {
  line-height: 1.6;
  color: #555;
}

a {
  color: #3498db;
  text-decoration: none;
}
```

**Use for:** Setting default styles for HTML elements.

---

### 3. Class Selector `.classname`

Selects all elements with a specific `class` attribute. Classes can be reused on multiple elements.

```html
<p class="highlight">This is highlighted.</p>
<span class="highlight">This is also highlighted.</span>
<div class="card">A card component.</div>
```

```css
.highlight {
  background-color: yellow;
  font-weight: bold;
}

.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
}
```

**Use for:** Reusable styles, components, utility classes.

---

### 4. ID Selector `#id`

Selects the single element with a specific `id` attribute. IDs must be unique on a page.

```html
<header id="site-header">...</header>
<main id="main-content">...</main>
```

```css
#site-header {
  background-color: #2c3e50;
  color: white;
  padding: 20px;
}

#main-content {
  max-width: 1200px;
  margin: 0 auto;
}
```

**Use for:** Unique page sections, JavaScript targets, anchor links.

---

## Multiple Classes

An element can have multiple classes:

```html
<button class="btn btn-primary btn-large">Click Me</button>
```

```css
.btn {
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}

.btn-primary {
  background-color: #3498db;
  color: white;
}

.btn-large {
  font-size: 1.2rem;
  padding: 15px 30px;
}
```

---

## Grouping Selectors

Apply the same styles to multiple selectors:

```css
h1, h2, h3, h4, h5, h6 {
  font-family: 'Georgia', serif;
  color: #1a1a2e;
}

.card, .panel, .box {
  border-radius: 8px;
  padding: 20px;
}
```

---

## Specificity

When multiple rules target the same element, specificity determines which wins:

| Selector | Specificity |
|---|---|
| `*` | 0 |
| `p` (type) | 1 |
| `.class` | 10 |
| `#id` | 100 |
| `style=""` (inline) | 1000 |

Higher specificity wins. If equal, the last rule wins.

---

## Class vs ID — When to Use Which

| | Class | ID |
|---|---|---|
| Reusable? | Yes | No (unique per page) |
| Multiple per element? | Yes | No |
| CSS specificity | 10 | 100 |
| JavaScript | `getElementsByClassName` | `getElementById` |
| Anchor links | No | Yes (`href="#id"`) |
| **Use for** | Styling components | Unique sections, JS targets |
