# Notes — CSS Colors

## Format Quick Reference

```css
/* Named */
color: tomato;

/* Hex */
color: #3498db;
color: #3498dbcc;  /* with alpha */

/* RGB */
color: rgb(52 152 219);
color: rgb(52 152 219 / 80%);

/* HSL */
color: hsl(204 70% 53%);
color: hsl(204 70% 53% / 80%);

/* oklch (modern) */
color: oklch(0.65 0.15 230);
color: oklch(0.65 0.15 230 / 80%);
```

## HSL Color Wheel

| Hue | Color |
|---|---|
| 0 / 360 | Red |
| 30 | Orange |
| 60 | Yellow |
| 120 | Green |
| 180 | Cyan |
| 240 | Blue |
| 270 | Purple |
| 300 | Magenta |

## HSL Palette Pattern

```css
/* Same hue, vary lightness */
--color-100: hsl(204 70% 95%);  /* lightest */
--color-500: hsl(204 70% 53%);  /* base */
--color-900: hsl(204 70% 13%);  /* darkest */
```

## Common Colors in Hex

```
#ffffff  white
#000000  black
#f8f9fa  light gray
#6c757d  medium gray
#343a40  dark gray
#007bff  blue
#28a745  green
#dc3545  red
#ffc107  yellow
#17a2b8  teal
```

## Common Mistakes

- Using `rgba()` when `rgb()` with `/` syntax is cleaner
- Not using HSL for color variations (much easier than hex)
- Forgetting that oklch requires modern browsers (2023+)
- Using opacity on the whole element when you only want transparent background
