# Notes — Modern CSS Selectors

## Quick Reference

```css
/* :is() — group selectors */
:is(h1, h2, h3) { color: blue; }
:is(article, section) p { }

/* :where() — zero specificity */
:where(header, footer) a { color: blue; }

/* :not() — exclusion */
li:not(:last-child) { border-bottom: 1px solid #eee; }
button:not(:disabled) { cursor: pointer; }

/* :has() — parent selector */
.card:has(img) { padding: 0; }
.field:has(input:invalid) label { color: red; }
```

## :is() vs :where()

| | :is() | :where() |
|---|---|---|
| Specificity | Highest in list | Zero |
| Override | Harder | Easy |
| Use for | Grouping | Resets, defaults |

## :has() Use Cases

```css
/* Card with image */
.card:has(img) { layout: different; }

/* Form validation */
.field:has(input:invalid) label { color: red; }

/* Navigation with open dropdown */
nav:has(.dropdown.open) { background: dark; }

/* Article without images */
article:not(:has(img)) { max-width: 65ch; }
```
