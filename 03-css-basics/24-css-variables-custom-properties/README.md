# 24 — CSS Variables (Custom Properties)

## What Is This Lesson About?

CSS custom properties (also called CSS variables) let you store values and reuse them throughout your stylesheet. They are the foundation of modern design systems and theming.

---

## Defining Custom Properties

```css
:root {
  --primary-color: #3498db;
  --font-size-base: 1rem;
  --spacing-md: 1rem;
  --border-radius: 8px;
}
```

The `:root` selector targets the `<html>` element — making these variables globally available.

---

## Using Custom Properties

```css
.button {
  background: var(--primary-color);
  font-size: var(--font-size-base);
  padding: var(--spacing-md);
  border-radius: var(--border-radius);
}
```

---

## Fallback Values

```css
color: var(--text-color, #333);
/* If --text-color is not defined, use #333 */
```

---

## Scoped Variables

Variables can be scoped to specific elements:

```css
:root { --color: blue; }

.card {
  --color: red;  /* overrides for this element and children */
  color: var(--color);  /* red */
}

.card .title {
  color: var(--color);  /* also red (inherited) */
}
```

---

## Theming with Custom Properties

```css
/* Light theme */
:root {
  --bg: #ffffff;
  --text: #1a1a2e;
  --border: #e0e0e0;
}

/* Dark theme */
[data-theme="dark"] {
  --bg: #0f172a;
  --text: #e2e8f0;
  --border: #334155;
}

/* Components use variables */
body { background: var(--bg); color: var(--text); }
.card { border: 1px solid var(--border); }
```

---

## JavaScript Integration

```javascript
// Read a CSS variable
const primary = getComputedStyle(document.documentElement)
  .getPropertyValue('--primary-color');

// Set a CSS variable
document.documentElement.style.setProperty('--primary-color', '#e74c3c');
```

---

## Design Token System

```css
:root {
  /* Colors */
  --color-primary-500: hsl(204 70% 53%);
  --color-success: hsl(145 63% 42%);

  /* Typography */
  --font-sans: 'Inter', system-ui, sans-serif;
  --text-base: 1rem;
  --text-lg: 1.125rem;

  /* Spacing */
  --space-4: 1rem;
  --space-8: 2rem;

  /* Layout */
  --max-width: 1200px;
  --nav-height: 64px;
  --border-radius: 8px;

  /* Shadows */
  --shadow-md: 0 4px 12px rgba(0,0,0,0.1);
}
```
