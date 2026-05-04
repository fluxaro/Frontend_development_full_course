# Class Work — CSS Grid Basics

## What You Will Build

A visual grid playground demonstrating all grid template properties.

**Time:** 35 minutes

---

## Step 1 — Create the HTML

Create `grid-basics.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Grid Basics</title>
  <link rel="stylesheet" href="grid-basics.css">
</head>
<body>

  <h1>CSS Grid Basics</h1>

  <section>
    <h2>3-Column Equal Grid</h2>
    <div class="grid-3col">
      <div class="cell">1</div><div class="cell">2</div><div class="cell">3</div>
      <div class="cell">4</div><div class="cell">5</div><div class="cell">6</div>
    </div>
  </section>

  <section>
    <h2>Mixed Column Widths</h2>
    <div class="grid-mixed">
      <div class="cell">Sidebar (200px)</div>
      <div class="cell">Main (1fr)</div>
      <div class="cell">Aside (150px)</div>
    </div>
  </section>

  <section>
    <h2>repeat() and fr units</h2>
    <div class="grid-repeat">
      <div class="cell">1</div><div class="cell">2</div><div class="cell">3</div>
      <div class="cell">4</div><div class="cell">5</div><div class="cell">6</div>
      <div class="cell">7</div><div class="cell">8</div>
    </div>
  </section>

  <section>
    <h2>auto-fill vs auto-fit</h2>
    <h3>auto-fill</h3>
    <div class="grid-autofill">
      <div class="cell">A</div><div class="cell">B</div><div class="cell">C</div>
    </div>
    <h3>auto-fit</h3>
    <div class="grid-autofit">
      <div class="cell">A</div><div class="cell">B</div><div class="cell">C</div>
    </div>
  </section>

  <section>
    <h2>Explicit Rows</h2>
    <div class="grid-rows">
      <div class="cell">Row 1 (100px)</div>
      <div class="cell">Row 2 (200px)</div>
      <div class="cell">Row 3 (auto)</div>
    </div>
  </section>

  <section>
    <h2>gap</h2>
    <div class="grid-gap">
      <div class="cell">1</div><div class="cell">2</div><div class="cell">3</div>
      <div class="cell">4</div><div class="cell">5</div><div class="cell">6</div>
    </div>
  </section>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `grid-basics.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 12px; color: #2c3e50; }
h3 { margin: 16px 0 8px; color: #555; font-size: 0.9rem; }
section { margin-bottom: 50px; }

.cell {
  background: #3498db;
  color: white;
  padding: 20px;
  border-radius: 4px;
  text-align: center;
  font-weight: bold;
}

/* 3 equal columns */
.grid-3col {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 12px;
}

/* Mixed widths */
.grid-mixed {
  display: grid;
  grid-template-columns: 200px 1fr 150px;
  gap: 12px;
}

/* repeat() */
.grid-repeat {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
}

/* auto-fill */
.grid-autofill {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 12px;
  margin-bottom: 16px;
}

/* auto-fit */
.grid-autofit {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 12px;
}

/* Explicit rows */
.grid-rows {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 100px 200px auto;
  gap: 12px;
}

/* Gap */
.grid-gap {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px 12px; /* row-gap | column-gap */
}
```

---

## Checklist

- [ ] 3-column equal grid with `1fr 1fr 1fr`
- [ ] Mixed widths with `200px 1fr 150px`
- [ ] `repeat()` function used
- [ ] `auto-fill` vs `auto-fit` demonstrated
- [ ] Explicit row heights with `grid-template-rows`
- [ ] `gap` with different row and column values
