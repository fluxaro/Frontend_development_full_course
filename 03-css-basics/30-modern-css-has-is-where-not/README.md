# 30 — Modern CSS: :has(), :is(), :where(), :not()

## What Is This Lesson About?

These four modern CSS pseudo-classes dramatically reduce the amount of CSS you need to write and enable patterns that were previously impossible without JavaScript.

---

## :is() — Group Selectors

Matches any element that matches any selector in the list. Takes the specificity of the most specific selector.

```css
/* Instead of this: */
h1, h2, h3, h4, h5, h6 { color: #2c3e50; }
article h1, article h2, article h3 { color: #3498db; }

/* Use this: */
:is(h1, h2, h3, h4, h5, h6) { color: #2c3e50; }
:is(article, section) :is(h1, h2, h3) { color: #3498db; }
```

---

## :where() — Zero Specificity

Like `:is()` but with zero specificity — easy to override.

```css
/* Zero specificity — easy to override */
:where(header, footer) a {
  color: #3498db;
}

/* This overrides :where() easily */
footer a {
  color: #666;
}
```

---

## :not() — Exclusion

Selects elements that do NOT match the selector.

```css
/* All buttons except disabled */
button:not(:disabled) { cursor: pointer; }

/* All list items except the last */
li:not(:last-child) { border-bottom: 1px solid #eee; }

/* All inputs except checkboxes and radios */
input:not([type="checkbox"]):not([type="radio"]) {
  border: 2px solid #ddd;
}
```

---

## :has() — The Parent Selector

Selects an element that contains a matching descendant. This was impossible in CSS before 2023.

```css
/* Card that contains an image */
.card:has(img) {
  padding: 0;
  overflow: hidden;
}

/* Form field that contains an invalid input */
.field:has(input:invalid) label {
  color: red;
}

/* Navigation that contains a dropdown */
nav:has(.dropdown:hover) {
  background: #2c3e50;
}

/* Article that has no images */
article:not(:has(img)) {
  max-width: 65ch;
}
```

---

## Browser Support

All four selectors are supported in all modern browsers (Chrome 105+, Firefox 121+, Safari 15.4+).

`:has()` is the newest — supported since Chrome 105 (2022) and Safari 15.4 (2022).
