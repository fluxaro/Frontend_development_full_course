# Class Work — Hero Section with Gradient Overlay

## What You Will Build

A hero section with a background image, gradient overlay, and multiple background techniques.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `backgrounds-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Backgrounds Demo</title>
  <link rel="stylesheet" href="backgrounds.css">
</head>
<body>

  <!-- Hero with image + gradient overlay -->
  <section class="hero">
    <div class="hero-content">
      <h1>Beautiful Backgrounds</h1>
      <p>Using CSS backgrounds, gradients, and overlays.</p>
      <a href="#" class="btn">Get Started</a>
    </div>
  </section>

  <main>

    <section class="gradient-demos">
      <h2>Gradient Types</h2>
      <div class="gradient-grid">
        <div class="grad-linear-lr">Linear: left to right</div>
        <div class="grad-linear-diag">Linear: diagonal</div>
        <div class="grad-radial">Radial gradient</div>
        <div class="grad-conic">Conic gradient</div>
        <div class="grad-multi">Multi-stop gradient</div>
        <div class="grad-repeating">Repeating gradient</div>
      </div>
    </section>

    <section class="bg-demos">
      <h2>Background Properties</h2>
      <div class="bg-grid">
        <div class="bg-cover">background-size: cover</div>
        <div class="bg-contain">background-size: contain</div>
        <div class="bg-fixed">background-attachment: fixed</div>
        <div class="bg-clip-text">
          <h3 class="gradient-text">Gradient Text</h3>
        </div>
      </div>
    </section>

    <section class="pattern-demos">
      <h2>CSS Patterns</h2>
      <div class="pattern-grid">
        <div class="pattern-stripes">Diagonal stripes</div>
        <div class="pattern-dots">Dot pattern</div>
        <div class="pattern-grid-bg">Grid pattern</div>
      </div>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `backgrounds.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; color: #333; }

/* Hero with image + gradient overlay */
.hero {
  height: 100dvh;
  background:
    linear-gradient(135deg, rgba(52, 152, 219, 0.8), rgba(155, 89, 182, 0.8)),
    url('https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=1600') center/cover no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: white;
}

.hero-content h1 { font-size: 3rem; margin-bottom: 1rem; }
.hero-content p  { font-size: 1.2rem; margin-bottom: 2rem; opacity: 0.9; }

.btn {
  display: inline-block;
  padding: 12px 32px;
  background: white;
  color: #3498db;
  text-decoration: none;
  border-radius: 30px;
  font-weight: 600;
}

main { max-width: 1200px; margin: 0 auto; padding: 4rem 2rem; }
section { margin-bottom: 4rem; }
h2 { font-size: 1.5rem; margin-bottom: 1.5rem; color: #2c3e50; }

/* Gradient demos */
.gradient-grid, .bg-grid, .pattern-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1rem;
}

.gradient-grid div, .bg-grid div, .pattern-grid div {
  height: 120px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 0.85rem;
  font-weight: 600;
  text-align: center;
  padding: 1rem;
  text-shadow: 0 1px 3px rgba(0,0,0,0.3);
}

.grad-linear-lr   { background: linear-gradient(to right, #3498db, #9b59b6); }
.grad-linear-diag { background: linear-gradient(135deg, #f093fb, #f5576c); }
.grad-radial      { background: radial-gradient(circle, #4facfe, #00f2fe); }
.grad-conic       { background: conic-gradient(from 0deg, #f093fb, #f5576c, #4facfe, #f093fb); }
.grad-multi       { background: linear-gradient(to right, #f093fb 0%, #f5576c 25%, #4facfe 75%, #00f2fe 100%); }
.grad-repeating   { background: repeating-linear-gradient(45deg, #3498db 0px, #3498db 10px, #2980b9 10px, #2980b9 20px); }

/* Background property demos */
.bg-cover {
  background: url('https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=400') center/cover no-repeat;
}

.bg-contain {
  background: url('https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=400') center/contain no-repeat #1a1a2e;
}

.bg-fixed {
  background: url('https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=400') center/cover fixed;
}

.bg-clip-text {
  background: linear-gradient(135deg, #667eea, #764ba2);
  display: flex;
  align-items: center;
  justify-content: center;
}

.gradient-text {
  font-size: 2rem;
  background: linear-gradient(to right, #f093fb, #f5576c);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* CSS Patterns */
.pattern-stripes {
  background: repeating-linear-gradient(
    -45deg, #3498db 0px, #3498db 10px, #2980b9 10px, #2980b9 20px
  );
}

.pattern-dots {
  background-color: #1a1a2e;
  background-image: radial-gradient(circle, #3498db 1px, transparent 1px);
  background-size: 20px 20px;
}

.pattern-grid-bg {
  background-color: #1a1a2e;
  background-image:
    linear-gradient(rgba(52,152,219,0.3) 1px, transparent 1px),
    linear-gradient(90deg, rgba(52,152,219,0.3) 1px, transparent 1px);
  background-size: 20px 20px;
}
```

---

## Checklist

- [ ] Hero uses image + gradient overlay with multiple backgrounds
- [ ] All 6 gradient types demonstrated
- [ ] `background-size: cover` and `contain` shown
- [ ] Gradient text using `background-clip: text`
- [ ] CSS patterns using repeating gradients
