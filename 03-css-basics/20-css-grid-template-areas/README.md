# 20 — CSS Grid: Template Areas

## What Is This Lesson About?

`grid-template-areas` lets you define your layout visually using named areas. It is one of the most readable and maintainable ways to build complex page layouts.

---

## grid-template-areas

```css
.layout {
  display: grid;
  grid-template-columns: 200px 1fr 200px;
  grid-template-rows: 64px 1fr auto;
  grid-template-areas:
    "header  header  header"
    "sidebar main    aside"
    "footer  footer  footer";
}
```

The string representation shows exactly what the layout looks like. Each word is a named area. Repeated names span multiple cells.

---

## grid-area

Assigns an element to a named area:

```css
.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.aside   { grid-area: aside; }
.footer  { grid-area: footer; }
```

---

## Spanning with Dots

Use `.` for empty cells:

```css
grid-template-areas:
  "header header header"
  "sidebar main  .     "
  "footer footer footer";
```

---

## Responsive Template Areas

```css
/* Mobile */
.layout {
  grid-template-columns: 1fr;
  grid-template-areas:
    "header"
    "main"
    "sidebar"
    "footer";
}

/* Desktop */
@media (min-width: 768px) {
  .layout {
    grid-template-columns: 250px 1fr;
    grid-template-areas:
      "header  header"
      "sidebar main"
      "footer  footer";
  }
}
```

---

## Benefits

- Layout is visually readable in CSS
- Easy to change layout by just editing the template string
- Responsive changes are clear and explicit
- No need to count column/row numbers
