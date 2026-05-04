# Class Work — Flexbox Item Properties

## What You Will Build

A visual demo of all flexbox item properties.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `flexbox-items.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flexbox Item Properties</title>
  <link rel="stylesheet" href="flexbox-items.css">
</head>
<body>

  <h1>Flexbox Item Properties</h1>

  <section>
    <h2>flex-grow</h2>
    <p>Items with higher flex-grow take more available space.</p>
    <div class="flex-container">
      <div class="item grow-0">grow: 0</div>
      <div class="item grow-1">grow: 1</div>
      <div class="item grow-2">grow: 2</div>
      <div class="item grow-3">grow: 3</div>
    </div>
  </section>

  <section>
    <h2>flex-shrink</h2>
    <p>Items with higher flex-shrink shrink more when space is tight.</p>
    <div class="flex-container narrow">
      <div class="item shrink-0">shrink: 0 (won't shrink)</div>
      <div class="item shrink-1">shrink: 1</div>
      <div class="item shrink-3">shrink: 3 (shrinks most)</div>
    </div>
  </section>

  <section>
    <h2>flex-basis</h2>
    <p>Sets the initial size before grow/shrink is applied.</p>
    <div class="flex-container">
      <div class="item basis-auto">basis: auto</div>
      <div class="item basis-200">basis: 200px</div>
      <div class="item basis-30">basis: 30%</div>
    </div>
  </section>

  <section>
    <h2>align-self</h2>
    <p>Override align-items for individual items.</p>
    <div class="flex-container tall">
      <div class="item as-start">start</div>
      <div class="item as-center">center</div>
      <div class="item as-end">end</div>
      <div class="item as-stretch">stretch</div>
    </div>
  </section>

  <section>
    <h2>order</h2>
    <p>Change visual order without changing HTML order.</p>
    <div class="flex-container">
      <div class="item order-3">HTML 1st (order: 3)</div>
      <div class="item order-1">HTML 2nd (order: 1)</div>
      <div class="item order-2">HTML 3rd (order: 2)</div>
    </div>
  </section>

  <section>
    <h2>Real-world: Sidebar Layout</h2>
    <div class="sidebar-layout">
      <aside class="sidebar">Sidebar (fixed 250px)</aside>
      <main class="main-content">Main content (flex: 1 — takes remaining space)</main>
    </div>
  </section>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `flexbox-items.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 8px; color: #2c3e50; }
p  { margin-bottom: 12px; color: #666; font-size: 0.9rem; }
section { margin-bottom: 50px; }

.flex-container {
  display: flex;
  background: #ebf5fb;
  border: 2px solid #3498db;
  border-radius: 8px;
  padding: 12px;
  gap: 8px;
  min-height: 60px;
}

.flex-container.narrow { width: 500px; }
.flex-container.tall   { min-height: 120px; align-items: stretch; }

.item {
  background: #3498db;
  color: white;
  padding: 10px 16px;
  border-radius: 4px;
  font-size: 0.85rem;
  font-weight: 600;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

/* flex-grow */
.grow-0 { flex-grow: 0; }
.grow-1 { flex-grow: 1; }
.grow-2 { flex-grow: 2; background: #2980b9; }
.grow-3 { flex-grow: 3; background: #1a6fa8; }

/* flex-shrink */
.shrink-0 { flex-shrink: 0; flex-basis: 200px; background: #27ae60; }
.shrink-1 { flex-shrink: 1; flex-basis: 200px; }
.shrink-3 { flex-shrink: 3; flex-basis: 200px; background: #e74c3c; }

/* flex-basis */
.basis-auto { flex-basis: auto; }
.basis-200  { flex-basis: 200px; background: #9b59b6; }
.basis-30   { flex-basis: 30%; background: #f39c12; }

/* align-self */
.as-start   { align-self: flex-start; }
.as-center  { align-self: center; }
.as-end     { align-self: flex-end; }
.as-stretch { align-self: stretch; }

/* order */
.order-1 { order: 1; background: #27ae60; }
.order-2 { order: 2; background: #f39c12; }
.order-3 { order: 3; background: #e74c3c; }

/* Sidebar layout */
.sidebar-layout {
  display: flex;
  gap: 1rem;
  min-height: 200px;
}

.sidebar {
  flex: 0 0 250px; /* don't grow, don't shrink, 250px basis */
  background: #2c3e50;
  color: white;
  padding: 20px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.main-content {
  flex: 1; /* grow to fill remaining space */
  background: white;
  border: 1px solid #e0e0e0;
  padding: 20px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

---

## Checklist

- [ ] `flex-grow` demo shows items taking proportional space
- [ ] `flex-shrink` demo shows items shrinking differently
- [ ] `flex-basis` demo shows initial sizes
- [ ] `align-self` demo shows individual alignment
- [ ] `order` demo shows visual reordering
- [ ] Sidebar layout uses `flex: 0 0 250px` and `flex: 1`
