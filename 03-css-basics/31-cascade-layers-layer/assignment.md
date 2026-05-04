# Assignment — Design System with Cascade Layers

## What You Are Building

Refactor a design system to use cascade layers for clean style management.

---

## Requirements

Create `layered-design-system.html` and `layered-design-system.css` with:

### Layer Stack

```css
@layer reset, tokens, base, components, utilities;
```

### Each Layer

- **reset** — box-sizing, margin, padding reset
- **tokens** — CSS custom properties
- **base** — body, typography, links
- **components** — buttons, cards, forms, navigation
- **utilities** — spacing, display, color utilities

### Demonstrate Layer Priority

Show that a utility class overrides a component style even with lower specificity.

---

## Submission

Submit `layered-design-system.html` and `layered-design-system.css`.
