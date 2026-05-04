# Class Work — Build a Themeable Component

## What You Will Build

A UI component that can switch between light and dark themes using only CSS custom properties.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `css-variables.html`:

```html
<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Variables Demo</title>
  <link rel="stylesheet" href="css-variables.css">
</head>
<body>

  <header>
    <span class="logo">MyApp</span>
    <button id="theme-toggle" onclick="toggleTheme()">🌙 Dark Mode</button>
  </header>

  <main>
    <h1>CSS Custom Properties</h1>
    <p>Click the button to switch themes. Only the custom property values change.</p>

    <div class="card-grid">
      <div class="card">
        <h2>Card Title</h2>
        <p>This card uses CSS custom properties for all colors and spacing.</p>
        <button class="btn btn-primary">Primary</button>
      </div>
      <div class="card">
        <h2>Another Card</h2>
        <p>Change the theme and all cards update instantly.</p>
        <button class="btn btn-secondary">Secondary</button>
      </div>
    </div>

    <section class="color-demo">
      <h2>Color Tokens</h2>
      <div class="swatches">
        <div class="swatch primary">--color-primary</div>
        <div class="swatch secondary">--color-secondary</div>
        <div class="swatch success">--color-success</div>
        <div class="swatch warning">--color-warning</div>
        <div class="swatch danger">--color-danger</div>
      </div>
    </section>
  </main>

  <script>
    function toggleTheme() {
      const html = document.documentElement;
      const btn = document.getElementById('theme-toggle');
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

Create `css-variables.css`:

```css
/* === DESIGN TOKENS === */
:root {
  /* Colors */
  --color-primary:   #3498db;
  --color-secondary: #9b59b6;
  --color-success:   #27ae60;
  --color-warning:   #f39c12;
  --color-danger:    #e74c3c;

  /* Spacing */
  --space-1: 0.25rem;
  --space-2: 0.5rem;
  --space-4: 1rem;
  --space-6: 1.5rem;
  --space-8: 2rem;

  /* Border radius */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 16px;

  /* Shadows */
  --shadow-sm: 0 1px 3px rgba(0,0,0,0.1);
  --shadow-md: 0 4px 12px rgba(0,0,0,0.1);
}

/* === LIGHT THEME === */
[data-theme="light"] {
  --bg-page:       #f8f9fa;
  --bg-surface:    #ffffff;
  --bg-header:     #2c3e50;
  --text-primary:  #1a1a2e;
  --text-secondary:#666666;
  --border-color:  #e0e0e0;
}

/* === DARK THEME === */
[data-theme="dark"] {
  --bg-page:       #0f172a;
  --bg-surface:    #1e293b;
  --bg-header:     #0f172a;
  --text-primary:  #e2e8f0;
  --text-secondary:#94a3b8;
  --border-color:  #334155;
}

/* === COMPONENTS (use only variables) === */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: sans-serif;
  background: var(--bg-page);
  color: var(--text-primary);
  transition: background 0.3s, color 0.3s;
}

header {
  background: var(--bg-header);
  padding: 0 var(--space-8);
  height: 64px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo { color: white; font-weight: bold; font-size: 1.2rem; }

#theme-toggle {
  padding: var(--space-2) var(--space-4);
  background: transparent;
  color: white;
  border: 1px solid rgba(255,255,255,0.3);
  border-radius: var(--radius-sm);
  cursor: pointer;
}

main {
  max-width: 900px;
  margin: 0 auto;
  padding: var(--space-8) var(--space-4);
}

h1 { margin-bottom: var(--space-2); }
p  { color: var(--text-secondary); margin-bottom: var(--space-4); }

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: var(--space-6);
  margin-bottom: var(--space-8);
}

.card {
  background: var(--bg-surface);
  border: 1px solid var(--border-color);
  border-radius: var(--radius-md);
  padding: var(--space-6);
  box-shadow: var(--shadow-sm);
  transition: background 0.3s, border-color 0.3s;
}

.card h2 { margin-bottom: var(--space-2); }
.card p  { margin-bottom: var(--space-4); }

.btn {
  padding: var(--space-2) var(--space-4);
  border: none;
  border-radius: var(--radius-sm);
  cursor: pointer;
  font-weight: 600;
}

.btn-primary   { background: var(--color-primary);   color: white; }
.btn-secondary { background: var(--color-secondary); color: white; }

/* Color swatches */
.color-demo { margin-top: var(--space-8); }
.color-demo h2 { margin-bottom: var(--space-4); }

.swatches { display: flex; gap: var(--space-4); flex-wrap: wrap; }

.swatch {
  padding: var(--space-4) var(--space-6);
  border-radius: var(--radius-md);
  color: white;
  font-size: 0.8rem;
  font-weight: bold;
}

.primary   { background: var(--color-primary); }
.secondary { background: var(--color-secondary); }
.success   { background: var(--color-success); }
.warning   { background: var(--color-warning); }
.danger    { background: var(--color-danger); }
```

---

## Checklist

- [ ] Design tokens defined in `:root`
- [ ] Light theme defined on `[data-theme="light"]`
- [ ] Dark theme defined on `[data-theme="dark"]`
- [ ] All component styles use `var()` only
- [ ] Theme toggle button works
- [ ] Smooth transition between themes
