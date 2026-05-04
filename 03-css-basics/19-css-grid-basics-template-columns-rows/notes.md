# Notes — CSS Grid Basics

## Quick Reference

```css
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: auto;
  gap: 1rem;
}
```

## Column Patterns

```css
/* Equal columns */
grid-template-columns: 1fr 1fr 1fr;
grid-template-columns: repeat(3, 1fr);

/* Mixed */
grid-template-columns: 250px 1fr;
grid-template-columns: 200px 1fr 150px;

/* Responsive */
grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
```

## auto-fill vs auto-fit

- `auto-fill` — creates as many columns as fit, even if empty
- `auto-fit` — collapses empty columns, items stretch to fill

## fr Unit

`1fr` = one fraction of available space.

```css
grid-template-columns: 1fr 2fr 1fr;
/* 25% | 50% | 25% */
```

## Common Mistakes

- Forgetting `display: grid` on the container
- Using `fr` units for rows (usually use `auto` or fixed heights)
- Confusing `auto-fill` and `auto-fit`
- Not using `minmax()` with `auto-fill/fit`
