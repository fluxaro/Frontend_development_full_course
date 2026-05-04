# Class Work — Build a Card Component with BEM

## What You Will Build

A card component library using strict BEM naming conventions.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `bem-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BEM Demo</title>
  <link rel="stylesheet" href="bem.css">
</head>
<body>

  <nav class="nav">
    <span class="nav__logo">Brand</span>
    <ul class="nav__list">
      <li class="nav__item"><a class="nav__link" href="#">Home</a></li>
      <li class="nav__item"><a class="nav__link nav__link--active" href="#">About</a></li>
      <li class="nav__item"><a class="nav__link" href="#">Contact</a></li>
    </ul>
  </nav>

  <main>
    <div class="card-grid">

      <div class="card">
        <img class="card__image" src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=360&h=180&fit=crop" alt="Code" width="360" height="180" loading="lazy">
        <div class="card__body">
          <span class="badge badge--info">Tutorial</span>
          <h2 class="card__title">Default Card</h2>
          <p class="card__text">This is a default card using BEM naming.</p>
          <div class="card__footer">
            <button class="btn btn--primary">Read More</button>
          </div>
        </div>
      </div>

      <div class="card card--featured">
        <img class="card__image" src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=360&h=180&fit=crop" alt="Developer" width="360" height="180" loading="lazy">
        <div class="card__body">
          <span class="badge badge--success">Featured</span>
          <h2 class="card__title">Featured Card</h2>
          <p class="card__text">The --featured modifier adds a colored border.</p>
          <div class="card__footer">
            <button class="btn btn--primary">Read More</button>
            <button class="btn btn--ghost">Save</button>
          </div>
        </div>
      </div>

    </div>
  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `bem.css` using strict BEM — no nested selectors:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; background: #f8f9fa; padding: 0; }

/* Nav */
.nav { background: #2c3e50; padding: 0 2rem; height: 64px; display: flex; align-items: center; justify-content: space-between; margin-bottom: 2rem; }
.nav__logo { color: white; font-weight: 700; font-size: 1.2rem; }
.nav__list { list-style: none; display: flex; }
.nav__link { display: block; padding: 20px 16px; color: #bdc3c7; text-decoration: none; }
.nav__link:hover { color: white; }
.nav__link--active { color: white; font-weight: 600; }

/* Card grid */
.card-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 1.5rem; padding: 2rem; max-width: 900px; margin: 0 auto; }

/* Card */
.card { background: white; border: 1px solid #e0e0e0; border-radius: 12px; overflow: hidden; }
.card--featured { border-color: #3498db; border-width: 2px; }
.card__image { width: 100%; height: 180px; object-fit: cover; display: block; }
.card__body { padding: 1.5rem; }
.card__title { font-size: 1.1rem; color: #2c3e50; margin: 0.5rem 0; }
.card__text { color: #666; font-size: 0.9rem; margin-bottom: 1rem; }
.card__footer { display: flex; gap: 0.75rem; }

/* Button */
.btn { padding: 8px 20px; border-radius: 6px; font-size: 0.875rem; font-weight: 600; cursor: pointer; border: 2px solid transparent; }
.btn--primary { background: #3498db; color: white; border-color: #3498db; }
.btn--primary:hover { background: #2980b9; }
.btn--ghost { background: transparent; color: #3498db; border-color: #3498db; }
.btn--ghost:hover { background: #3498db; color: white; }

/* Badge */
.badge { display: inline-block; padding: 2px 10px; border-radius: 20px; font-size: 0.7rem; font-weight: 700; }
.badge--info    { background: #ebf5fb; color: #3498db; }
.badge--success { background: #eafaf1; color: #27ae60; }
.badge--warning { background: #fef9e7; color: #f39c12; }
.badge--danger  { background: #fdf2f2; color: #e74c3c; }
```

---

## Checklist

- [ ] No nested selectors (`.card .card__title` is forbidden)
- [ ] All selectors are flat (specificity 0,1,0)
- [ ] Modifiers always used with base class
- [ ] BEM naming is consistent throughout
