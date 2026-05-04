# 12 — z-index and Stacking Context

## What Is This Lesson About?

When elements overlap, CSS needs to decide which one appears on top. `z-index` controls this stacking order, but it only works within a stacking context — and understanding stacking contexts is what separates developers who fight with z-index from those who understand it.

---

## z-index Basics

`z-index` controls the stacking order of positioned elements. Higher values appear on top.

```css
.modal    { z-index: 1000; }
.overlay  { z-index: 999; }
.dropdown { z-index: 100; }
.navbar   { z-index: 50; }
.card     { z-index: 1; }
```

**z-index only works on positioned elements** (position: relative, absolute, fixed, or sticky).

---

## Stacking Context

A stacking context is an isolated group of elements that stack together. Elements inside a stacking context are stacked relative to each other, not to the rest of the page.

### What Creates a Stacking Context

```css
/* These all create a new stacking context */
position: relative/absolute/fixed/sticky + z-index (not auto)
opacity: less than 1
transform: any value
filter: any value
will-change: transform/opacity
isolation: isolate
```

---

## The z-index Scale

Use a consistent scale to avoid conflicts:

```css
:root {
  --z-below:    -1;
  --z-base:      0;
  --z-raised:    1;
  --z-dropdown: 100;
  --z-sticky:   200;
  --z-overlay:  300;
  --z-modal:    400;
  --z-toast:    500;
}
```

---

## isolation: isolate

Creates a stacking context without changing any visual properties. Useful for containing z-index within a component.

```css
.card {
  isolation: isolate;  /* z-index values inside won't escape */
}
```

---

## Common Mistakes

- Using `z-index` on `position: static` elements (has no effect)
- Using huge z-index values (9999, 99999) — use a scale instead
- Not understanding that z-index is relative to the stacking context
- Forgetting that `opacity < 1` creates a stacking context
