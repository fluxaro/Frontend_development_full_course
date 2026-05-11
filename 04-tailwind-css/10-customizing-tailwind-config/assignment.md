# Assignment — Branded Design System

## What You Are Building

A branded landing page that uses a custom Tailwind config to define a complete design system — custom colors, fonts, spacing, shadows, and animations — all via the CDN config approach.

---

## Requirements

Create `branded-page.html` with the Tailwind CDN and a custom config block.

### Custom Config (required)
- [ ] Define a `primary` color with at least 5 shades (50, 100, 500, 600, 900)
- [ ] Define a `secondary` color with at least 3 shades
- [ ] Define at least 2 semantic colors: `success`, `warning`, or `danger`
- [ ] Define a custom `fontFamily` for `display` (use a Google Font via `<link>`)
- [ ] Define at least 2 custom spacing values (e.g., `'18': '4.5rem'`)
- [ ] Define at least 1 custom shadow (e.g., `glow` or `card`)
- [ ] Define at least 1 custom animation with keyframes

### Page Content (use your custom config throughout)
- [ ] A navbar using `bg-primary-900` or similar
- [ ] A hero section with a `bg-primary-600` or gradient using your custom colors
- [ ] At least 3 feature cards using `bg-primary-50`, `text-primary-600`, etc.
- [ ] A CTA section using your `secondary` color
- [ ] At least one element using your custom `font-display`
- [ ] At least one element using your custom shadow
- [ ] At least one element using your custom animation

### Design Requirements
- [ ] The page has a consistent color palette — everything uses your custom colors, not Tailwind defaults
- [ ] The brand feels cohesive — colors, fonts, and spacing work together

---

## What Good Looks Like

- The config block defines a real design system, not just one color
- Every section uses the custom colors — no `bg-blue-600` or `text-gray-900` from the defaults
- The custom font is visibly different from the default sans-serif
- The custom animation plays on page load or hover
- The page looks like a real branded product, not a generic template

---

## Submission

Submit `branded-page.html`. Open it in a browser and confirm:
1. The custom colors are applied throughout
2. The custom font is loading and visible
3. The custom animation plays
