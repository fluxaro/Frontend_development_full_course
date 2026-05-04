# Class Work — Container Queries Demo

## What You Will Build

A card component that adapts to its container size using container queries.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `container-queries.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Container Queries Demo</title>
  <link rel="stylesheet" href="container-queries.css">
</head>
<body>

  <h1>Container Queries Demo</h1>
  <p>The same card component adapts to its container size.</p>

  <div class="demo-layout">

    <!-- Narrow container -->
    <div class="container-narrow">
      <h2>Narrow (250px)</h2>
      <div class="card-wrapper">
        <div class="card">
          <img src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=400" alt="Code on screen">
          <div class="card-body">
            <h3>Card Title</h3>
            <p>This card adapts to its container width.</p>
            <a href="#" class="btn">Read More</a>
          </div>
        </div>
      </div>
    </div>

    <!-- Medium container -->
    <div class="container-medium">
      <h2>Medium (400px)</h2>
      <div class="card-wrapper">
        <div class="card">
          <img src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=400" alt="Code on screen">
          <div class="card-body">
            <h3>Card Title</h3>
            <p>This card adapts to its container width.</p>
            <a href="#" class="btn">Read More</a>
          </div>
        </div>
      </div>
    </div>

    <!-- Wide container -->
    <div class="container-wide">
      <h2>Wide (600px)</h2>
      <div class="card-wrapper">
        <div class="card">
          <img src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=400" alt="Code on screen">
          <div class="card-body">
            <h3>Card Title</h3>
            <p>This card adapts to its container width. In a wide container, it shows more content.</p>
            <a href="#" class="btn">Read More</a>
          </div>
        </div>
      </div>
    </div>

  </div>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `container-queries.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 8px; }
p  { margin-bottom: 40px; color: #666; }
h2 { margin-bottom: 12px; color: #555; font-size: 0.9rem; text-transform: uppercase; }

.demo-layout {
  display: flex;
  gap: 2rem;
  flex-wrap: wrap;
  align-items: flex-start;
}

/* Container sizes */
.container-narrow { width: 250px; }
.container-medium { width: 400px; }
.container-wide   { width: 600px; }

/* Define containment context */
.card-wrapper {
  container-type: inline-size;
}

/* === BASE CARD (narrow/default) === */
.card {
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  overflow: hidden;
}

.card img {
  width: 100%;
  height: 160px;
  object-fit: cover;
  display: block;
}

.card-body {
  padding: 1rem;
}

.card-body h3 { margin-bottom: 0.5rem; font-size: 1rem; }
.card-body p  { color: #666; font-size: 0.875rem; margin-bottom: 1rem; }

.btn {
  display: inline-block;
  padding: 6px 16px;
  background: #3498db;
  color: white;
  text-decoration: none;
  border-radius: 4px;
  font-size: 0.875rem;
}

/* === MEDIUM CONTAINER (350px+) === */
@container (min-width: 350px) {
  .card {
    display: flex;
    flex-direction: row;
  }

  .card img {
    width: 140px;
    height: auto;
    flex-shrink: 0;
  }

  .card-body {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
}

/* === WIDE CONTAINER (550px+) === */
@container (min-width: 550px) {
  .card img {
    width: 200px;
  }

  .card-body h3 { font-size: 1.25rem; }
  .card-body p  { font-size: 1rem; }

  .btn {
    padding: 10px 24px;
    font-size: 1rem;
  }
}
```

---

## Checklist

- [ ] `container-type: inline-size` on `.card-wrapper`
- [ ] Default card is stacked (narrow)
- [ ] `@container (min-width: 350px)` makes card horizontal
- [ ] `@container (min-width: 550px)` makes card larger
- [ ] Same HTML, different layouts based on container
