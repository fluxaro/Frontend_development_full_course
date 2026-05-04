# Notes — Borders, Border-radius, Box-shadow

## Border Cheat Sheet

```css
border: 2px solid #3498db;
border-top: 4px solid red;
border-radius: 8px;
border-radius: 50%;          /* circle */
border-radius: 9999px;       /* pill */
border-radius: 0 8px 8px 0;  /* right side only */
```

## Box-shadow Syntax

```css
box-shadow: offset-x offset-y blur spread color;
box-shadow: 0 4px 12px rgba(0,0,0,0.1);
box-shadow: inset 0 2px 8px rgba(0,0,0,0.15);
box-shadow: 0 4px 12px rgba(0,0,0,0.1), 0 1px 3px rgba(0,0,0,0.05);
```

## Shadow Scale

```css
--shadow-sm: 0 1px 3px rgba(0,0,0,0.1);
--shadow-md: 0 4px 12px rgba(0,0,0,0.1);
--shadow-lg: 0 8px 24px rgba(0,0,0,0.15);
--shadow-xl: 0 20px 60px rgba(0,0,0,0.2);
```

## Glass Effect

```css
.glass {
  background: rgba(255,255,255,0.2);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255,255,255,0.3);
}
```

## Common Mistakes

- Using `border-radius: 50%` on non-square elements (creates ellipse, not circle)
- Forgetting that `box-shadow` does not affect layout
- Using too many shadows (performance)
- Not using `outline` for focus states (use `outline`, not `box-shadow` for accessibility)
