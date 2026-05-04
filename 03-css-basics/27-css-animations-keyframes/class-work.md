# Class Work — Build Animated Components

## What You Will Build

A page with loading spinner, fade-in cards, and a pulsing notification badge.

**Time:** 35 minutes

---

## Step 1 — Create the HTML

Create `animations-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Animations Demo</title>
  <link rel="stylesheet" href="animations.css">
</head>
<body>

  <main>
    <h1>CSS Animations</h1>

    <section>
      <h2>Loading Spinner</h2>
      <div class="spinner"></div>
    </section>

    <section>
      <h2>Fade In Cards (staggered)</h2>
      <div class="card-grid">
        <div class="card fade-card">Card 1</div>
        <div class="card fade-card">Card 2</div>
        <div class="card fade-card">Card 3</div>
        <div class="card fade-card">Card 4</div>
      </div>
    </section>

    <section>
      <h2>Slide Up Hero</h2>
      <div class="hero">
        <h2 class="hero-title">Welcome to My Site</h2>
        <p class="hero-text">This text slides up when the page loads.</p>
        <button class="hero-btn">Get Started</button>
      </div>
    </section>

    <section>
      <h2>Notification Badge</h2>
      <div class="icon-wrapper">
        <span class="icon">🔔</span>
        <span class="badge">3</span>
      </div>
    </section>

    <section>
      <h2>Skeleton Loading</h2>
      <div class="skeleton-card">
        <div class="skeleton skeleton-avatar"></div>
        <div class="skeleton-content">
          <div class="skeleton skeleton-line"></div>
          <div class="skeleton skeleton-line short"></div>
          <div class="skeleton skeleton-line"></div>
        </div>
      </div>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `animations.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 20px; color: #2c3e50; }
section { margin-bottom: 60px; }

/* === KEYFRAMES === */

@keyframes spin {
  from { transform: rotate(0deg); }
  to   { transform: rotate(360deg); }
}

@keyframes fadeSlideUp {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}

@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50%       { transform: scale(1.2); }
}

@keyframes shimmer {
  0%   { background-position: -200% 0; }
  100% { background-position: 200% 0; }
}

/* === SPINNER === */
.spinner {
  width: 48px;
  height: 48px;
  border: 4px solid #e0e0e0;
  border-top-color: #3498db;
  border-radius: 50%;
  animation: spin 0.8s linear infinite;
}

/* === FADE CARDS === */
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1rem;
}

.card {
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 1.5rem;
  text-align: center;
  font-weight: bold;
  opacity: 0;
  animation: fadeSlideUp 0.5s ease forwards;
}

.fade-card:nth-child(1) { animation-delay: 0.1s; }
.fade-card:nth-child(2) { animation-delay: 0.2s; }
.fade-card:nth-child(3) { animation-delay: 0.3s; }
.fade-card:nth-child(4) { animation-delay: 0.4s; }

/* === HERO === */
.hero {
  background: #2c3e50;
  color: white;
  padding: 3rem;
  border-radius: 12px;
  text-align: center;
}

.hero-title {
  font-size: 2rem;
  animation: fadeSlideUp 0.6s ease 0.2s both;
}

.hero-text {
  margin: 1rem 0 1.5rem;
  opacity: 0.8;
  animation: fadeSlideUp 0.6s ease 0.4s both;
}

.hero-btn {
  padding: 12px 28px;
  background: #3498db;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-size: 1rem;
  animation: fadeSlideUp 0.6s ease 0.6s both;
}

/* === NOTIFICATION BADGE === */
.icon-wrapper { position: relative; display: inline-block; }
.icon { font-size: 2rem; }

.badge {
  position: absolute;
  top: -8px;
  right: -8px;
  background: #e74c3c;
  color: white;
  width: 22px;
  height: 22px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75rem;
  font-weight: bold;
  animation: pulse 1.5s ease infinite;
}

/* === SKELETON === */
.skeleton-card {
  display: flex;
  gap: 1rem;
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  border: 1px solid #e0e0e0;
  max-width: 400px;
}

.skeleton {
  background: linear-gradient(90deg, #f0f0f0 25%, #e0e0e0 50%, #f0f0f0 75%);
  background-size: 200% 100%;
  animation: shimmer 1.5s infinite;
  border-radius: 4px;
}

.skeleton-avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  flex-shrink: 0;
}

.skeleton-content { flex: 1; display: flex; flex-direction: column; gap: 8px; }
.skeleton-line { height: 14px; }
.skeleton-line.short { width: 60%; }

/* Reduced motion */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
  }
}
```

---

## Checklist

- [ ] Spinner uses `spin` keyframes with `infinite`
- [ ] Cards use `fadeSlideUp` with staggered delays
- [ ] Hero elements animate in sequence
- [ ] Badge pulses with `pulse` keyframes
- [ ] Skeleton uses `shimmer` keyframes
- [ ] `prefers-reduced-motion` respected
