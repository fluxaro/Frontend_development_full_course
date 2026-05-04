# Class Work — Cascade Layers Demo

## What You Will Build

A page demonstrating how cascade layers control style priority.

**Time:** 25 minutes

---

## Step 1 — Create the HTML

Create `cascade-layers.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cascade Layers Demo</title>
  <link rel="stylesheet" href="cascade-layers.css">
</head>
<body>
  <main>
    <h1>Cascade Layers</h1>
    <p>Layers control which styles win without fighting specificity.</p>

    <div class="card">
      <h2>Card Component</h2>
      <p>This card is styled by multiple layers.</p>
      <button class="btn">Click Me</button>
    </div>

    <div class="card featured">
      <h2>Featured Card</h2>
      <p>This card has an extra class that overrides the base layer.</p>
      <button class="btn">Click Me</button>
    </div>
  </main>
</body>
</html>
```

---

## Step 2 — Create the CSS

Create `cascade-layers.css`:

```css
/* Define layer order — FIRST layer wins if equal specificity */
@layer reset, base, components, utilities;

/* Reset layer */
@layer reset {
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: sans-serif; }
}

/* Base layer */
@layer base {
  body { padding: 40px; background: #f8f9fa; color: #333; }
  h1 { margin-bottom: 40px; }
  h2 { margin-bottom: 12px; }
  p  { color: #666; margin-bottom: 1rem; }
}

/* Components layer */
@layer components {
  .card {
    background: white;
    border: 1px solid #e0e0e0;
    border-radius: 8px;
    padding: 1.5rem;
    margin-bottom: 1rem;
    max-width: 400px;
  }

  .btn {
    padding: 10px 20px;
    background: #3498db;
    color: white;
    border: none;
    border-radius: 6px;
    cursor: pointer;
  }
}

/* Utilities layer — highest priority */
@layer utilities {
  .featured {
    border-color: #3498db;
    border-width: 2px;
    background: #ebf5fb;
  }
}
```

---

## Checklist

- [ ] Layer order defined at the top
- [ ] Reset layer applied
- [ ] Base layer applied
- [ ] Components layer applied
- [ ] Utilities layer overrides components
