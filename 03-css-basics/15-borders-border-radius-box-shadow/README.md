# 15 — Borders, Border-radius, and Box-shadow

## What Is This Lesson About?

Borders, border-radius, and box-shadow are the three properties that give elements their visual shape and depth. Together they create cards, buttons, modals, and almost every UI component you see on the web.

---

## Borders

```css
/* Shorthand */
border: 2px solid #3498db;

/* Individual sides */
border-top: 4px solid #e74c3c;
border-right: 1px solid #ddd;
border-bottom: 2px dashed #27ae60;
border-left: 4px solid #3498db;

/* Individual properties */
border-width: 2px;
border-style: solid;
border-color: #3498db;
```

### Border Styles

`solid`, `dashed`, `dotted`, `double`, `groove`, `ridge`, `inset`, `outset`, `none`

---

## Border Radius

```css
border-radius: 8px;           /* all corners */
border-radius: 8px 0;         /* top-left/bottom-right | top-right/bottom-left */
border-radius: 8px 0 8px 0;   /* top-left | top-right | bottom-right | bottom-left */

border-radius: 50%;            /* circle (on square element) */
border-radius: 9999px;         /* pill shape */

/* Individual corners */
border-top-left-radius: 8px;
border-top-right-radius: 0;
border-bottom-right-radius: 8px;
border-bottom-left-radius: 0;
```

---

## Box Shadow

```css
/* Syntax: offset-x offset-y blur spread color */
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);

/* Inset shadow */
box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.15);

/* Multiple shadows */
box-shadow:
  0 1px 3px rgba(0, 0, 0, 0.1),
  0 8px 24px rgba(0, 0, 0, 0.1);

/* Colored shadow */
box-shadow: 0 8px 24px rgba(52, 152, 219, 0.4);
```

---

## Shadow Scale

```css
:root {
  --shadow-sm: 0 1px 3px rgba(0,0,0,0.1);
  --shadow-md: 0 4px 12px rgba(0,0,0,0.1);
  --shadow-lg: 0 8px 24px rgba(0,0,0,0.15);
  --shadow-xl: 0 20px 60px rgba(0,0,0,0.2);
}
```

---

## Glass Effect

```css
.glass-card {
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
}
```

---

## Hover Shadow Effect

```css
.card {
  box-shadow: var(--shadow-sm);
  transition: box-shadow 0.3s, transform 0.3s;
}

.card:hover {
  box-shadow: var(--shadow-xl);
  transform: translateY(-4px);
}
```
