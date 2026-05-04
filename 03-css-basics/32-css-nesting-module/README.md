# 32 — CSS Nesting Module

## What Is This Lesson About?

CSS nesting lets you write nested CSS rules inside parent rules — similar to how Sass/SCSS works, but now natively in CSS. It reduces repetition and makes component styles more readable.

---

## Basic Nesting

```css
/* Without nesting */
.card { background: white; }
.card h2 { color: #2c3e50; }
.card p  { color: #666; }
.card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.1); }

/* With nesting */
.card {
  background: white;

  h2 { color: #2c3e50; }
  p  { color: #666; }

  &:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
}
```

---

## The & Selector

`&` refers to the parent selector:

```css
.btn {
  background: blue;

  &:hover { background: darkblue; }    /* .btn:hover */
  &:active { transform: scale(0.98); } /* .btn:active */
  &.large { font-size: 1.2rem; }       /* .btn.large */
  &--primary { background: #3498db; }  /* .btn--primary */
}
```

---

## Nesting with BEM

```css
.card {
  background: white;
  border-radius: 8px;

  &__header {
    padding: 1.5rem;
    border-bottom: 1px solid #eee;
  }

  &__title {
    font-size: 1.2rem;
    color: #2c3e50;
  }

  &__body {
    padding: 1.5rem;
  }

  &--featured {
    border: 2px solid #3498db;
  }
}
```

---

## Nested Media Queries

```css
.hero {
  font-size: 1.5rem;

  @media (min-width: 768px) {
    font-size: 2.5rem;
  }

  @media (min-width: 1024px) {
    font-size: 3.5rem;
  }
}
```

---

## Browser Support

CSS nesting is supported in all modern browsers (Chrome 112+, Firefox 117+, Safari 16.5+). As of 2026, it is safe to use in production.
