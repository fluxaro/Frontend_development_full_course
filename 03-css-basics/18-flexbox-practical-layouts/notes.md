# Notes — Flexbox Practical Layouts

## Layout Patterns

```css
/* Center anything */
.center { display: flex; justify-content: center; align-items: center; }

/* Navbar */
.navbar { display: flex; justify-content: space-between; align-items: center; }

/* Push to right */
.push { margin-left: auto; }

/* Sidebar */
.sidebar { flex: 0 0 280px; }
.main    { flex: 1; }

/* Responsive cards */
.card { flex: 1 1 280px; }

/* Media object */
.media { display: flex; gap: 1rem; align-items: flex-start; }
.media-img { flex-shrink: 0; }
.media-body { flex: 1; }
```

## When to Use Flexbox vs Grid

| Use Flexbox | Use Grid |
|---|---|
| One-dimensional (row OR column) | Two-dimensional (rows AND columns) |
| Navigation bars | Page layouts |
| Card rows | Complex grids |
| Centering | Magazine layouts |
| Aligning items | Overlapping elements |
