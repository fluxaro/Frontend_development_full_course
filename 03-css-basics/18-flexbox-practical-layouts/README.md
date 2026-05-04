# 18 — Flexbox Practical Layouts

## What Is This Lesson About?

This lesson applies everything from the previous two flexbox lessons to build real-world UI layouts. You will build navigation bars, hero sections, card grids, sidebar layouts, and more.

---

## The 5 Essential Flexbox Layouts

### 1. Navigation Bar

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 2rem;
  height: 64px;
}
```

### 2. Centered Hero

```css
.hero {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100dvh;
  text-align: center;
}
```

### 3. Responsive Card Grid

```css
.card-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
}

.card {
  flex: 1 1 280px;  /* grow, shrink, min 280px */
}
```

### 4. Sidebar Layout

```css
.layout {
  display: flex;
  gap: 2rem;
}

.sidebar { flex: 0 0 280px; }  /* fixed width */
.main    { flex: 1; }           /* fill remaining */
```

### 5. Media Object (Image + Text)

```css
.media {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
}

.media-img  { flex-shrink: 0; }
.media-body { flex: 1; }
```

---

## Push to End with margin-left: auto

```css
.navbar {
  display: flex;
  align-items: center;
}

.logo { /* stays left */ }
.nav-links { margin-left: auto; /* pushes to right */ }
```

---

## Responsive Flexbox

```css
/* Mobile: stack vertically */
.layout {
  display: flex;
  flex-direction: column;
}

/* Desktop: side by side */
@media (min-width: 768px) {
  .layout {
    flex-direction: row;
  }
  .sidebar { flex: 0 0 280px; }
  .main    { flex: 1; }
}
```
