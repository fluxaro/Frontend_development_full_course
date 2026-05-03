# Assignment — Interactive Product Table

## What You Are Building

Create a product comparison table with interactive pseudo-class styling.

---

## Requirements

### HTML

Create `product-table.html` with:
- A table comparing at least 5 products
- At least 6 columns (name, price, rating, category, in stock, action)
- A form with search input and filter select above the table

### CSS Requirements

Use ALL of these pseudo-classes:

**User actions:**
- `:hover` on table rows (highlight on hover)
- `:hover` on buttons (color change)
- `:focus` on form inputs (visible focus ring)
- `:active` on buttons (pressed effect)

**Structural:**
- `:nth-child(even)` for zebra striping
- `:first-child` on table header cells
- `:last-child` on table rows
- `:not(:last-child)` for borders between items

**Form states:**
- `:focus` on inputs
- `:valid` and `:invalid` on the search input
- `:disabled` on a button

---

## What Good Looks Like

- Table rows highlight on hover
- Zebra striping makes rows easy to read
- Focus styles are visible and accessible
- Buttons have clear hover and active states
- The page is fully keyboard navigable

---

## Submission

Submit `product-table.html` and `product-table.css`.
