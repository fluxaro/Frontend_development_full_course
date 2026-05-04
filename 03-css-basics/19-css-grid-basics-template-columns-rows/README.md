# 19 — CSS Grid: template-columns and template-rows

## What Is This Lesson About?

CSS Grid is a two-dimensional layout system. Unlike Flexbox (one direction), Grid lets you control both rows and columns simultaneously. It is the most powerful layout tool in CSS.

---

## Enabling Grid

```css
.container {
  display: grid;
}
```

---

## grid-template-columns

Defines the number and size of columns.

```css
/* 3 equal columns */
grid-template-columns: 1fr 1fr 1fr;

/* Mixed sizes */
grid-template-columns: 200px 1fr 150px;

/* Using repeat() */
grid-template-columns: repeat(3, 1fr);
grid-template-columns: repeat(4, 200px);

/* Responsive with auto-fill */
grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));

/* Responsive with auto-fit */
grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
```

---

## grid-template-rows

Defines the number and size of rows.

```css
grid-template-rows: 100px 200px auto;
grid-template-rows: repeat(3, 1fr);
grid-template-rows: auto;  /* default: size to content */
```

---

## The fr Unit

`fr` stands for "fraction". It divides available space proportionally.

```css
grid-template-columns: 1fr 2fr 1fr;
/* Column 1: 25%, Column 2: 50%, Column 3: 25% */
```

---

## minmax()

Sets a minimum and maximum size for a track.

```css
grid-template-columns: repeat(3, minmax(200px, 1fr));
/* Each column: at least 200px, at most 1fr */
```

---

## auto-fill vs auto-fit

```css
/* auto-fill: creates empty columns if space allows */
grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));

/* auto-fit: collapses empty columns, items stretch */
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

---

## gap

```css
gap: 1rem;           /* row and column gap */
gap: 1rem 2rem;      /* row-gap | column-gap */
row-gap: 1rem;
column-gap: 2rem;
```

---

## Common Grid Patterns

```css
/* 12-column grid */
grid-template-columns: repeat(12, 1fr);

/* Holy grail layout */
grid-template-columns: 200px 1fr 200px;
grid-template-rows: auto 1fr auto;

/* Responsive cards */
grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
```
