# Assignment — Fluid Responsive Layout

## What You Are Building

Create a fully fluid responsive layout using only relative units — no fixed pixel widths for layout.

---

## Requirements

### Typography Scale

Define a complete type scale using `clamp()`:
- `--text-xs` through `--text-5xl`
- Each size must be fluid (scales between min and max)
- Apply to a sample article page

### Layout

Create a page layout using:
- `rem` for all spacing (padding, margin, gap)
- `%` or `fr` for widths
- `dvh` for the hero section height
- `ch` for max-width of text content (65ch is ideal for readability)
- `clamp()` for the hero font size

### Components

Build these components using appropriate units:
1. **Hero section** — `100dvh`, fluid heading with `clamp()`
2. **Card grid** — widths in `%` or `fr`
3. **Sidebar layout** — sidebar in `rem`, main content in `fr`
4. **Navigation** — padding in `em`, font-size in `rem`

---

## What Good Looks Like

- No `px` values for font sizes or layout widths
- Text is readable at all viewport sizes
- The hero is exactly full-screen on mobile (no overflow from browser UI)
- Spacing scales proportionally

---

## Submission

Submit `fluid-layout.html` and `fluid-layout.css`.
