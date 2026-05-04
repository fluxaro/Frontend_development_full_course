# 08 — CSS Functions: calc(), min(), max(), var()

## What Is This Lesson About?

CSS functions let you perform calculations, set dynamic values, and store reusable values directly in CSS — without JavaScript.

---

## calc()

Performs mathematical calculations. Can mix units.

```css
/* Mix units */
width: calc(100% - 40px);
height: calc(100vh - 80px);  /* full height minus nav */
padding: calc(1rem + 10px);

/* Arithmetic */
width: calc(100% / 3);
font-size: calc(1rem * 1.25);
margin: calc(var(--spacing) * 2);
```

**Operators:** `+`, `-`, `*`, `/`  
**Rule:** Always put spaces around `+` and `-`.

---

## min()

Returns the smallest value from a list.

```css
/* Width is 50% OR 600px, whichever is smaller */
width: min(50%, 600px);

/* Font size is 5vw OR 3rem, whichever is smaller */
font-size: min(5vw, 3rem);
```

**Use for:** Preventing elements from getting too large.

---

## max()

Returns the largest value from a list.

```css
/* Width is 50% OR 300px, whichever is larger */
width: max(50%, 300px);

/* Font size is 2vw OR 1rem, whichever is larger */
font-size: max(2vw, 1rem);
```

**Use for:** Ensuring a minimum size.

---

## clamp()

Combines min and max: `clamp(minimum, preferred, maximum)`.

```css
font-size: clamp(1rem, 2.5vw, 2rem);
width: clamp(300px, 50%, 800px);
padding: clamp(1rem, 5vw, 3rem);
```

---

## var() — CSS Custom Properties

Store and reuse values throughout your CSS.

```css
/* Define in :root (global) */
:root {
  --primary: #3498db;
  --spacing-sm: 0.5rem;
  --spacing-md: 1rem;
  --spacing-lg: 2rem;
  --border-radius: 8px;
}

/* Use anywhere */
.button {
  background: var(--primary);
  padding: var(--spacing-sm) var(--spacing-md);
  border-radius: var(--border-radius);
}

/* With fallback */
color: var(--text-color, #333);
```

---

## Combining Functions

```css
/* calc with var */
width: calc(100% - var(--sidebar-width));

/* clamp with calc */
font-size: clamp(1rem, calc(1rem + 1vw), 2rem);

/* min with var */
width: min(var(--max-width), 100%);
```

---

## Real-World Patterns

```css
:root {
  --nav-height: 64px;
  --sidebar-width: 280px;
  --max-content-width: 1200px;
}

/* Full height minus nav */
.main-content {
  min-height: calc(100dvh - var(--nav-height));
}

/* Sidebar layout */
.layout {
  display: grid;
  grid-template-columns: var(--sidebar-width) 1fr;
}

/* Centered container */
.container {
  width: min(var(--max-content-width), 100% - 2rem);
  margin-inline: auto;
}
```
