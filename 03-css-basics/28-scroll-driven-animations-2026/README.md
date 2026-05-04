# 28 — Scroll-Driven Animations (2026)

## What Is This Lesson About?

Scroll-driven animations let you tie CSS animations to the scroll position — no JavaScript needed. Elements can animate as they enter the viewport or as the user scrolls through a section.

---

## animation-timeline

Links an animation to a scroll timeline:

```css
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}

.element {
  animation: fadeIn linear;
  animation-timeline: view();
  animation-range: entry 0% entry 100%;
}
```

---

## scroll() Timeline

Ties animation to the scroll position of a scroll container:

```css
.progress-bar {
  animation: grow linear;
  animation-timeline: scroll(root);
}

@keyframes grow {
  from { width: 0%; }
  to   { width: 100%; }
}
```

---

## view() Timeline

Ties animation to when an element enters/exits the viewport:

```css
.card {
  animation: slideIn linear;
  animation-timeline: view();
  animation-range: entry 0% entry 50%;
}
```

---

## animation-range

Controls when in the scroll timeline the animation plays:

```css
animation-range: entry 0% entry 100%;   /* as element enters */
animation-range: exit 0% exit 100%;     /* as element exits */
animation-range: contain 0% contain 100%; /* while fully visible */
```

---

## Browser Support

Scroll-driven animations are supported in Chrome 115+, Edge 115+, and Safari 18+. As of 2026, they are safe to use with a fallback.

---

## Fallback Pattern

```css
/* Fallback for older browsers */
.card { opacity: 0; transform: translateY(20px); }

/* Scroll-driven for modern browsers */
@supports (animation-timeline: view()) {
  .card {
    animation: fadeIn linear;
    animation-timeline: view();
    animation-range: entry 0% entry 60%;
  }
}
```
