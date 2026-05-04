# Class Work — Build a Design Token System

## What You Will Build

A complete design token system using CSS custom properties, then apply it to a sample UI.

**Time:** 35 minutes

---

## Step 1 — Define Your Design Tokens

Create `design-system.css`:

```css
:root {
  /* === COLORS === */
  --color-primary-100: hsl(204 70% 95%);
  --color-primary-500: hsl(204 70% 53%);
  --color-primary-700: hsl(204 70% 33%);

  --color-success: hsl(145 63% 42%);
  --color-warning: hsl(38 92% 50%);
  --color-danger:  hsl(354 70% 54%);

  --color-gray-50:  hsl(0 0% 98%);
  --color-gray-100: hsl(0 0% 96%);
  --color-gray-200: hsl(0 0% 90%);
  --color-gray-500: hsl(0 0% 45%);
  --color-gray-900: hsl(0 0% 10%);

  /* === TYPOGRAPHY === */
  --font-sans: 'Segoe UI', system-ui, sans-serif;
  --font-mono: 'Courier New', monospace;

  --text-xs:   0.75rem;
  --text-sm:   0.875rem;
  --text-base: 1rem;
  --text-lg:   1.125rem;
  --text-xl:   1.25rem;
  --text-2xl:  1.5rem;
  --text-3xl:  1.875rem;
  --text-4xl:  2.25rem;

  /* === SPACING === */
  --space-1:  0.25rem;
  --space-2:  0.5rem;
  --space-3:  0.75rem;
  --space-4:  1rem;
  --space-6:  1.5rem;
  --space-8:  2rem;
  --space-12: 3rem;
  --space-16: 4rem;

  /* === LAYOUT === */
  --nav-height:    64px;
  --sidebar-width: 280px;
  --max-width:     1200px;
  --border-radius: 8px;
  --border-radius-lg: 16px;

  /* === SHADOWS === */
  --shadow-sm: 0 1px 3px rgba(0,0,0,0.1);
  --shadow-md: 0 4px 12px rgba(0,0,0,0.1);
  --shadow-lg: 0 8px 24px rgba(0,0,0,0.15);
}
```

---

## Step 2 — Apply Tokens to a UI

Create `design-system-demo.html` and apply your tokens:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Design System Demo</title>
  <link rel="stylesheet" href="design-system.css">
  <link rel="stylesheet" href="components.css">
</head>
<body>
  <nav class="navbar">
    <div class="container">
      <span class="logo">MyApp</span>
      <div class="nav-links">
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
      </div>
    </div>
  </nav>

  <main class="container">
    <h1>Design System Demo</h1>

    <section class="card-grid">
      <div class="card">
        <h2>Card Title</h2>
        <p>Card content using design tokens.</p>
        <button class="btn btn-primary">Primary</button>
      </div>
      <div class="card">
        <h2>Another Card</h2>
        <p>All spacing and colors from tokens.</p>
        <button class="btn btn-success">Success</button>
      </div>
    </section>
  </main>
</body>
</html>
```

Create `components.css` using ONLY your design tokens:

```css
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: var(--font-sans);
  font-size: var(--text-base);
  color: var(--color-gray-900);
  background: var(--color-gray-50);
}

.navbar {
  height: var(--nav-height);
  background: var(--color-primary-500);
  display: flex;
  align-items: center;
  box-shadow: var(--shadow-sm);
}

.container {
  width: min(var(--max-width), 100% - var(--space-8));
  margin-inline: auto;
}

.logo {
  color: white;
  font-size: var(--text-xl);
  font-weight: bold;
}

.nav-links a {
  color: white;
  text-decoration: none;
  margin-left: var(--space-6);
  font-size: var(--text-sm);
}

main.container {
  padding: var(--space-8) 0;
}

h1 {
  font-size: var(--text-4xl);
  margin-bottom: var(--space-8);
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: var(--space-6);
}

.card {
  background: white;
  padding: var(--space-6);
  border-radius: var(--border-radius);
  box-shadow: var(--shadow-md);
}

.card h2 {
  font-size: var(--text-xl);
  margin-bottom: var(--space-3);
}

.card p {
  color: var(--color-gray-500);
  margin-bottom: var(--space-4);
}

.btn {
  padding: var(--space-2) var(--space-4);
  border: none;
  border-radius: var(--border-radius);
  font-size: var(--text-sm);
  cursor: pointer;
  font-weight: 600;
}

.btn-primary { background: var(--color-primary-500); color: white; }
.btn-success { background: var(--color-success); color: white; }
```

---

## Checklist

- [ ] All colors defined as custom properties
- [ ] All spacing defined as custom properties
- [ ] All typography defined as custom properties
- [ ] `calc()` used at least once
- [ ] `min()` used for container width
- [ ] `var()` used throughout components
- [ ] No hardcoded values in components — only tokens
