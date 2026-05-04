# Class Work — Add Transitions to a UI

## What You Will Build

Add smooth transitions to buttons, cards, and form inputs.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `transitions-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Transitions Demo</title>
  <link rel="stylesheet" href="transitions.css">
</head>
<body>

  <main>
    <h1>CSS Transitions</h1>

    <section>
      <h2>Button Transitions</h2>
      <div class="button-row">
        <button class="btn btn-primary">Hover Me</button>
        <button class="btn btn-outline">Outline Button</button>
        <button class="btn btn-ghost">Ghost Button</button>
      </div>
    </section>

    <section>
      <h2>Card Hover Effect</h2>
      <div class="card-grid">
        <div class="card">
          <h3>Card Title</h3>
          <p>Hover to see the lift effect.</p>
        </div>
        <div class="card">
          <h3>Another Card</h3>
          <p>Shadow and transform transition.</p>
        </div>
        <div class="card">
          <h3>Third Card</h3>
          <p>Smooth and performant.</p>
        </div>
      </div>
    </section>

    <section>
      <h2>Form Input Focus</h2>
      <form>
        <input type="text" placeholder="Your name" class="input">
        <input type="email" placeholder="Your email" class="input">
        <textarea placeholder="Your message" class="input textarea"></textarea>
        <button type="submit" class="btn btn-primary">Send</button>
      </form>
    </section>

    <section>
      <h2>Image Overlay</h2>
      <div class="image-grid">
        <div class="image-card">
          <img src="https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=400" alt="Mountain">
          <div class="overlay">
            <span>View Photo</span>
          </div>
        </div>
        <div class="image-card">
          <img src="https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=400" alt="Forest">
          <div class="overlay">
            <span>View Photo</span>
          </div>
        </div>
      </div>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `transitions.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 20px; color: #2c3e50; }
section { margin-bottom: 50px; }

/* Buttons */
.button-row { display: flex; gap: 1rem; flex-wrap: wrap; }

.btn {
  padding: 12px 28px;
  border-radius: 6px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  border: 2px solid transparent;
  transition: background 0.2s ease, color 0.2s ease, border-color 0.2s ease,
              transform 0.1s ease, box-shadow 0.2s ease;
}

.btn-primary {
  background: #3498db;
  color: white;
}
.btn-primary:hover {
  background: #2980b9;
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(52,152,219,0.4);
}
.btn-primary:active {
  transform: translateY(0);
  box-shadow: none;
}

.btn-outline {
  background: transparent;
  color: #3498db;
  border-color: #3498db;
}
.btn-outline:hover {
  background: #3498db;
  color: white;
}

.btn-ghost {
  background: transparent;
  color: #666;
  border-color: transparent;
}
.btn-ghost:hover {
  background: #f0f0f0;
  color: #333;
}

/* Cards */
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1.5rem;
}

.card {
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 1.5rem;
  transition: box-shadow 0.3s ease, transform 0.3s ease;
  cursor: pointer;
}

.card:hover {
  box-shadow: 0 12px 40px rgba(0,0,0,0.15);
  transform: translateY(-6px);
}

.card h3 { margin-bottom: 0.5rem; }
.card p  { color: #666; }

/* Form inputs */
form { display: flex; flex-direction: column; gap: 1rem; max-width: 500px; }

.input {
  padding: 12px 16px;
  border: 2px solid #ddd;
  border-radius: 6px;
  font-size: 1rem;
  outline: none;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.input:focus {
  border-color: #3498db;
  box-shadow: 0 0 0 3px rgba(52,152,219,0.2);
}

.textarea { min-height: 120px; resize: vertical; }

/* Image overlay */
.image-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1rem;
}

.image-card {
  position: relative;
  border-radius: 8px;
  overflow: hidden;
  cursor: pointer;
}

.image-card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  display: block;
  transition: transform 0.4s ease;
}

.image-card:hover img {
  transform: scale(1.05);
}

.overlay {
  position: absolute;
  inset: 0;
  background: rgba(0,0,0,0);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.3s ease;
}

.overlay span {
  color: white;
  font-weight: bold;
  font-size: 1.1rem;
  opacity: 0;
  transform: translateY(10px);
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.image-card:hover .overlay {
  background: rgba(0,0,0,0.5);
}

.image-card:hover .overlay span {
  opacity: 1;
  transform: translateY(0);
}

/* Respect reduced motion */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    transition-duration: 0.01ms !important;
  }
}
```

---

## Checklist

- [ ] Buttons have hover and active transitions
- [ ] Cards lift on hover with shadow and transform
- [ ] Form inputs show focus ring transition
- [ ] Image overlay fades in on hover
- [ ] Image scales slightly on hover
- [ ] `prefers-reduced-motion` respected
