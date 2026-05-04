# 21 — CSS Grid: Item Placement

## What Is This Lesson About?

Grid item placement lets you control exactly where each item sits in the grid — spanning multiple columns or rows, and positioning items at specific grid lines.

---

## Grid Lines

Grid lines are numbered starting from 1. A 3-column grid has 4 column lines (1, 2, 3, 4).

```
|  1  |  2  |  3  |
1     2     3     4
```

---

## grid-column and grid-row

```css
/* Start at line 1, end at line 3 (spans 2 columns) */
.item { grid-column: 1 / 3; }

/* Start at line 2, span 2 columns */
.item { grid-column: 2 / span 2; }

/* Span 2 from current position */
.item { grid-column: span 2; }

/* Span to last line */
.item { grid-column: 1 / -1; }
```

---

## grid-area Shorthand

```css
/* row-start / col-start / row-end / col-end */
.item { grid-area: 1 / 1 / 2 / 4; }
```

---

## align-self and justify-self

Control alignment of a single item within its cell:

```css
.item {
  align-self: start | end | center | stretch;
  justify-self: start | end | center | stretch;
}
```

---

## place-self

Shorthand for `align-self` and `justify-self`:

```css
.item { place-self: center; }
.item { place-self: start end; }
```

---

## Common Patterns

```css
/* Full-width header */
.header { grid-column: 1 / -1; }

/* Feature card spanning 2 columns */
.featured { grid-column: span 2; }

/* Tall item spanning 2 rows */
.tall { grid-row: span 2; }

/* Centered in cell */
.centered { place-self: center; }
```
