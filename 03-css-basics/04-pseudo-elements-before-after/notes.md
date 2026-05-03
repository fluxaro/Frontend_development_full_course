# Notes — Pseudo-elements ::before and ::after

## Quick Reference

```css
/* Insert before element */
.element::before {
  content: '';
  display: block;
  /* styles */
}

/* Insert after element */
.element::after {
  content: '';
  display: block;
  /* styles */
}
```

## content Property Values

```css
content: '';              /* empty (decoration) */
content: '★';             /* text */
content: ' ↗';            /* icon/symbol */
content: attr(data-tip);  /* HTML attribute value */
content: counter(item);   /* CSS counter */
```

## Common Patterns

```css
/* Underline decoration */
h2::after {
  content: '';
  display: block;
  width: 50px;
  height: 3px;
  background: #3498db;
  margin-top: 8px;
}

/* Required asterisk */
label.required::after {
  content: ' *';
  color: red;
}

/* External link arrow */
a[target="_blank"]::after {
  content: ' ↗';
  font-size: 0.8em;
}

/* Custom bullet */
li::before {
  content: '→ ';
  color: #3498db;
}

/* Tooltip */
[data-tooltip]:hover::after {
  content: attr(data-tooltip);
  position: absolute;
  background: #333;
  color: white;
  padding: 4px 8px;
  border-radius: 4px;
}
```

## Rules to Remember

- `content` is REQUIRED — without it nothing renders
- Pseudo-elements are inline by default
- Not in the DOM — JS cannot select them
- One `::before` and one `::after` per element
- Use `position: absolute` on the pseudo-element + `position: relative` on parent for precise placement

## Common Mistakes

- Forgetting `content: ''` (nothing renders)
- Forgetting `position: relative` on parent when using `position: absolute` on pseudo-element
- Trying to select pseudo-elements with JavaScript (not possible)
- Using single colon `:before` (works but `::before` is correct modern syntax)
