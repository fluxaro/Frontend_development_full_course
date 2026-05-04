# 16 — Flexbox: Container Properties

## What Is This Lesson About?

Flexbox is a one-dimensional layout system that makes it easy to align and distribute items in a row or column. This lesson covers the properties applied to the **flex container** (the parent element).

---

## Enabling Flexbox

```css
.container {
  display: flex;
}
```

All direct children become **flex items**.

---

## flex-direction

Controls the main axis direction.

```css
flex-direction: row;            /* default: left to right */
flex-direction: row-reverse;    /* right to left */
flex-direction: column;         /* top to bottom */
flex-direction: column-reverse; /* bottom to top */
```

---

## flex-wrap

Controls whether items wrap to a new line.

```css
flex-wrap: nowrap;   /* default: all on one line */
flex-wrap: wrap;     /* wrap to next line */
flex-wrap: wrap-reverse; /* wrap in reverse */
```

---

## justify-content

Aligns items along the **main axis** (horizontal in row, vertical in column).

```css
justify-content: flex-start;    /* default */
justify-content: flex-end;
justify-content: center;
justify-content: space-between; /* equal space between */
justify-content: space-around;  /* equal space around */
justify-content: space-evenly;  /* equal space everywhere */
```

---

## align-items

Aligns items along the **cross axis** (vertical in row, horizontal in column).

```css
align-items: stretch;     /* default: fill cross axis */
align-items: flex-start;
align-items: flex-end;
align-items: center;
align-items: baseline;
```

---

## align-content

Aligns **rows** when there is extra space on the cross axis (only when wrapping).

```css
align-content: flex-start;
align-content: flex-end;
align-content: center;
align-content: space-between;
align-content: space-around;
align-content: stretch;
```

---

## gap

Space between flex items.

```css
gap: 1rem;          /* row and column gap */
gap: 1rem 2rem;     /* row-gap | column-gap */
row-gap: 1rem;
column-gap: 2rem;
```

---

## Common Patterns

```css
/* Center anything */
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Navigation bar */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

/* Card grid that wraps */
.card-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

/* Vertical stack */
.stack {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
```
