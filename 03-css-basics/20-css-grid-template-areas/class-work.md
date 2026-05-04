# Class Work — Page Layout with Grid Template Areas

## What You Will Build

A complete page layout using named grid areas.

**Time:** 35 minutes

---

## Step 1 — Create the HTML

Create `grid-areas.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Grid Template Areas</title>
  <link rel="stylesheet" href="grid-areas.css">
</head>
<body>

  <div class="page-layout">

    <header class="header">
      <span class="logo">MyApp</span>
      <nav>
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
      </nav>
    </header>

    <aside class="sidebar">
      <h3>Sidebar</h3>
      <ul>
        <li><a href="#">Dashboard</a></li>
        <li><a href="#">Analytics</a></li>
        <li><a href="#">Settings</a></li>
        <li><a href="#">Profile</a></li>
      </ul>
    </aside>

    <main class="main">
      <h1>Main Content Area</h1>
      <p>This is the main content. It takes up the largest area of the layout.</p>
      <p>The layout is defined using <code>grid-template-areas</code> which makes it very readable.</p>
      <div class="cards">
        <div class="card">Card 1</div>
        <div class="card">Card 2</div>
        <div class="card">Card 3</div>
      </div>
    </main>

    <aside class="aside">
      <h3>Right Panel</h3>
      <p>Additional information or widgets go here.</p>
    </aside>

    <footer class="footer">
      <p>Footer — Copyright 2025 MyApp</p>
    </footer>

  </div>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `grid-areas.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; background: #f0f2f5; color: #333; }

/* Grid layout with named areas */
.page-layout {
  display: grid;
  grid-template-columns: 220px 1fr 200px;
  grid-template-rows: 64px 1fr auto;
  grid-template-areas:
    "header  header  header"
    "sidebar main    aside"
    "footer  footer  footer";
  min-height: 100dvh;
  gap: 0;
}

/* Assign each element to its area */
.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.aside   { grid-area: aside; }
.footer  { grid-area: footer; }

/* Styles */
.header {
  background: #2c3e50;
  color: white;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 2rem;
}

.logo { font-size: 1.2rem; font-weight: bold; }
.header nav { display: flex; gap: 1.5rem; }
.header a { color: #bdc3c7; text-decoration: none; }

.sidebar {
  background: #34495e;
  color: white;
  padding: 2rem 1.5rem;
}

.sidebar h3 { margin-bottom: 1rem; font-size: 0.8rem; text-transform: uppercase; letter-spacing: 1px; color: #95a5a6; }
.sidebar ul { list-style: none; }
.sidebar li { margin-bottom: 0.5rem; }
.sidebar a { color: #bdc3c7; text-decoration: none; display: block; padding: 6px 0; }
.sidebar a:hover { color: white; }

.main {
  padding: 2rem;
  background: #f8f9fa;
}

.main h1 { margin-bottom: 1rem; }
.main p  { margin-bottom: 1rem; color: #666; }

.cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  margin-top: 1.5rem;
}

.card {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  border: 1px solid #e0e0e0;
  text-align: center;
}

.aside {
  background: white;
  border-left: 1px solid #e0e0e0;
  padding: 2rem 1.5rem;
}

.aside h3 { margin-bottom: 1rem; color: #2c3e50; }

.footer {
  background: #2c3e50;
  color: #95a5a6;
  padding: 1.5rem 2rem;
  text-align: center;
  font-size: 0.9rem;
}

/* Responsive: stack on mobile */
@media (max-width: 768px) {
  .page-layout {
    grid-template-columns: 1fr;
    grid-template-areas:
      "header"
      "main"
      "sidebar"
      "aside"
      "footer";
  }
}
```

---

## Checklist

- [ ] `grid-template-areas` defines the layout visually
- [ ] Each element uses `grid-area` to assign itself
- [ ] Header spans all 3 columns
- [ ] Footer spans all 3 columns
- [ ] Sidebar, main, and aside are in the middle row
- [ ] Responsive: stacks to single column on mobile
