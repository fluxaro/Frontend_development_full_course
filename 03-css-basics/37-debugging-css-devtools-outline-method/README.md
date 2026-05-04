# 37 — Debugging CSS: DevTools and the Outline Method

## What Is This Lesson About?

CSS bugs are inevitable. This lesson teaches you systematic debugging techniques using browser DevTools and the outline method.

---

## The Outline Method

The fastest way to debug layout issues:

```css
/* See all element boxes */
* { outline: 1px solid red; }

/* See specific elements */
.card { outline: 2px solid blue; }
.navbar { outline: 2px solid green; }
```

Unlike `border`, `outline` does not affect layout — it does not take up space.

---

## DevTools Workflow

1. **Right-click** the element → **Inspect**
2. **Styles panel** — see all CSS rules applied, in order of specificity
3. **Computed panel** — see the final computed value for any property
4. **Layout panel** — see the box model (margin, border, padding, content)
5. **Toggle rules** — click the checkbox next to any rule to disable it

---

## Common CSS Bugs

### Bug: Element wider than expected

```css
/* Problem */
.card { width: 50%; padding: 20px; }
/* Total width = 50% + 40px (padding) */

/* Fix */
*, *::before, *::after { box-sizing: border-box; }
.card { width: 50%; padding: 20px; }
/* Total width = 50% (padding included) */
```

### Bug: Image has gap below it

```css
/* Problem: images are inline by default */
img { width: 100%; }

/* Fix: make image block */
img { width: 100%; display: block; }
```

### Bug: z-index not working

```css
/* Problem: z-index only works on positioned elements */
.badge { z-index: 10; }  /* no effect */

/* Fix: add position */
.badge { position: relative; z-index: 10; }
```

### Bug: Margin not working as expected

```css
/* Problem: vertical margins collapse */
.box-1 { margin-bottom: 30px; }
.box-2 { margin-top: 20px; }
/* Gap = 30px, not 50px */

/* Fix: use flex/grid or padding instead */
.container { display: flex; flex-direction: column; gap: 30px; }
```

---

## DevTools Tips

- **Ctrl+Shift+C** — click to inspect any element
- **Ctrl+Shift+M** — toggle device/responsive mode
- **Ctrl+Z** in DevTools — undo style changes
- **Copy element** — right-click → Copy → Copy element
- **Force state** — right-click element → Force state → :hover/:focus/:active
