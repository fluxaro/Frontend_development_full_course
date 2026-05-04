# Class Work — Add Dark Mode to a Page

## What You Will Build

Add dark mode to an existing page using CSS custom properties and prefers-color-scheme.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `dark-mode-demo.html`:

```html
<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dark Mode Demo</title>
  <link rel="stylesheet" href="dark-mode.css">
</head>
<body>
  <header>
    <h1>Dark Mode Demo</h1>
    <button id="toggle" onclick="toggleTheme()">🌙 Dark Mode</button>
  </header>
  <main>
    <div class="card">
      <h2>Card Title</h2>
      <p>This card changes with the theme.</p>
      <button class="btn">Action</button>
    </div>
  </main>
  <script>
    function toggleTheme() {
      const html = document.documentElement;
      const btn = document.getElementById('toggle');
      if (html.getAttribute('data-theme') === 'light') {
        html.setAttribute('data-theme', 'dark');
        btn.textContent = '☀️ Light Mode';
      } else {
        html.setAttribute('data-theme', 'light');
        btn.textContent = '🌙 Dark Mode';
      }
    }
  </script>
</body>
</html>
```

---

## Step 2 — Create the CSS

Create `dark-mode.css`:

```css
/* Define tokens */
:root {
  --bg: #f8f9fa;
  --surface: white;
  --text: #1a1a2e;
  --text-muted: #666;
  --border: #e0e0e0;
  --primary: #3498db;
}

/* System dark mode */
@media (prefers-color-scheme: dark) {
  :root {
    --bg: #0f172a;
    --surface: #1e293b;
    --text: #e2e8f0;
    --text-muted: #94a3b8;
    --border: #334155;
  }
}

/* Manual dark mode */
[data-theme="dark"] {
  --bg: #0f172a;
  --surface: #1e293b;
  --text: #e2e8f0;
  --text-muted: #94a3b8;
  --border: #334155;
}

[data-theme="light"] {
  --bg: #f8f9fa;
  --surface: white;
  --text: #1a1a2e;
  --text-muted: #666;
  --border: #e0e0e0;
}

/* Apply tokens */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: system-ui, sans-serif;
  background: var(--bg);
  color: var(--text);
  padding: 40px;
  transition: background 0.3s, color 0.3s;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
}

.card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 1.5rem;
  max-width: 400px;
  transition: background 0.3s, border-color 0.3s;
}

.card h2 { margin-bottom: 0.5rem; }
.card p  { color: var(--text-muted); margin-bottom: 1rem; }

.btn {
  padding: 8px 20px;
  background: var(--primary); color: white;
  border: none; border-radius: 6px; cursor: pointer;
}

#toggle {
  padding: 8px 16px;
  background: transparent;
  border: 1px solid var(--border);
  border-radius: 6px;
  color: var(--text);
  cursor: pointer;
  transition: border-color 0.3s, color 0.3s;
}
```

---

## Checklist

- [ ] CSS custom properties defined in `:root`
- [ ] `@media (prefers-color-scheme: dark)` overrides tokens
- [ ] `[data-theme="dark"]` overrides tokens for manual toggle
- [ ] Smooth transition on background and color
- [ ] Toggle button works
- [ ] Page looks good in both modes
