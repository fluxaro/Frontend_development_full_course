# Assignment — Landing Page Layout

## What You Are Building

A complete landing page layout using Tailwind's layout utilities. The page must use `container`, proper padding/margin, and demonstrate understanding of width, height, and positioning utilities.

---

## Requirements

Create `landing-layout.html` with these sections:

### 1. Fixed Navbar
- `fixed top-0 left-0 right-0` or `sticky top-0`
- `z-50` so it stays above content
- `container mx-auto px-4` inside for centered content
- Height: `h-16`

### 2. Hero Section
- `min-h-screen` so it fills the viewport
- Centered content using `flex items-center justify-center`
- `container mx-auto px-4` for the inner content
- A heading, subheading, and two buttons

### 3. Features Section
- `py-20` top and bottom padding
- `container mx-auto px-4` wrapper
- A section heading centered with `text-center mb-12`
- Three feature cards in a row using `flex gap-6` or `grid grid-cols-3 gap-6`

### 4. CTA Section
- Full-width colored background (`bg-blue-600`)
- `py-16` padding
- Centered text and a button

### 5. Footer
- `bg-gray-900 text-white`
- `py-8`
- `container mx-auto px-4` with copyright text

---

## Spacing Rules

- Use `py-20` for major section vertical padding
- Use `mb-4` for heading-to-paragraph gaps
- Use `mb-12` for section heading-to-content gaps
- Use `gap-6` between cards

---

## What Good Looks Like

- Navbar stays at the top when scrolling
- Hero fills the full viewport height
- All sections have consistent padding
- Content never touches the screen edges (always has `px-4`)
- The page looks like a real landing page

---

## Submission

Submit `landing-layout.html`.
