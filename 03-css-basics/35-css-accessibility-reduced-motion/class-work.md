# Class Work — Make a Page Accessible

## What You Will Build

Add accessibility features to an existing page: focus styles, skip links, reduced motion, and color contrast.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `accessible-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Accessible Demo</title>
  <link rel="stylesheet" href="accessible.css">
</head>
<body>

  <!-- Skip link -->
  <a href="#main" class="skip-link">Skip to main content</a>

  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>

  <main id="main">
    <h1>Accessible Page Demo</h1>
    <p>Tab through this page to see the focus styles.</p>

    <div class="card-grid">
      <div class="card">
        <h2>Animated Card</h2>
        <p>Hover to see the animation. Users with reduced motion get a simpler effect.</p>
        <button class="btn">Action</button>
      </div>
      <div class="card">
        <h2>Another Card</h2>
        <p>All interactive elements have visible focus styles.</p>
        <button class="btn">Action</button>
      </div>
    </div>

    <form>
      <label for="name">Name</label>
      <input type="text" id="name" placeholder="Enter your name">
      <button type="submit" class="btn">Submit</button>
    </form>
  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `accessible.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }

/* Skip link */
.skip-link {
  position: absolute;
  top: -100%;
  left: 0;
  padding: 8px 16px;
  background: #3498db;
  color: white;
  font-weight: 600;
  z-index: 1000;
  text-decoration: none;
  border-radius: 0 0 4px 0;
}

.skip-link:focus { top: 0; }

/* Focus styles */
:focus-visible {
  outline: 2px solid #3498db;
  outline-offset: 2px;
  border-radius: 4px;
}

:focus:not(:focus-visible) { outline: none; }

/* Navigation */
nav { background: #2c3e50; padding: 0 2rem; margin-bottom: 2rem; }
nav ul { list-style: none; display: flex; }
nav a { display: block; padding: 16px; color: #bdc3c7; text-decoration: none; }
nav a:hover { color: white; }

/* Cards */
.card-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 1rem; margin-bottom: 2rem; }

.card {
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 1.5rem;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 24px rgba(0,0,0,0.12);
}

/* Reduced motion */
@media (prefers-reduced-motion: reduce) {
  .card { transition: box-shadow 0.3s ease; }
  .card:hover { transform: none; }
}

.card h2 { margin-bottom: 0.5rem; }
.card p  { color: #666; font-size: 0.9rem; margin-bottom: 1rem; }

/* Buttons */
.btn {
  padding: 10px 20px;
  background: #3498db; color: white;
  border: none; border-radius: 6px; cursor: pointer;
  font-size: 1rem; font-weight: 600;
  transition: background 0.2s;
}

.btn:hover { background: #2980b9; }

/* Form */
form { display: flex; flex-direction: column; gap: 8px; max-width: 300px; }
label { font-weight: 600; font-size: 0.9rem; }
input {
  padding: 10px 14px;
  border: 2px solid #ddd;
  border-radius: 6px;
  font-size: 1rem;
  outline: none;
}
input:focus { border-color: #3498db; }
```

---

## Checklist

- [ ] Skip link appears on focus
- [ ] All interactive elements have visible focus styles
- [ ] Card animation is disabled for reduced motion users
- [ ] Color contrast is sufficient (check with browser DevTools)
- [ ] Tab through the page — every element is reachable
