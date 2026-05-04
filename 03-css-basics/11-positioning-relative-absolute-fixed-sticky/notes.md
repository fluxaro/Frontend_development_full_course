# Notes — CSS Positioning

## Quick Reference

| Value | In Flow | Positioned Relative To |
|---|---|---|
| `static` | Yes | Normal flow |
| `relative` | Yes | Own position |
| `absolute` | No | Nearest positioned ancestor |
| `fixed` | No | Viewport |
| `sticky` | Yes | Scroll container |

## Offset Properties

```css
top: 0;
right: 0;
bottom: 0;
left: 0;
inset: 0;  /* shorthand for all four */
```

## Common Patterns

```css
/* Sticky nav */
nav { position: sticky; top: 0; z-index: 100; }

/* Absolute badge on card */
.card { position: relative; }
.badge { position: absolute; top: -8px; right: -8px; }

/* Fixed overlay */
.overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.5); }

/* Centered modal */
.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* Full-cover pseudo-element */
.card::after {
  content: '';
  position: absolute;
  inset: 0;
}
```

## Common Mistakes

- Forgetting `position: relative` on parent when using `position: absolute` on child
- Using `position: fixed` for sticky headers (breaks on mobile scroll)
- Not adding `z-index` to fixed/sticky elements (they go behind other content)
- Using `top/left` on `position: static` (has no effect)
