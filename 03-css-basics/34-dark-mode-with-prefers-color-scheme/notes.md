# Notes — Dark Mode

## Quick Reference

```css
/* System preference */
@media (prefers-color-scheme: dark) {
  :root { --bg: #0f172a; --text: #e2e8f0; }
}

/* Manual toggle */
[data-theme="dark"]  { --bg: #0f172a; --text: #e2e8f0; }
[data-theme="light"] { --bg: white;   --text: #333; }
```

## Color Palette Pattern

```css
:root {
  --bg-page:    white;
  --bg-surface: white;
  --text:       #1a1a2e;
  --text-muted: #666;
  --border:     #e0e0e0;
}

@media (prefers-color-scheme: dark) {
  :root {
    --bg-page:    #0f172a;
    --bg-surface: #1e293b;
    --text:       #e2e8f0;
    --text-muted: #94a3b8;
    --border:     #334155;
  }
}
```

## JavaScript Toggle

```javascript
function toggleTheme() {
  const html = document.documentElement;
  const isDark = html.getAttribute('data-theme') === 'dark';
  html.setAttribute('data-theme', isDark ? 'light' : 'dark');
  localStorage.setItem('theme', isDark ? 'light' : 'dark');
}

// Restore on load
const saved = localStorage.getItem('theme');
if (saved) document.documentElement.setAttribute('data-theme', saved);
```

## Common Mistakes

- Using hardcoded colors instead of CSS variables
- Forgetting to add smooth transitions
- Not saving the user's preference to localStorage
- Not checking system preference on initial load
