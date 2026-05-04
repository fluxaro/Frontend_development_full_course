# Class Work — Grid Item Placement

## What You Will Build

A magazine-style layout using explicit grid item placement.

**Time:** 35 minutes

---

## Step 1 — Create the HTML

Create `grid-placement.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Grid Item Placement</title>
  <link rel="stylesheet" href="grid-placement.css">
</head>
<body>

  <h1>Grid Item Placement</h1>

  <section>
    <h2>Magazine Layout</h2>
    <div class="magazine">
      <div class="item featured">Featured Article (spans 2 cols, 2 rows)</div>
      <div class="item side-1">Side Article 1</div>
      <div class="item side-2">Side Article 2</div>
      <div class="item side-3">Side Article 3</div>
      <div class="item full-width">Full Width Banner (spans all columns)</div>
      <div class="item small-1">Small 1</div>
      <div class="item small-2">Small 2</div>
      <div class="item small-3">Small 3</div>
      <div class="item small-4">Small 4</div>
    </div>
  </section>

  <section>
    <h2>Grid Lines Visualization</h2>
    <div class="grid-lines">
      <div class="gl-item" style="grid-column: 1/2; grid-row: 1/2;">1/1</div>
      <div class="gl-item" style="grid-column: 2/4; grid-row: 1/2;">2-3/1</div>
      <div class="gl-item" style="grid-column: 4/5; grid-row: 1/3;">4/1-2</div>
      <div class="gl-item" style="grid-column: 1/3; grid-row: 2/3;">1-2/2</div>
      <div class="gl-item" style="grid-column: 3/4; grid-row: 2/3;">3/2</div>
      <div class="gl-item" style="grid-column: 1/-1; grid-row: 3/4;">Full width (1/-1)</div>
    </div>
  </section>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `grid-placement.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 16px; color: #2c3e50; }
section { margin-bottom: 60px; }

/* Magazine layout */
.magazine {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: 200px 200px auto auto;
  gap: 12px;
}

.item {
  background: #3498db;
  color: white;
  padding: 20px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-weight: bold;
}

/* Featured: spans 2 columns and 2 rows */
.featured {
  grid-column: 1 / 3;
  grid-row: 1 / 3;
  background: #2c3e50;
  font-size: 1.1rem;
}

/* Side articles */
.side-1 { grid-column: 3; grid-row: 1; background: #9b59b6; }
.side-2 { grid-column: 4; grid-row: 1; background: #e74c3c; }
.side-3 { grid-column: 3 / 5; grid-row: 2; background: #27ae60; }

/* Full width banner */
.full-width {
  grid-column: 1 / -1;  /* span all columns */
  background: #f39c12;
  color: #333;
}

/* Small articles */
.small-1, .small-2, .small-3, .small-4 {
  background: #1abc9c;
}

/* Grid lines visualization */
.grid-lines {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(3, 100px);
  gap: 8px;
  background: #ecf0f1;
  padding: 8px;
  border-radius: 8px;
}

.gl-item {
  background: #3498db;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
  font-size: 0.85rem;
  font-weight: bold;
}
```

---

## Checklist

- [ ] Featured item spans 2 columns and 2 rows
- [ ] Side article spans 2 columns with `3 / 5`
- [ ] Full-width banner uses `1 / -1`
- [ ] Grid lines visualization shows explicit placement
- [ ] All items are placed correctly without overlap
