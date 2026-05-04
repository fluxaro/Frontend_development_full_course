# 13 — Typography: Fonts and Text Styling

## What Is This Lesson About?

Typography is one of the most impactful aspects of web design. Good typography makes content readable, establishes hierarchy, and communicates brand personality. This lesson covers everything from loading fonts to advanced text styling.

---

## Loading Fonts

### Google Fonts

```html
<!-- In <head> -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
```

```css
body { font-family: 'Inter', sans-serif; }
h1   { font-family: 'Playfair Display', serif; }
```

### @font-face (Self-hosted)

```css
@font-face {
  font-family: 'MyFont';
  src: url('fonts/myfont.woff2') format('woff2'),
       url('fonts/myfont.woff') format('woff');
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}
```

---

## Font Properties

```css
font-family: 'Inter', system-ui, sans-serif;
font-size: 1rem;
font-weight: 400;       /* 100–900 */
font-style: italic;
font-variant: small-caps;
line-height: 1.6;       /* unitless preferred */
letter-spacing: 0.05em;
word-spacing: 0.1em;
```

---

## Text Properties

```css
text-align: left | center | right | justify;
text-decoration: underline | line-through | none;
text-transform: uppercase | lowercase | capitalize;
text-indent: 2em;
text-overflow: ellipsis;
white-space: nowrap | pre | pre-wrap;
word-break: break-word;
overflow-wrap: break-word;
```

---

## Truncation with Ellipsis

```css
/* Single line truncation */
.truncate {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

/* Multi-line truncation */
.clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
```

---

## Type Scale

```css
:root {
  --text-xs:   0.75rem;   /* 12px */
  --text-sm:   0.875rem;  /* 14px */
  --text-base: 1rem;      /* 16px */
  --text-lg:   1.125rem;  /* 18px */
  --text-xl:   1.25rem;   /* 20px */
  --text-2xl:  1.5rem;    /* 24px */
  --text-3xl:  1.875rem;  /* 30px */
  --text-4xl:  2.25rem;   /* 36px */
  --text-5xl:  3rem;      /* 48px */
}
```

---

## Font Stacks

```css
/* System UI (no download needed) */
font-family: system-ui, -apple-system, sans-serif;

/* Serif */
font-family: Georgia, 'Times New Roman', serif;

/* Monospace */
font-family: 'Courier New', Courier, monospace;

/* Modern sans-serif */
font-family: 'Inter', 'Segoe UI', system-ui, sans-serif;
```
