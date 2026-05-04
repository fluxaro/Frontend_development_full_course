# 17 — Flexbox Item Properties: grow, shrink, basis

## What Is This Lesson About?

While container properties control the overall layout, item properties give you fine-grained control over individual flex items — how much they grow, shrink, and what their initial size is.

---

## flex-grow

Controls how much an item grows relative to other items when there is extra space.

```css
.item-a { flex-grow: 1; }  /* takes 1 part of extra space */
.item-b { flex-grow: 2; }  /* takes 2 parts of extra space */
.item-c { flex-grow: 0; }  /* does not grow (default) */
```

---

## flex-shrink

Controls how much an item shrinks relative to others when there is not enough space.

```css
.item-a { flex-shrink: 1; }  /* shrinks normally (default) */
.item-b { flex-shrink: 3; }  /* shrinks 3x as much */
.item-c { flex-shrink: 0; }  /* never shrinks */
```

---

## flex-basis

Sets the initial size of an item before grow/shrink is applied.

```css
flex-basis: auto;    /* use content size (default) */
flex-basis: 200px;   /* fixed initial size */
flex-basis: 30%;     /* percentage of container */
flex-basis: 0;       /* start from 0, then grow */
```

---

## flex Shorthand

```css
flex: grow shrink basis;

flex: 1;          /* 1 1 0 — grow and shrink equally */
flex: auto;       /* 1 1 auto */
flex: none;       /* 0 0 auto — fixed size */
flex: 0 0 250px;  /* fixed 250px */
```

---

## align-self

Overrides `align-items` for a single item.

```css
.item { align-self: flex-start | flex-end | center | stretch | baseline; }
```

---

## order

Changes the visual order without changing HTML order.

```css
.item-1 { order: 3; }  /* appears last */
.item-2 { order: 1; }  /* appears first */
.item-3 { order: 2; }  /* appears second */
```

---

## Common Patterns

```css
/* Sidebar layout */
.sidebar { flex: 0 0 280px; }  /* fixed, never grows or shrinks */
.main    { flex: 1; }           /* fills remaining space */

/* Equal columns */
.col { flex: 1; }

/* Push to end */
.push-right { margin-left: auto; }

/* Don't shrink below content size */
.no-shrink { flex-shrink: 0; }
```
