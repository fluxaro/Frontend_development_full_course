# Assignment — Photo Gallery & Magazine Layout

## What You Are Building

A page with two grid layouts: a responsive photo gallery and a magazine-style editorial layout with a featured article spanning multiple cells.

---

## Requirements

Create `photo-gallery.html` with:

### Section 1 — Responsive Photo Gallery
- Grid: `grid-cols-2 md:grid-cols-3 lg:grid-cols-4`
- `gap-3` between images
- Each image: `aspect-square object-cover rounded-xl`
- At least 8 images (use gradient divs as placeholders if no images)
- A heading above the gallery

### Section 2 — Magazine Layout
- Grid: `grid-cols-3 grid-rows-2` with a fixed height (`h-96`)
- Featured article: `col-span-2 row-span-2` (takes up 2/3 of the grid)
- Two smaller articles filling the remaining cells
- Each cell has a gradient background, title, and category tag
- The featured article has a larger title

### Section 3 — Stats Dashboard
- Grid: `grid-cols-2 lg:grid-cols-4 gap-4`
- 4 stat cards, each with a label, large number, and trend indicator
- One stat card spans `col-span-2` on mobile

---

## What Good Looks Like

- Gallery images are perfectly square using `aspect-square`
- Magazine layout has a clear visual hierarchy (featured vs secondary)
- Stats grid collapses from 4 columns to 2 on smaller screens
- All sections have consistent padding and spacing

---

## Submission

Submit `photo-gallery.html`.
