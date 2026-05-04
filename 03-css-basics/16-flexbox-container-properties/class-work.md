# Class Work — Flexbox Container Properties

## What You Will Build

A visual playground for all flexbox container properties.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `flexbox-container.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flexbox Container Demo</title>
  <link rel="stylesheet" href="flexbox-container.css">
</head>
<body>

  <h1>Flexbox Container Properties</h1>

  <section>
    <h2>justify-content</h2>
    <div class="demo-row">
      <div class="flex-demo jc-start"><div>A</div><div>B</div><div>C</div></div>
      <div class="flex-demo jc-center"><div>A</div><div>B</div><div>C</div></div>
      <div class="flex-demo jc-end"><div>A</div><div>B</div><div>C</div></div>
      <div class="flex-demo jc-between"><div>A</div><div>B</div><div>C</div></div>
      <div class="flex-demo jc-around"><div>A</div><div>B</div><div>C</div></div>
      <div class="flex-demo jc-evenly"><div>A</div><div>B</div><div>C</div></div>
    </div>
  </section>

  <section>
    <h2>align-items</h2>
    <div class="demo-row">
      <div class="flex-demo ai-start tall"><div>A</div><div class="tall-item">B</div><div>C</div></div>
      <div class="flex-demo ai-center tall"><div>A</div><div class="tall-item">B</div><div>C</div></div>
      <div class="flex-demo ai-end tall"><div>A</div><div class="tall-item">B</div><div>C</div></div>
      <div class="flex-demo ai-stretch tall"><div>A</div><div class="tall-item">B</div><div>C</div></div>
    </div>
  </section>

  <section>
    <h2>flex-direction</h2>
    <div class="demo-row">
      <div class="flex-demo fd-row"><div>A</div><div>B</div><div>C</div></div>
      <div class="flex-demo fd-column"><div>A</div><div>B</div><div>C</div></div>
      <div class="flex-demo fd-row-reverse"><div>A</div><div>B</div><div>C</div></div>
    </div>
  </section>

  <section>
    <h2>flex-wrap</h2>
    <div class="flex-demo fw-wrap">
      <div>Item 1</div><div>Item 2</div><div>Item 3</div>
      <div>Item 4</div><div>Item 5</div><div>Item 6</div>
      <div>Item 7</div><div>Item 8</div>
    </div>
  </section>

  <section>
    <h2>Real-world: Navigation Bar</h2>
    <nav class="navbar">
      <span class="logo">MyApp</span>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
      <button>Sign Up</button>
    </nav>
  </section>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `flexbox-container.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 16px; color: #2c3e50; }
section { margin-bottom: 50px; }

.demo-row { display: flex; flex-direction: column; gap: 12px; }

.flex-demo {
  display: flex;
  background: #ebf5fb;
  border: 2px solid #3498db;
  border-radius: 8px;
  padding: 12px;
  min-height: 60px;
  gap: 8px;
}

.flex-demo div {
  background: #3498db;
  color: white;
  padding: 8px 16px;
  border-radius: 4px;
  font-weight: bold;
  font-size: 0.9rem;
}

/* justify-content */
.jc-start   { justify-content: flex-start; }
.jc-center  { justify-content: center; }
.jc-end     { justify-content: flex-end; }
.jc-between { justify-content: space-between; }
.jc-around  { justify-content: space-around; }
.jc-evenly  { justify-content: space-evenly; }

/* align-items */
.tall { min-height: 100px; }
.tall-item { height: 80px; display: flex; align-items: center; }
.ai-start   { align-items: flex-start; }
.ai-center  { align-items: center; }
.ai-end     { align-items: flex-end; }
.ai-stretch { align-items: stretch; }

/* flex-direction */
.fd-row         { flex-direction: row; }
.fd-column      { flex-direction: column; min-height: 150px; }
.fd-row-reverse { flex-direction: row-reverse; }

/* flex-wrap */
.fw-wrap { flex-wrap: wrap; }
.fw-wrap div { width: 120px; }

/* Navbar */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #2c3e50;
  padding: 0 2rem;
  height: 64px;
  border-radius: 8px;
}

.logo { color: white; font-weight: bold; font-size: 1.2rem; }
.navbar ul { list-style: none; display: flex; gap: 1.5rem; }
.navbar a { color: #bdc3c7; text-decoration: none; }
.navbar button { padding: 8px 20px; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; }
```

---

## Checklist

- [ ] All 6 `justify-content` values demonstrated
- [ ] All 4 `align-items` values demonstrated
- [ ] `flex-direction` row, column, and row-reverse shown
- [ ] `flex-wrap` demonstrated with many items
- [ ] Real navbar built with flexbox
