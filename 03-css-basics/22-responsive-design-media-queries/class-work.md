# Class Work — Make a Page Responsive

## What You Will Build

Take a desktop-only layout and make it fully responsive using media queries.

**Time:** 35 minutes

---

## Step 1 — Create the Desktop Layout

Create `responsive-demo.html` and `responsive-demo.css`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Demo</title>
  <link rel="stylesheet" href="responsive-demo.css">
</head>
<body>

  <nav class="navbar">
    <span class="logo">Brand</span>
    <ul class="nav-links">
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>

  <section class="hero">
    <div class="hero-text">
      <h1>Build for Every Screen</h1>
      <p>Responsive design ensures your site works on all devices.</p>
      <a href="#" class="btn">Get Started</a>
    </div>
    <div class="hero-image">
      <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=600" alt="Developer working on laptop" width="600" height="400">
    </div>
  </section>

  <section class="features">
    <h2>Features</h2>
    <div class="features-grid">
      <div class="feature-card"><h3>Fast</h3><p>Optimized for performance.</p></div>
      <div class="feature-card"><h3>Responsive</h3><p>Works on all devices.</p></div>
      <div class="feature-card"><h3>Accessible</h3><p>Built for everyone.</p></div>
    </div>
  </section>

  <footer class="footer">
    <div class="footer-grid">
      <div><h4>Company</h4><ul><li>About</li><li>Blog</li></ul></div>
      <div><h4>Product</h4><ul><li>Features</li><li>Pricing</li></ul></div>
      <div><h4>Support</h4><ul><li>Docs</li><li>Contact</li></ul></div>
      <div><h4>Legal</h4><ul><li>Privacy</li><li>Terms</li></ul></div>
    </div>
    <p class="copyright">© 2025 Brand. All rights reserved.</p>
  </footer>

</body>
</html>
```

---

## Step 2 — Mobile-First CSS

Create `responsive-demo.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body { font-family: sans-serif; color: #333; }

/* === MOBILE FIRST === */

/* Navbar */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 1.5rem;
  background: #2c3e50;
}

.logo { color: white; font-weight: bold; font-size: 1.2rem; }

.nav-links {
  display: none; /* hidden on mobile */
  list-style: none;
  gap: 1.5rem;
}

.nav-links a { color: #bdc3c7; text-decoration: none; }

/* Hero: stacked on mobile */
.hero {
  display: flex;
  flex-direction: column;
  padding: 3rem 1.5rem;
  gap: 2rem;
}

.hero-text h1 { font-size: clamp(1.75rem, 5vw, 3rem); margin-bottom: 1rem; }
.hero-text p  { color: #666; margin-bottom: 1.5rem; }

.btn {
  display: inline-block;
  padding: 12px 28px;
  background: #3498db;
  color: white;
  text-decoration: none;
  border-radius: 6px;
}

.hero-image img { width: 100%; height: auto; border-radius: 8px; }

/* Features: 1 column on mobile */
.features { padding: 3rem 1.5rem; }
.features h2 { text-align: center; margin-bottom: 2rem; font-size: 1.75rem; }

.features-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.5rem;
}

.feature-card {
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 1.5rem;
}

.feature-card h3 { margin-bottom: 0.5rem; }
.feature-card p  { color: #666; }

/* Footer: stacked on mobile */
.footer { background: #2c3e50; color: #bdc3c7; padding: 3rem 1.5rem 1.5rem; }

.footer-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  margin-bottom: 2rem;
}

.footer h4 { color: white; margin-bottom: 0.75rem; }
.footer ul { list-style: none; }
.footer li { margin-bottom: 0.4rem; font-size: 0.9rem; }

.copyright { text-align: center; font-size: 0.85rem; padding-top: 1.5rem; border-top: 1px solid #34495e; }

/* === TABLET (640px+) === */
@media (min-width: 640px) {
  .features-grid { grid-template-columns: repeat(2, 1fr); }
  .footer-grid   { grid-template-columns: repeat(4, 1fr); }
}

/* === DESKTOP (1024px+) === */
@media (min-width: 1024px) {
  .nav-links { display: flex; }

  .hero {
    flex-direction: row;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    padding: 5rem 2rem;
  }

  .hero-text { flex: 1; }
  .hero-image { flex: 1; }

  .features { max-width: 1200px; margin: 0 auto; }
  .features-grid { grid-template-columns: repeat(3, 1fr); }
}
```

---

## Checklist

- [ ] Viewport meta tag present
- [ ] Mobile-first approach (min-width queries)
- [ ] Nav links hidden on mobile, visible on desktop
- [ ] Hero stacks on mobile, side-by-side on desktop
- [ ] Features: 1 → 2 → 3 columns
- [ ] Footer: 2 → 4 columns
- [ ] Images use `max-width: 100%`
- [ ] `clamp()` used for fluid heading
