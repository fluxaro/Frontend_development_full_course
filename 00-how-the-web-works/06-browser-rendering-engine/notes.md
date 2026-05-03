# Notes — Browser Rendering Engine

## The Critical Rendering Path (6 Steps)

```
HTML → DOM
CSS  → CSSOM
         ↓
    Render Tree
         ↓
      Layout
         ↓
       Paint
         ↓
     Composite
```

## Quick Reference

| Step | What Happens | Triggered By |
|---|---|---|
| Parse HTML | Build DOM tree | Receiving HTML bytes |
| Parse CSS | Build CSSOM tree | CSS files loading |
| Render Tree | Combine DOM + CSSOM | Both trees ready |
| Layout | Calculate positions/sizes | DOM/CSS changes |
| Paint | Draw pixels | Layout changes |
| Composite | Combine layers | Paint complete |

## CSS Property Cost

| Property | Layout | Paint | Composite |
|---|---|---|---|
| width, height | ✅ | ✅ | ✅ |
| top, left, margin | ✅ | ✅ | ✅ |
| color, background | ❌ | ✅ | ✅ |
| border-radius, box-shadow | ❌ | ✅ | ✅ |
| transform | ❌ | ❌ | ✅ |
| opacity | ❌ | ❌ | ✅ |

**Rule:** Use `transform` and `opacity` for animations — they are the cheapest.

## Key Terms

- **DOM** — Tree of HTML elements the browser builds from your HTML
- **CSSOM** — Tree of CSS rules the browser builds from your CSS
- **Render Tree** — DOM + CSSOM combined, only visible elements
- **Layout / Reflow** — Calculating where everything goes on screen
- **Paint** — Drawing the actual pixels
- **Composite** — Combining layers into the final image
- **Render-blocking** — CSS and sync JS that delay the first render
- **TTFB** — Time to First Byte — how long before the server starts responding

## Common Mistakes

- Placing `<script>` in `<head>` without `defer` — blocks HTML parsing
- Animating `width`/`height` instead of `transform: scale()` — causes layout thrash
- Not using `will-change` on elements you know will animate
- Loading large CSS files that block rendering

## DevTools Tips

- **Performance tab** — Record page load to see rendering timeline
- **Rendering tab** (in DevTools More Tools) — Enable "Paint flashing" to see what repaints
- **Layers panel** — See how the browser splits your page into layers
