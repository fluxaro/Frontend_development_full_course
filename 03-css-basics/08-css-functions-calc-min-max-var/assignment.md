# Assignment — Complete Design Token System

## What You Are Building

Create a production-ready design token system and apply it to a complete landing page.

---

## Requirements

### Design Tokens File (`tokens.css`)

Define custom properties for:
- **Colors** — primary (9 shades), secondary (9 shades), neutrals (9 shades), semantic (success, warning, danger, info)
- **Typography** — font families, 8 size steps, line heights, font weights
- **Spacing** — 12 spacing steps (space-1 through space-16)
- **Layout** — nav height, sidebar width, max widths, border radii
- **Shadows** — 4 shadow levels
- **Transitions** — duration and easing values

### Landing Page

Apply your tokens to a complete landing page with:
- Navigation bar (height from token)
- Hero section (full dvh, fluid heading with clamp)
- Features section (3-column grid)
- Pricing section (3 pricing cards)
- Footer

### CSS Functions Required

- `calc()` — at least 3 uses
- `min()` — container width pattern
- `max()` — at least 1 use
- `clamp()` — fluid typography
- `var()` — everywhere

---

## What Good Looks Like

- Zero hardcoded values in component CSS — only `var()` references
- Changing one token updates the whole page
- The page looks professional and polished
- All CSS functions are used correctly

---

## Submission

Submit `tokens.css`, `landing-page.html`, and `landing-page.css`.
