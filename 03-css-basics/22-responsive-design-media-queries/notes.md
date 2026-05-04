# Notes — Responsive Design and Media Queries

## Breakpoints (Mobile-First)

```css
/* Mobile: default */
/* Tablet: */
@media (min-width: 640px) { }
/* Desktop: */
@media (min-width: 1024px) { }
/* Large: */
@media (min-width: 1280px) { }
```

## Common Media Queries

```css
@media (prefers-color-scheme: dark) { }
@media (prefers-reduced-motion: reduce) { }
@media (orientation: landscape) { }
@media print { }
@media (hover: hover) { }
```

## Responsive Grid Pattern

```css
.grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

@media (min-width: 640px) {
  .grid { grid-template-columns: repeat(2, 1fr); }
}

@media (min-width: 1024px) {
  .grid { grid-template-columns: repeat(3, 1fr); }
}
```

## Responsive Images

```css
img { max-width: 100%; height: auto; }
```

## Common Mistakes

- Forgetting the viewport meta tag
- Using desktop-first when mobile-first is better
- Too many breakpoints (3–4 is usually enough)
- Not testing on real devices
