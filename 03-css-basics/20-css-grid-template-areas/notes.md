# Notes — Grid Template Areas

## Quick Reference

```css
.layout {
  display: grid;
  grid-template-columns: 200px 1fr;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.footer  { grid-area: footer; }
```

## Rules

- Each row must have the same number of cells
- Named areas must be rectangular
- Use `.` for empty cells
- Repeated names span multiple cells

## Common Layouts

```css
/* Holy Grail */
grid-template-areas:
  "header header header"
  "nav    main   aside"
  "footer footer footer";

/* Dashboard */
grid-template-areas:
  "sidebar header"
  "sidebar main"
  "sidebar footer";

/* Blog */
grid-template-areas:
  "header"
  "main"
  "footer";
```
