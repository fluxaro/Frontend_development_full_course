# 04 — Pseudo-elements: ::before and ::after

## What Is This Lesson About?

Pseudo-elements let you insert virtual elements into the DOM using only CSS — no extra HTML needed. `::before` and `::after` are the most commonly used and are essential for decorative effects, icons, and UI patterns.

---

## What Are Pseudo-elements?

A pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element, or insert content before/after it.

```css
selector::pseudo-element {
  content: '';
  /* styles */
}
```

The double colon `::` distinguishes pseudo-elements from pseudo-classes (`:`). Single colon `:before` still works but `::before` is the modern standard.

---

## ::before and ::after

`::before` inserts a virtual element as the **first child** of the selected element.  
`::after` inserts a virtual element as the **last child** of the selected element.

**The `content` property is required.** Without it, the pseudo-element will not render.

```css
.card::before {
  content: '';        /* empty string — just for decoration */
}

.label::before {
  content: '★ ';     /* text content */
}

.external-link::after {
  content: ' ↗';     /* arrow after external links */
}
```

---

## Common Use Cases

### 1. Decorative Lines

```css
h2 {
  position: relative;
  padding-bottom: 12px;
}

h2::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 60px;
  height: 3px;
  background-color: #3498db;
}
```

### 2. Quote Marks on Blockquotes

```css
blockquote {
  position: relative;
  padding: 20px 20px 20px 60px;
  font-style: italic;
}

blockquote::before {
  content: '"';
  position: absolute;
  left: 10px;
  top: -10px;
  font-size: 5rem;
  color: #3498db;
  line-height: 1;
}
```

### 3. Required Field Asterisk

```css
label.required::after {
  content: ' *';
  color: #e74c3c;
}
```

### 4. Clearfix (Legacy)

```css
.clearfix::after {
  content: '';
  display: table;
  clear: both;
}
```

### 5. Tooltip

```css
[data-tooltip] {
  position: relative;
}

[data-tooltip]::after {
  content: attr(data-tooltip);
  position: absolute;
  bottom: 100%;
  left: 50%;
  transform: translateX(-50%);
  background: #333;
  color: white;
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 0.8rem;
  white-space: nowrap;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.2s;
}

[data-tooltip]:hover::after {
  opacity: 1;
}
```

### 6. Custom List Bullets

```css
ul.custom-list {
  list-style: none;
  padding: 0;
}

ul.custom-list li {
  position: relative;
  padding-left: 24px;
}

ul.custom-list li::before {
  content: '→';
  position: absolute;
  left: 0;
  color: #3498db;
}
```

### 7. Overlay on Images

```css
.card {
  position: relative;
  overflow: hidden;
}

.card::after {
  content: '';
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0);
  transition: background 0.3s;
}

.card:hover::after {
  background: rgba(0, 0, 0, 0.4);
}
```

---

## The `content` Property Values

```css
content: '';                    /* empty — for decoration */
content: 'text';                /* literal text */
content: attr(data-label);      /* value of an HTML attribute */
content: counter(section);      /* CSS counter */
content: url('icon.svg');       /* image */
content: open-quote;            /* language-appropriate quote */
content: close-quote;
```

---

## Key Rules

1. `content` property is **required** — without it, nothing renders
2. Pseudo-elements are **inline** by default — add `display: block` or `position: absolute` as needed
3. They are **not in the DOM** — JavaScript cannot select them
4. They inherit styles from their parent element
5. You can only have **one** `::before` and **one** `::after` per element
