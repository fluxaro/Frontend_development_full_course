# 35 — CSS Accessibility and Reduced Motion

## What Is This Lesson About?

CSS plays a critical role in accessibility. This lesson covers focus styles, color contrast, reduced motion, and other CSS techniques that make your site usable by everyone.

---

## prefers-reduced-motion

Some users have vestibular disorders or motion sensitivity. The `prefers-reduced-motion` media query lets you disable or reduce animations for these users.

```css
/* Default: full animation */
.card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 40px rgba(0,0,0,0.2);
}

/* Reduced motion: no transform, keep shadow */
@media (prefers-reduced-motion: reduce) {
  .card {
    transition: box-shadow 0.3s ease;
  }

  .card:hover {
    transform: none;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  }
}
```

---

## Focus Styles

Never remove focus outlines — they are critical for keyboard navigation.

```css
/* Good: visible focus ring */
:focus-visible {
  outline: 2px solid #3498db;
  outline-offset: 2px;
  border-radius: 4px;
}

/* Remove only for mouse users (not keyboard) */
:focus:not(:focus-visible) {
  outline: none;
}
```

---

## Skip Links

Allow keyboard users to skip navigation:

```css
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
}

.skip-link:focus {
  top: 0;
}
```

---

## Color Contrast

WCAG 2.1 AA requires:
- Normal text: 4.5:1 contrast ratio
- Large text (18px+ or 14px+ bold): 3:1 ratio
- UI components and graphics: 3:1 ratio

---

## Accessible Animations

```css
/* Prefer opacity/color over transform for reduced motion */
@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}

/* Full animation */
.card { animation: slideUp 0.5s ease; }

/* Reduced motion: fade only */
@media (prefers-reduced-motion: reduce) {
  .card { animation: fadeIn 0.3s ease; }
}
```
