# 25 — CSS Transitions

## What Is This Lesson About?

CSS transitions animate property changes smoothly over time. When a property changes (on hover, focus, or class change), instead of jumping instantly, it transitions smoothly.

---

## The transition Property

```css
transition: property duration timing-function delay;

/* Examples */
transition: all 0.3s ease;
transition: background-color 0.2s ease;
transition: transform 0.3s ease, opacity 0.3s ease;
```

---

## transition-property

Which property to animate:

```css
transition-property: all;
transition-property: background-color;
transition-property: transform, opacity;
```

---

## transition-duration

How long the transition takes:

```css
transition-duration: 0.3s;
transition-duration: 300ms;
```

---

## transition-timing-function

The speed curve of the transition:

```css
transition-timing-function: ease;          /* default */
transition-timing-function: linear;
transition-timing-function: ease-in;
transition-timing-function: ease-out;
transition-timing-function: ease-in-out;
transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
```

---

## transition-delay

Wait before starting:

```css
transition-delay: 0.1s;
```

---

## What Can Be Transitioned

Most CSS properties can be transitioned. But for performance, only animate:
- `transform` — translate, scale, rotate, skew
- `opacity`

These only trigger compositing (cheapest rendering step).

---

## Common Patterns

```css
/* Button hover */
.btn {
  background: #3498db;
  transition: background 0.2s ease, transform 0.1s ease;
}
.btn:hover {
  background: #2980b9;
  transform: translateY(-2px);
}

/* Card lift */
.card {
  transition: box-shadow 0.3s ease, transform 0.3s ease;
}
.card:hover {
  box-shadow: 0 12px 40px rgba(0,0,0,0.2);
  transform: translateY(-4px);
}

/* Fade */
.overlay {
  opacity: 0;
  transition: opacity 0.3s ease;
}
.overlay.visible {
  opacity: 1;
}
```
