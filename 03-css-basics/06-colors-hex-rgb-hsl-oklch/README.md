# 06 — Colors: hex, rgb, hsl, oklch

## What Is This Lesson About?

CSS supports multiple color formats. Understanding each format helps you choose the right one for different situations — and modern formats like `oklch` give you perceptually uniform color manipulation.

---

## Color Formats

### Named Colors

```css
color: red;
color: blue;
color: tomato;
color: cornflowerblue;
```

147 named colors exist. Good for quick prototyping, not for production.

### Hex

```css
color: #ff0000;    /* red */
color: #00ff00;    /* green */
color: #0000ff;    /* blue */
color: #ffffff;    /* white */
color: #000000;    /* black */
color: #3498db;    /* a nice blue */

/* Shorthand (when pairs repeat) */
color: #fff;       /* = #ffffff */
color: #f00;       /* = #ff0000 */

/* With alpha (transparency) */
color: #3498dbcc;  /* 80% opacity */
```

### RGB

```css
color: rgb(52, 152, 219);           /* r, g, b — 0 to 255 */
color: rgba(52, 152, 219, 0.8);     /* with alpha 0–1 */

/* Modern syntax */
color: rgb(52 152 219);             /* no commas */
color: rgb(52 152 219 / 80%);       /* with alpha */
```

### HSL

HSL stands for Hue, Saturation, Lightness. It is much more intuitive for creating color variations.

```css
color: hsl(204, 70%, 53%);          /* hue, saturation, lightness */
color: hsla(204, 70%, 53%, 0.8);    /* with alpha */

/* Modern syntax */
color: hsl(204 70% 53%);
color: hsl(204 70% 53% / 80%);
```

- **Hue** — 0–360 degrees on the color wheel (0=red, 120=green, 240=blue)
- **Saturation** — 0% (gray) to 100% (vivid)
- **Lightness** — 0% (black) to 100% (white), 50% = normal

### oklch (Modern — 2023+)

oklch is a perceptually uniform color space. When you change lightness, the perceived brightness actually changes uniformly.

```css
color: oklch(0.65 0.15 230);        /* lightness, chroma, hue */
color: oklch(65% 0.15 230);         /* lightness as percentage */
color: oklch(0.65 0.15 230 / 80%);  /* with alpha */
```

- **Lightness** — 0 (black) to 1 (white)
- **Chroma** — 0 (gray) to ~0.4 (vivid)
- **Hue** — 0–360 degrees

---

## When to Use Each Format

| Format | Use When |
|---|---|
| Named | Quick prototyping, learning |
| Hex | Design tokens, copying from design tools |
| RGB | When you need to manipulate channels in JS |
| HSL | Creating color variations, themes |
| oklch | Modern projects, design systems, accessible palettes |

---

## Creating Color Palettes with HSL

HSL makes it easy to create consistent color palettes:

```css
:root {
  --primary-100: hsl(204, 70%, 95%);
  --primary-200: hsl(204, 70%, 85%);
  --primary-300: hsl(204, 70%, 70%);
  --primary-400: hsl(204, 70%, 60%);
  --primary-500: hsl(204, 70%, 53%);  /* base */
  --primary-600: hsl(204, 70%, 43%);
  --primary-700: hsl(204, 70%, 33%);
  --primary-800: hsl(204, 70%, 23%);
  --primary-900: hsl(204, 70%, 13%);
}
```

Only the lightness changes — the hue and saturation stay the same.

---

## Transparency

```css
/* All formats support transparency */
color: #3498db80;                    /* hex with alpha */
color: rgb(52 152 219 / 50%);        /* rgb with alpha */
color: hsl(204 70% 53% / 50%);       /* hsl with alpha */
color: oklch(0.65 0.15 230 / 50%);   /* oklch with alpha */
```

---

## currentColor

```css
.icon {
  color: #3498db;
  border: 2px solid currentColor;  /* uses the same blue */
}
```

`currentColor` uses the element's current `color` value.
