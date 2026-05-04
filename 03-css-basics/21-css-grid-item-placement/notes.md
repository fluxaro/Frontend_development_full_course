# Notes — Grid Item Placement

## Quick Reference

```css
.item {
  grid-column: 1 / 3;        /* start / end */
  grid-column: 1 / span 2;   /* start / span count */
  grid-column: span 2;       /* span from current position */
  grid-row: 1 / 3;
  grid-area: 1 / 1 / 3 / 3;  /* row-start / col-start / row-end / col-end */
}
```

## Shorthand

```css
/* grid-area: row-start / col-start / row-end / col-end */
.item { grid-area: 1 / 1 / 2 / 4; }
```

## Negative Line Numbers

```css
/* Span to the last column */
.item { grid-column: 1 / -1; }
```

## align-self and justify-self

```css
.item {
  align-self: start | end | center | stretch;
  justify-self: start | end | center | stretch;
}
```

## Common Patterns

```css
/* Full-width item */
.full-width { grid-column: 1 / -1; }

/* Span 2 columns */
.span-2 { grid-column: span 2; }

/* Center in cell */
.centered { align-self: center; justify-self: center; }
```
