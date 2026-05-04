# 11 — Positioning: relative, absolute, fixed, sticky

## What Is This Lesson About?

CSS positioning lets you take elements out of the normal document flow and place them exactly where you want. Understanding the four positioning values is essential for building modals, tooltips, sticky headers, and overlays.

---

## position: static (default)

Every element is `static` by default. It follows the normal document flow.

```css
.element { position: static; } /* default — no effect */
```

---

## position: relative

Moves the element relative to its normal position. The original space is preserved.

```css
.element {
  position: relative;
  top: 20px;    /* move down 20px from normal position */
  left: 10px;   /* move right 10px from normal position */
}
```

**Key use:** Creates a positioning context for absolutely positioned children.

---

## position: absolute

Removes the element from normal flow. Positions relative to the nearest positioned ancestor (any position other than static).

```css
.parent {
  position: relative;  /* creates positioning context */
}

.child {
  position: absolute;
  top: 0;
  right: 0;
  /* positioned at top-right corner of .parent */
}
```

If no positioned ancestor exists, it positions relative to the `<html>` element.

---

## position: fixed

Removes from flow. Positions relative to the viewport. Stays in place when scrolling.

```css
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
}

.back-to-top {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
```

---

## position: sticky

Behaves like `relative` until it reaches a scroll threshold, then becomes `fixed`.

```css
.sticky-header {
  position: sticky;
  top: 0;  /* sticks when it reaches the top */
  z-index: 10;
}

.sticky-sidebar {
  position: sticky;
  top: 80px;  /* sticks 80px from top */
}
```

---

## Offset Properties

Used with positioned elements:

```css
top: 20px;      /* distance from top */
right: 20px;    /* distance from right */
bottom: 20px;   /* distance from bottom */
left: 20px;     /* distance from left */
inset: 0;       /* shorthand for all four = 0 */
```

---

## Comparison Table

| Value | In Flow | Relative To | Scrolls With Page |
|---|---|---|---|
| `static` | Yes | — | Yes |
| `relative` | Yes (space kept) | Own normal position | Yes |
| `absolute` | No | Nearest positioned ancestor | Yes |
| `fixed` | No | Viewport | No |
| `sticky` | Yes (until threshold) | Scroll container | Until threshold |

---

## Common Patterns

```css
/* Sticky navigation */
nav {
  position: sticky;
  top: 0;
  z-index: 100;
  background: white;
}

/* Overlay/modal backdrop */
.overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
  z-index: 200;
}

/* Badge on card */
.card { position: relative; }
.badge {
  position: absolute;
  top: -8px;
  right: -8px;
}

/* Centered modal */
.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 300;
}
```
