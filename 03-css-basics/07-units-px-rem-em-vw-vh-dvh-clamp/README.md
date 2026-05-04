# 07 — CSS Units: px, rem, em, vw, vh, dvh, clamp

## What Is This Lesson About?

CSS has many units for expressing sizes. Choosing the right unit is critical for responsive design, accessibility, and maintainability.

---

## Absolute Units

### px (pixels)

Fixed size — does not scale with user preferences.

```css
font-size: 16px;
border: 1px solid #ddd;
border-radius: 4px;
```

**Use for:** Borders, shadows, small fixed decorative sizes. Avoid for font sizes and layout.

---

## Relative Units

### rem (root em)

Relative to the root element's (`<html>`) font size. Default is 16px.

```css
/* If html font-size is 16px: */
font-size: 1rem;    /* = 16px */
font-size: 1.5rem;  /* = 24px */
font-size: 0.875rem;/* = 14px */
padding: 1rem;      /* = 16px */
```

**Use for:** Font sizes, spacing, layout. Scales with user's browser font size preference.

### em

Relative to the **parent element's** font size.

```css
.parent { font-size: 20px; }
.child  { font-size: 1.5em; }  /* = 30px (1.5 × 20) */
.child  { padding: 1em; }      /* = 30px (relative to own font-size) */
```

**Use for:** Padding/margin relative to the element's own font size. Careful with nesting.

### % (percentage)

Relative to the parent element's value.

```css
.container { width: 1200px; }
.child { width: 50%; }  /* = 600px */
```

---

## Viewport Units

### vw (viewport width)

1vw = 1% of the viewport width.

```css
.hero { width: 100vw; }
.sidebar { width: 25vw; }
font-size: 5vw;  /* scales with viewport */
```

### vh (viewport height)

1vh = 1% of the viewport height.

```css
.hero { height: 100vh; }
.modal { max-height: 80vh; }
```

### dvh (dynamic viewport height)

Like `vh` but accounts for mobile browser UI (address bar, etc.).

```css
.hero { height: 100dvh; }  /* correct on mobile */
```

**Use `dvh` instead of `vh` for full-screen sections on mobile.**

### svh / lvh

- `svh` — small viewport height (when browser UI is visible)
- `lvh` — large viewport height (when browser UI is hidden)

---

## The clamp() Function

`clamp(min, preferred, max)` — fluid sizing between a minimum and maximum.

```css
/* Font size: min 16px, preferred 4vw, max 32px */
font-size: clamp(1rem, 4vw, 2rem);

/* Width: min 300px, preferred 50%, max 800px */
width: clamp(300px, 50%, 800px);

/* Padding: min 16px, preferred 5vw, max 48px */
padding: clamp(1rem, 5vw, 3rem);
```

---

## When to Use Each Unit

| Unit | Use For |
|---|---|
| `px` | Borders, shadows, small fixed sizes |
| `rem` | Font sizes, spacing, layout |
| `em` | Padding/margin relative to font size |
| `%` | Widths relative to parent |
| `vw` | Full-width elements, fluid typography |
| `vh` | Full-height sections (desktop) |
| `dvh` | Full-height sections (mobile-safe) |
| `clamp()` | Fluid responsive sizing |

---

## Fluid Typography with clamp

```css
:root {
  --text-sm:   clamp(0.875rem, 1.5vw, 1rem);
  --text-base: clamp(1rem, 2vw, 1.125rem);
  --text-lg:   clamp(1.125rem, 2.5vw, 1.5rem);
  --text-xl:   clamp(1.5rem, 4vw, 2.5rem);
  --text-2xl:  clamp(2rem, 6vw, 4rem);
}
```
