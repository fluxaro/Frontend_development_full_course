# 22 — Responsive Design and Media Queries

## What Is This Lesson About?

Responsive design means your website looks and works great on all screen sizes — from a 320px phone to a 4K monitor. Media queries are the CSS tool that makes this possible.

---

## What Is a Media Query?

A media query applies CSS only when certain conditions are met.

```css
@media (condition) {
  /* CSS applied only when condition is true */
}
```

---

## Breakpoints

Common breakpoints (mobile-first approach):

```css
/* Mobile: default (no media query needed) */

/* Tablet */
@media (min-width: 640px) { }

/* Small desktop */
@media (min-width: 768px) { }

/* Desktop */
@media (min-width: 1024px) { }

/* Large desktop */
@media (min-width: 1280px) { }

/* XL */
@media (min-width: 1536px) { }
```

---

## Mobile-First vs Desktop-First

### Mobile-First (recommended)

Start with mobile styles, add complexity for larger screens:

```css
/* Mobile: single column */
.grid { display: grid; grid-template-columns: 1fr; }

/* Tablet: 2 columns */
@media (min-width: 768px) {
  .grid { grid-template-columns: 1fr 1fr; }
}

/* Desktop: 3 columns */
@media (min-width: 1024px) {
  .grid { grid-template-columns: repeat(3, 1fr); }
}
```

### Desktop-First

Start with desktop, simplify for smaller screens:

```css
/* Desktop: 3 columns */
.grid { display: grid; grid-template-columns: repeat(3, 1fr); }

/* Tablet: 2 columns */
@media (max-width: 1023px) {
  .grid { grid-template-columns: 1fr 1fr; }
}

/* Mobile: 1 column */
@media (max-width: 767px) {
  .grid { grid-template-columns: 1fr; }
}
```

---

## Media Query Types

```css
/* Width */
@media (min-width: 768px) { }
@media (max-width: 767px) { }
@media (min-width: 768px) and (max-width: 1023px) { }

/* Height */
@media (min-height: 600px) { }

/* Orientation */
@media (orientation: landscape) { }
@media (orientation: portrait) { }

/* Dark mode */
@media (prefers-color-scheme: dark) { }

/* Reduced motion */
@media (prefers-reduced-motion: reduce) { }

/* Print */
@media print { }

/* Hover capability */
@media (hover: hover) { }
@media (hover: none) { }  /* touch devices */
```

---

## Responsive Typography

```css
/* Fluid font size */
font-size: clamp(1rem, 2.5vw, 1.5rem);

/* Or with media queries */
h1 { font-size: 1.75rem; }

@media (min-width: 768px) {
  h1 { font-size: 2.5rem; }
}

@media (min-width: 1024px) {
  h1 { font-size: 3.5rem; }
}
```

---

## Responsive Images

```css
img {
  max-width: 100%;
  height: auto;
}
```

---

## The Viewport Meta Tag

Required for responsive design to work on mobile:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
