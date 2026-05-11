# Assignment — Responsive Landing Page

## What You Are Building

A fully responsive landing page that adapts from a single-column mobile layout to a multi-column desktop layout — using only Tailwind responsive prefixes.

---

## Requirements

Create `responsive-landing.html` with the Tailwind CDN.

### Navbar
- [ ] On mobile: logo only + hamburger icon (no links visible)
- [ ] On `md:` and above: logo + nav links + CTA button all in one row
- [ ] Use `hidden md:flex` for the nav links and `md:hidden` for the hamburger

### Hero Section
- [ ] On mobile: single column, text centered, stacked vertically
- [ ] On `md:` and above: two columns side by side (`flex-col md:flex-row`)
- [ ] Heading: `text-3xl sm:text-4xl md:text-5xl lg:text-6xl`
- [ ] Padding: `px-4 md:px-8 lg:px-16 py-12 md:py-20 lg:py-28`

### Features Section
- [ ] On mobile: 1 column
- [ ] On `sm:`: 2 columns
- [ ] On `lg:`: 3 columns
- [ ] Use `grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3`

### Testimonials Section
- [ ] On mobile: 1 column
- [ ] On `md:`: 2 columns
- [ ] On `xl:`: 3 columns

### Footer
- [ ] On mobile: stacked vertically, centered
- [ ] On `md:`: two columns (logo/description left, links right)
- [ ] On `lg:`: four columns

### Breakpoint Indicator
- [ ] Include the dev breakpoint indicator in the bottom-right corner

---

## What Good Looks Like

- The page looks great at every breakpoint — not just desktop
- No horizontal scrollbar at any viewport width
- Text sizes scale appropriately — not too small on mobile, not too large on desktop
- The navbar hamburger is visible on mobile, hidden on desktop
- The footer columns collapse gracefully on small screens

---

## Submission

Submit `responsive-landing.html`. Test it by resizing the browser window through all breakpoints and confirm each section adapts correctly.
