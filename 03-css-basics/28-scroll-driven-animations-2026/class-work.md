# Class Work — Scroll Progress Bar and Fade-in Sections

## What You Will Build

A page with a scroll progress bar and sections that fade in as you scroll.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `scroll-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Scroll-Driven Animations</title>
  <link rel="stylesheet" href="scroll-demo.css">
</head>
<body>

  <!-- Scroll progress bar -->
  <div class="progress-bar"></div>

  <main>
    <section class="hero">
      <h1>Scroll-Driven Animations</h1>
      <p>Scroll down to see elements animate into view.</p>
    </section>

    <section class="reveal-section">
      <h2>Section 1</h2>
      <p>This section fades in as you scroll to it.</p>
    </section>

    <section class="reveal-section">
      <h2>Section 2</h2>
      <p>Each section animates independently.</p>
    </section>

    <div class="card-grid">
      <div class="reveal-card">Card 1</div>
      <div class="reveal-card">Card 2</div>
      <div class="reveal-card">Card 3</div>
    </div>

    <section class="reveal-section">
      <h2>Section 3</h2>
      <p>No JavaScript needed for these animations.</p>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `scroll-demo.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; }

/* === SCROLL PROGRESS BAR === */
@keyframes grow-bar {
  from { width: 0%; }
  to   { width: 100%; }
}

.progress-bar {
  position: fixed;
  top: 0;
  left: 0;
  height: 4px;
  background: linear-gradient(to right, #3498db, #9b59b6);
  z-index: 1000;
  width: 0%;
}

@supports (animation-timeline: scroll()) {
  .progress-bar {
    animation: grow-bar linear;
    animation-timeline: scroll(root);
  }
}

/* === SECTIONS === */
.hero {
  height: 100dvh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  background: #2c3e50;
  color: white;
  padding: 2rem;
}

.hero h1 { font-size: 3rem; margin-bottom: 1rem; }

.reveal-section {
  max-width: 800px;
  margin: 0 auto;
  padding: 5rem 2rem;
}

.reveal-section h2 { font-size: 2rem; margin-bottom: 1rem; }
.reveal-section p  { color: #666; font-size: 1.1rem; }

/* === FADE IN ON SCROLL === */
@keyframes fade-slide-up {
  from { opacity: 0; transform: translateY(30px); }
  to   { opacity: 1; transform: translateY(0); }
}

@supports (animation-timeline: view()) {
  .reveal-section {
    animation: fade-slide-up linear;
    animation-timeline: view();
    animation-range: entry 0% entry 60%;
  }
}

/* Fallback for older browsers */
@supports not (animation-timeline: view()) {
  .reveal-section {
    opacity: 1;
    transform: none;
  }
}

/* === CARD GRID === */
.card-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem;
}

.reveal-card {
  background: #3498db;
  color: white;
  padding: 2rem;
  border-radius: 8px;
  text-align: center;
  font-weight: bold;
  font-size: 1.2rem;
}

@supports (animation-timeline: view()) {
  .reveal-card {
    animation: fade-slide-up linear;
    animation-timeline: view();
    animation-range: entry 0% entry 70%;
  }
}
```

---

## Checklist

- [ ] Progress bar fills as you scroll
- [ ] Sections fade in as they enter the viewport
- [ ] Cards animate in on scroll
- [ ] `@supports` fallback included
- [ ] Page has enough content to scroll
