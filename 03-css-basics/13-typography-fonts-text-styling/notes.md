# Notes — Typography

## Font Properties Cheat Sheet

```css
font-family: 'Inter', sans-serif;
font-size: 1rem;
font-weight: 400;        /* 100-900 */
font-style: italic;
line-height: 1.6;        /* unitless = relative to font-size */
letter-spacing: 0.05em;
```

## Text Properties Cheat Sheet

```css
text-align: left | center | right | justify;
text-decoration: none | underline | line-through;
text-transform: none | uppercase | lowercase | capitalize;
text-overflow: ellipsis;
white-space: nowrap | pre | pre-wrap | normal;
```

## Truncation Patterns

```css
/* Single line */
.truncate {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

/* Multi-line (3 lines) */
.clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
```

## Google Fonts Quick Setup

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
```

```css
body { font-family: 'Inter', sans-serif; }
```

## Readable Typography Rules

- Body text: 16–18px, line-height 1.5–1.7
- Max line length: 65–75 characters (use `max-width: 65ch`)
- Heading line-height: 1.1–1.3
- Use `font-display: swap` for web fonts
