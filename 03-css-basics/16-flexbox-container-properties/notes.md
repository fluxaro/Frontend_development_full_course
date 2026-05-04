# Notes — Flexbox Container Properties

## Quick Reference

```css
.container {
  display: flex;
  flex-direction: row | column | row-reverse | column-reverse;
  flex-wrap: nowrap | wrap | wrap-reverse;
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
  align-items: stretch | flex-start | flex-end | center | baseline;
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
  gap: 1rem;
}
```

## Axis Reference

| flex-direction | Main Axis | Cross Axis |
|---|---|---|
| `row` | Horizontal (→) | Vertical (↓) |
| `column` | Vertical (↓) | Horizontal (→) |

## justify-content vs align-items

- `justify-content` → main axis
- `align-items` → cross axis

## Common Patterns

```css
/* Center */
display: flex; justify-content: center; align-items: center;

/* Space between nav items */
display: flex; justify-content: space-between; align-items: center;

/* Wrap cards */
display: flex; flex-wrap: wrap; gap: 1rem;
```
