# 37 — Intersection Observer

## What Is This Lesson About?

The Intersection Observer API lets you detect when an element enters or exits the viewport — without scroll event listeners. It's the modern way to implement lazy loading, scroll animations, and infinite scroll.

---

## Basic Usage

```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      console.log('Element is visible!', entry.target);
    }
  });
});

// Observe an element
const el = document.querySelector('.card');
observer.observe(el);

// Stop observing
observer.unobserve(el);
observer.disconnect(); // stop all observations
```

---

## Options

```javascript
const observer = new IntersectionObserver(callback, {
  root: null,          // null = viewport
  rootMargin: '0px',   // expand/shrink root bounds
  threshold: 0.5,      // 0-1: how much must be visible (0.5 = 50%)
});

// Multiple thresholds
const observer = new IntersectionObserver(callback, {
  threshold: [0, 0.25, 0.5, 0.75, 1],
});
```

---

## Scroll Animations

```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
      observer.unobserve(entry.target); // animate once
    }
  });
}, { threshold: 0.1 });

document.querySelectorAll('.animate-on-scroll').forEach(el => {
  observer.observe(el);
});
```

```css
.animate-on-scroll {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}
.animate-on-scroll.visible {
  opacity: 1;
  transform: translateY(0);
}
```

---

## Lazy Loading Images

```javascript
const imageObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const img = entry.target;
      img.src = img.dataset.src; // load the real image
      imageObserver.unobserve(img);
    }
  });
});

document.querySelectorAll('img[data-src]').forEach(img => {
  imageObserver.observe(img);
});
```

---

## Common Mistakes

- Not calling `unobserve` after a one-time animation (keeps firing)
- Using scroll event listeners instead (Intersection Observer is more performant)
- Setting `threshold: 1` when the element is taller than the viewport (never triggers)
