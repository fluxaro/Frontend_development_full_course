# Class Work — Build 5 Real Layouts with Flexbox

## What You Will Build

Five real-world UI layouts using only flexbox.

**Time:** 45 minutes

---

## Layout 1: Navigation Bar

```html
<nav class="navbar">
  <a href="/" class="logo">Brand</a>
  <ul class="nav-links">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
  </ul>
  <div class="nav-actions">
    <a href="#" class="btn-ghost">Login</a>
    <a href="#" class="btn-primary">Sign Up</a>
  </div>
</nav>
```

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 2rem;
  height: 64px;
  background: #2c3e50;
}
.nav-links { display: flex; list-style: none; gap: 1.5rem; }
.nav-actions { display: flex; gap: 0.75rem; align-items: center; }
```

---

## Layout 2: Hero Section

```html
<section class="hero">
  <div class="hero-content">
    <h1>Build Amazing Things</h1>
    <p>Start your journey today.</p>
    <div class="hero-buttons">
      <a href="#" class="btn-primary">Get Started</a>
      <a href="#" class="btn-ghost">Learn More</a>
    </div>
  </div>
</section>
```

```css
.hero {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100dvh;
  text-align: center;
}
.hero-buttons { display: flex; gap: 1rem; justify-content: center; margin-top: 2rem; }
```

---

## Layout 3: Card Grid

```html
<div class="card-grid">
  <div class="card">Card 1</div>
  <div class="card">Card 2</div>
  <div class="card">Card 3</div>
  <div class="card">Card 4</div>
  <div class="card">Card 5</div>
  <div class="card">Card 6</div>
</div>
```

```css
.card-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
}
.card {
  flex: 1 1 280px; /* grow, shrink, min 280px */
  max-width: calc(33.333% - 1rem);
}
```

---

## Layout 4: Sidebar Layout

```html
<div class="page-layout">
  <aside class="sidebar">Sidebar</aside>
  <main class="content">Main Content</main>
</div>
```

```css
.page-layout {
  display: flex;
  gap: 2rem;
  min-height: calc(100dvh - 64px);
}
.sidebar { flex: 0 0 280px; }
.content { flex: 1; }
```

---

## Layout 5: Media Object (Image + Text)

```html
<div class="media">
  <img class="media-img" src="avatar.jpg" alt="User">
  <div class="media-body">
    <h3>User Name</h3>
    <p>This is a comment or description text.</p>
  </div>
</div>
```

```css
.media {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
}
.media-img { flex-shrink: 0; width: 48px; height: 48px; border-radius: 50%; }
.media-body { flex: 1; }
```

---

## Your Task

Create `flexbox-layouts.html` and `flexbox-layouts.css` implementing all 5 layouts on one page with real content.

---

## Checklist

- [ ] Navbar with logo, links, and actions
- [ ] Hero section centered both ways
- [ ] Card grid that wraps
- [ ] Sidebar layout
- [ ] Media object pattern
