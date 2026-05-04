# Class Work — Optimize a Page for CSS Performance

## What You Will Do

Apply CSS performance optimizations to a page with many cards and animations.

**Time:** 25 minutes

---

## Step 1 — Create the HTML

Create `performance-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Performance Demo</title>
  <link rel="stylesheet" href="performance.css">
</head>
<body>
  <h1>CSS Performance Optimizations</h1>

  <section>
    <h2>Cards with will-change</h2>
    <div class="card-grid">
      <div class="card">Card 1</div>
      <div class="card">Card 2</div>
      <div class="card">Card 3</div>
      <div class="card">Card 4</div>
      <div class="card">Card 5</div>
      <div class="card">Card 6</div>
    </div>
  </section>

  <section>
    <h2>Long List with content-visibility</h2>
    <div class="long-list">
      <!-- 50 items -->
    </div>
  </section>
</body>
</html>
```

---

## Step 2 — Create the CSS

Create `performance.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 20px; color: #2c3e50; }
section { margin-bottom: 50px; }

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1rem;
}

.card {
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 2rem;
  text-align: center;
  font-weight: bold;

  /* contain: isolate layout and paint */
  contain: content;

  /* Transition using only compositor properties */
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

/* will-change: only on hover (not always) */
.card:hover {
  will-change: transform;
  transform: translateY(-4px);
  box-shadow: 0 8px 24px rgba(0,0,0,0.12);
}

/* Remove will-change after animation */
.card:not(:hover) {
  will-change: auto;
}

/* content-visibility for long lists */
.long-list-item {
  content-visibility: auto;
  contain-intrinsic-size: 0 80px;
  padding: 1rem;
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 6px;
  margin-bottom: 8px;
}
```

---

## Checklist

- [ ] `contain: content` on card components
- [ ] `will-change: transform` only on hover
- [ ] `will-change: auto` when not hovering
- [ ] Animations use only `transform` and `opacity`
- [ ] `content-visibility: auto` on long list items
