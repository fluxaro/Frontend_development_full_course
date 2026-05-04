# Assignment — Layered UI Components

## What You Are Building

Build a UI with multiple overlapping layers to demonstrate z-index mastery.

---

## Requirements

Create `layered-ui.html` and `layered-ui.css` with:

### Layer Stack (from bottom to top)
1. Background image/pattern (z-index: -1)
2. Page content (z-index: 0)
3. Floating action button (z-index: 10)
4. Dropdown menu (z-index: 100)
5. Sticky header (z-index: 200)
6. Modal overlay (z-index: 300)
7. Modal dialog (z-index: 400)
8. Toast notification (z-index: 500)

### Requirements
- Use CSS custom properties for all z-index values
- Each layer must be visually distinct
- The modal must appear above the sticky header
- The toast must appear above the modal
- Use `isolation: isolate` on at least one component

---

## Submission

Submit `layered-ui.html` and `layered-ui.css`.
