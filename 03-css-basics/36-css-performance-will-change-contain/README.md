# 36 — CSS Performance: will-change and contain

## What Is This Lesson About?

CSS can cause performance issues if used incorrectly. This lesson covers the CSS properties that help the browser optimize rendering: `will-change`, `contain`, and `content-visibility`.

---

## The Rendering Pipeline

When CSS changes, the browser may need to:
1. **Layout** — recalculate positions and sizes (expensive)
2. **Paint** — redraw pixels (medium)
3. **Composite** — combine layers (cheap)

**Goal:** Keep animations in the composite step only.

---

## will-change

Tells the browser to prepare for an upcoming change, creating a new compositing layer.

```css
/* Good: only when needed */
.card:hover {
  will-change: transform;
}

/* Bad: always on (wastes GPU memory) */
.card {
  will-change: transform; /* Don't do this */
}
```

**Use sparingly.** Each `will-change` creates a GPU layer. Too many layers = more memory usage.

---

## contain

Tells the browser that an element's subtree is independent from the rest of the page.

```css
.card {
  contain: content;  /* layout + paint + style */
}

.sidebar {
  contain: layout;   /* layout only */
}
```

**Benefits:** The browser can skip recalculating the rest of the page when this element changes.

---

## content-visibility

Skips rendering of off-screen elements entirely.

```css
.list-item {
  content-visibility: auto;
  contain-intrinsic-size: 0 80px;  /* estimated height */
}
```

**Use for:** Long lists, infinite scroll, off-screen sections.

---

## Performance Rules

1. **Animate only `transform` and `opacity`** — they skip layout and paint
2. **Use `will-change` sparingly** — only when you know an animation is coming
3. **Use `contain: content`** on independent components
4. **Use `content-visibility: auto`** for long lists
5. **Avoid animating** `width`, `height`, `top`, `left`, `margin`, `padding`
