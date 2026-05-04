# Notes — Utility-First Philosophy

## Quick Reference

```html
<!-- Utility-first: compose styles from small classes -->
<button class="bg-blue-600 text-white font-semibold px-4 py-2 rounded-lg hover:bg-blue-700 transition-colors">
  Click Me
</button>

<!-- vs. semantic CSS approach -->
<button class="btn btn-primary">Click Me</button>
/* .btn { padding: 0.5rem 1rem; border-radius: 0.5rem; font-weight: 600; }
   .btn-primary { background: #2563eb; color: white; } */
```

## What "Utility-First" Means

A utility class does **one thing only**. You compose many small classes to build a design, rather than writing one big class that bundles many styles together.

| Utility class | What it does |
|---|---|
| `text-lg` | `font-size: 1.125rem` |
| `font-bold` | `font-weight: 700` |
| `text-gray-700` | `color: #374151` |
| `p-4` | `padding: 1rem` |
| `mt-6` | `margin-top: 1.5rem` |
| `rounded-md` | `border-radius: 0.375rem` |
| `shadow` | adds a small box-shadow |
| `flex` | `display: flex` |

## Utility-First vs Component-Based CSS

**Semantic / component CSS** (BEM, Bootstrap):
- You name components (`.card`, `.btn-primary`)
- Styles are in a separate file
- Reuse by applying the class name

**Utility-first** (Tailwind):
- No naming required
- Styles live in the HTML
- Reuse by copying the class string, or extracting a component in your framework

## Why It Works

- **No dead CSS** — you only write what you use
- **No specificity battles** — each class targets one property
- **Faster iteration** — change a value by changing a class, not hunting through a CSS file
- **Consistent design** — all values come from a design scale (spacing, colors, type)

## Common Mistakes

- Writing custom CSS for things Tailwind already handles (padding, color, flex)
- Trying to keep class lists short — long class lists are normal and expected in Tailwind
- Mixing Tailwind utilities with a separate CSS file for the same elements (causes confusion)
- Forgetting that utility classes are just CSS — you can always inspect them in DevTools
