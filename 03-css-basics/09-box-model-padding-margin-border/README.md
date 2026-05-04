# 09 — The Box Model: padding, margin, border

## What Is This Lesson About?

Every HTML element is a rectangular box. The CSS Box Model describes how that box is structured — content, padding, border, and margin. Understanding this is fundamental to controlling layout and spacing.

---

## The Box Model

```
┌─────────────────────────────────┐
│           MARGIN                │
│  ┌───────────────────────────┐  │
│  │         BORDER            │  │
│  │  ┌─────────────────────┐  │  │
│  │  │       PADDING       │  │  │
│  │  │  ┌───────────────┐  │  │  │
│  │  │  │    CONTENT    │  │  │  │
│  │  │  └───────────────┘  │  │  │
│  │  └─────────────────────┘  │  │
│  └───────────────────────────┘  │
└─────────────────────────────────┘
```

- **Content** — the actual text, image, or element
- **Padding** — space between content and border (inside the box)
- **Border** — the line around the padding and content
- **Margin** — space outside the border (between elements)

---

## box-sizing

By default, `width` and `height` only apply to the content area. Padding and border are added on top.

```css
/* Default (content-box) */
.box {
  width: 200px;
  padding: 20px;
  border: 2px solid black;
  /* Total width = 200 + 20 + 20 + 2 + 2 = 244px */
}

/* Better (border-box) */
.box {
  box-sizing: border-box;
  width: 200px;
  padding: 20px;
  border: 2px solid black;
  /* Total width = 200px (padding and border included) */
}
```

**Always use `border-box`:**

```css
*, *::before, *::after {
  box-sizing: border-box;
}
```

---

## Padding

Space inside the element, between content and border.

```css
/* All sides */
padding: 20px;

/* Vertical | Horizontal */
padding: 10px 20px;

/* Top | Horizontal | Bottom */
padding: 10px 20px 15px;

/* Top | Right | Bottom | Left (clockwise) */
padding: 10px 20px 15px 5px;

/* Individual sides */
padding-top: 10px;
padding-right: 20px;
padding-bottom: 10px;
padding-left: 20px;

/* Logical properties */
padding-block: 10px;    /* top and bottom */
padding-inline: 20px;   /* left and right */
```

---

## Margin

Space outside the element, between it and other elements.

```css
/* Same shorthand as padding */
margin: 20px;
margin: 10px 20px;
margin: 10px auto;  /* center horizontally */

/* Individual sides */
margin-top: 10px;
margin-right: auto;
margin-bottom: 10px;
margin-left: auto;

/* Logical properties */
margin-block: 20px;
margin-inline: auto;  /* center horizontally */
```

### Margin Collapse

Vertical margins between adjacent elements collapse to the larger value:

```css
.box-1 { margin-bottom: 30px; }
.box-2 { margin-top: 20px; }
/* Gap between them = 30px (not 50px) */
```

Margin collapse does NOT happen with:
- Flexbox children
- Grid children
- Floated elements
- Absolutely positioned elements

---

## Border

```css
/* Shorthand: width style color */
border: 2px solid #3498db;
border: 1px dashed #ccc;
border: 3px dotted red;

/* Individual sides */
border-top: 2px solid blue;
border-bottom: 1px solid #eee;

/* Individual properties */
border-width: 2px;
border-style: solid;
border-color: #3498db;

/* Remove border */
border: none;
border: 0;
```

### Border Styles

```css
border-style: solid;
border-style: dashed;
border-style: dotted;
border-style: double;
border-style: groove;
border-style: ridge;
border-style: inset;
border-style: outset;
border-style: none;
```

---

## outline vs border

`outline` is similar to `border` but does NOT affect layout — it does not take up space.

```css
/* Used for focus indicators */
:focus {
  outline: 2px solid #3498db;
  outline-offset: 2px;
}
```

---

## Centering with margin: auto

```css
/* Center a block element horizontally */
.container {
  width: 800px;
  margin: 0 auto;
}

/* Modern way */
.container {
  max-width: 800px;
  margin-inline: auto;
}
```
