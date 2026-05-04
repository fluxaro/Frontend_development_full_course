# Notes — CSS Custom Properties

## Quick Reference

```css
/* Define */
:root { --color: #3498db; }

/* Use */
color: var(--color);

/* With fallback */
color: var(--color, #333);

/* Override in scope */
.card { --color: red; }
```

## Theming Pattern

```css
:root { --bg: white; --text: black; }
[data-theme="dark"] { --bg: #0f172a; --text: white; }
body { background: var(--bg); color: var(--text); }
```

## JavaScript

```javascript
// Read
getComputedStyle(document.documentElement).getPropertyValue('--color');

// Write
document.documentElement.style.setProperty('--color', 'red');
```

## Common Mistakes

- Forgetting `--` prefix (required)
- Defining in wrong scope (use `:root` for global)
- Not providing fallback values
- Using for non-CSS values (cannot use in media queries)
