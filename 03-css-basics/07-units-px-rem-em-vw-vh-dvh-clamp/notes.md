# Notes — CSS Units

## Quick Reference

| Unit | Relative To | Example |
|---|---|---|
| `px` | Fixed | `border: 1px` |
| `rem` | Root font-size (16px) | `font-size: 1.5rem` |
| `em` | Parent font-size | `padding: 1em` |
| `%` | Parent value | `width: 50%` |
| `vw` | Viewport width | `width: 100vw` |
| `vh` | Viewport height | `height: 100vh` |
| `dvh` | Dynamic viewport height | `height: 100dvh` |
| `ch` | Width of "0" character | `max-width: 65ch` |
| `fr` | Fraction of grid | `grid-template-columns: 1fr 2fr` |

## rem Conversion (base 16px)

| rem | px |
|---|---|
| 0.75rem | 12px |
| 0.875rem | 14px |
| 1rem | 16px |
| 1.125rem | 18px |
| 1.25rem | 20px |
| 1.5rem | 24px |
| 2rem | 32px |
| 3rem | 48px |

## clamp() Pattern

```css
clamp(minimum, preferred, maximum)

font-size: clamp(1rem, 2.5vw, 2rem);
padding:   clamp(1rem, 5vw, 3rem);
width:     clamp(300px, 50%, 800px);
```

## Common Mistakes

- Using `px` for font sizes (breaks user accessibility settings)
- Using `vh` on mobile (browser UI causes layout issues — use `dvh`)
- Nesting `em` units (compounds: 1.2em inside 1.2em = 1.44em)
- Using `vw` for font sizes without `clamp` (can get too small/large)
