# Class Work — Refactor CSS to Use Nesting

## What You Will Do

Take a flat CSS file and refactor it to use CSS nesting, reducing repetition and improving readability.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `nesting-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Nesting Demo</title>
  <link rel="stylesheet" href="nesting.css">
</head>
<body>
  <nav class="navbar">
    <span class="navbar__logo">Brand</span>
    <ul class="navbar__links">
      <li class="navbar__item"><a class="navbar__link" href="#">Home</a></li>
      <li class="navbar__item"><a class="navbar__link" href="#">About</a></li>
      <li class="navbar__item navbar__item--active"><a class="navbar__link" href="#">Contact</a></li>
    </ul>
  </nav>

  <main>
    <div class="card">
      <div class="card__header">
        <h2 class="card__title">Card Title</h2>
        <span class="card__badge card__badge--new">New</span>
      </div>
      <div class="card__body">
        <p class="card__text">Card content goes here.</p>
      </div>
      <div class="card__footer">
        <button class="btn btn--primary">Primary</button>
        <button class="btn btn--ghost">Ghost</button>
      </div>
    </div>
  </main>
</body>
</html>
```

---

## Step 2 — Write Nested CSS

Create `nesting.css` using CSS nesting:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }

/* Navbar with nesting */
.navbar {
  background: #2c3e50;
  padding: 0 2rem;
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 2rem;

  &__logo {
    color: white;
    font-weight: 700;
    font-size: 1.2rem;
  }

  &__links {
    list-style: none;
    display: flex;
    gap: 0;
  }

  &__link {
    display: block;
    padding: 20px 16px;
    color: #bdc3c7;
    text-decoration: none;
    transition: color 0.2s;

    &:hover { color: white; }
  }

  &__item--active &__link {
    color: white;
    font-weight: 600;
  }
}

/* Card with nesting */
.card {
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  overflow: hidden;
  max-width: 400px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.06);

  &__header {
    padding: 1.5rem 1.5rem 0;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
  }

  &__title {
    font-size: 1.1rem;
    color: #2c3e50;
  }

  &__badge {
    padding: 2px 10px;
    border-radius: 20px;
    font-size: 0.7rem;
    font-weight: 700;
    color: white;

    &--new  { background: #3498db; }
    &--sale { background: #e74c3c; }
  }

  &__body {
    padding: 1rem 1.5rem;
  }

  &__text {
    color: #666;
    font-size: 0.9rem;
  }

  &__footer {
    padding: 1rem 1.5rem 1.5rem;
    display: flex;
    gap: 0.75rem;
  }
}

/* Buttons with nesting */
.btn {
  padding: 8px 20px;
  border-radius: 6px;
  font-size: 0.875rem;
  font-weight: 600;
  cursor: pointer;
  border: 2px solid transparent;
  transition: all 0.2s;

  &--primary {
    background: #3498db;
    color: white;
    border-color: #3498db;

    &:hover { background: #2980b9; border-color: #2980b9; }
  }

  &--ghost {
    background: transparent;
    color: #3498db;
    border-color: #3498db;

    &:hover { background: #3498db; color: white; }
  }
}
```

---

## Checklist

- [ ] Navbar uses `&__logo`, `&__links`, `&__link` nesting
- [ ] Active state uses `&__item--active &__link`
- [ ] Card uses `&__header`, `&__body`, `&__footer` nesting
- [ ] Badge variants use `&--new`, `&--sale` nesting
- [ ] Button variants use `&--primary`, `&--ghost` nesting
- [ ] Hover states nested inside their parent selectors
