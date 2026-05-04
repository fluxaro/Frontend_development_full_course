# Notes — CSS Transitions

## Quick Reference

```css
transition: property duration timing-function delay;

transition: all 0.3s ease;
transition: color 0.2s ease, background 0.2s ease;
transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
```

## Timing Functions

```css
ease          /* slow start, fast middle, slow end (default) */
linear        /* constant speed */
ease-in       /* slow start */
ease-out      /* slow end */
ease-in-out   /* slow start and end */
cubic-bezier(x1, y1, x2, y2)
steps(4)      /* stepped animation */
```

## Performant Properties

Only animate these for best performance:
- `transform` (translate, scale, rotate)
- `opacity`

Avoid animating: `width`, `height`, `top`, `left`, `margin`, `padding`

## Common Patterns

```css
/* Button hover */
.btn { transition: background 0.2s ease, transform 0.1s ease; }
.btn:hover { background: darker; transform: translateY(-2px); }

/* Card hover */
.card { transition: box-shadow 0.3s ease, transform 0.3s ease; }
.card:hover { box-shadow: 0 12px 40px rgba(0,0,0,0.2); transform: translateY(-4px); }

/* Fade in/out */
.modal { opacity: 0; transition: opacity 0.3s ease; }
.modal.open { opacity: 1; }
```
