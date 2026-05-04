# 34 — Dark Mode with prefers-color-scheme

## What Is This Lesson About?

Dark mode is now a standard feature users expect. CSS provides two ways to implement it: the `prefers-color-scheme` media query (automatic, follows system setting) and a manual toggle using CSS custom properties.

---

## prefers-color-scheme

Detects the user's system color scheme preference:

```css
/* Light mode (default) */
body { background: white; color: #333; }

/* Dark mode — automatically applied when system is dark */
@media (prefers-color-scheme: dark) {
  body { background: #0f172a; color: #e2e8f0; }
}
```

---

## CSS Custom Properties Approach (Recommended)

Define all colors as custom properties, then override them for dark mode:

```css
:root {
  --bg: white;
  --text: #333;
  --border: #e0e0e0;
}

@media (prefers-color-scheme: dark) {
  :root {
    --bg: #0f172a;
    --text: #e2e8f0;
    --border: #334155;
  }
}

body { background: var(--bg); color: var(--text); }
.card { border: 1px solid var(--border); }
```

---

## Manual Toggle

Add a `data-theme` attribute and override variables:

```css
[data-theme="dark"] {
  --bg: #0f172a;
  --text: #e2e8f0;
}

[data-theme="light"] {
  --bg: white;
  --text: #333;
}
```

```javascript
function toggleTheme() {
  const html = document.documentElement;
  const current = html.getAttribute('data-theme');
  html.setAttribute('data-theme', current === 'dark' ? 'light' : 'dark');
}
```

---

## Smooth Transition

```css
body {
  transition: background 0.3s, color 0.3s;
}
```
