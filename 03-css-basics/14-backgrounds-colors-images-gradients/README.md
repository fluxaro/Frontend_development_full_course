# 14 — Backgrounds: Colors, Images, and Gradients

## What Is This Lesson About?

CSS backgrounds are far more powerful than just setting a color. You can layer multiple backgrounds, create gradients, use images, and even create complex patterns — all in CSS.

---

## Background Properties

```css
background-color: #3498db;
background-image: url('image.jpg');
background-size: cover;
background-position: center;
background-repeat: no-repeat;
background-attachment: scroll;
background-clip: border-box;
background-origin: padding-box;
```

### Shorthand

```css
background: url('image.jpg') center/cover no-repeat #3498db;
/* image | position/size | repeat | color */
```

---

## background-size

```css
background-size: cover;    /* fill container, may crop */
background-size: contain;  /* fit inside, may have gaps */
background-size: 100%;     /* 100% width */
background-size: 300px 200px; /* exact size */
```

---

## Gradients

### Linear Gradient

```css
background: linear-gradient(to right, #3498db, #9b59b6);
background: linear-gradient(135deg, #667eea, #764ba2);
background: linear-gradient(to bottom, #f8f9fa, #e9ecef);
```

### Radial Gradient

```css
background: radial-gradient(circle, #3498db, #1a1a2e);
background: radial-gradient(ellipse at top, #3498db, transparent);
```

### Conic Gradient

```css
background: conic-gradient(from 0deg, red, yellow, green, red);
background: conic-gradient(from 90deg at 50% 50%, #f093fb, #f5576c, #4facfe);
```

### Repeating Gradients

```css
background: repeating-linear-gradient(
  45deg,
  #f0f0f0 0px, #f0f0f0 10px,
  white 10px, white 20px
);
```

---

## Multiple Backgrounds

```css
/* Overlay + image */
background:
  linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
  url('hero.jpg') center/cover no-repeat;

/* Pattern + color */
background:
  radial-gradient(circle, #3498db 1px, transparent 1px),
  #1a1a2e;
background-size: 20px 20px, auto;
```

---

## Gradient Text

```css
.gradient-text {
  background: linear-gradient(to right, #f093fb, #f5576c);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

---

## CSS Patterns

```css
/* Diagonal stripes */
background: repeating-linear-gradient(
  -45deg, #3498db 0px, #3498db 10px, #2980b9 10px, #2980b9 20px
);

/* Dots */
background-image: radial-gradient(circle, #3498db 1px, transparent 1px);
background-size: 20px 20px;

/* Grid */
background-image:
  linear-gradient(rgba(0,0,0,0.1) 1px, transparent 1px),
  linear-gradient(90deg, rgba(0,0,0,0.1) 1px, transparent 1px);
background-size: 20px 20px;
```
