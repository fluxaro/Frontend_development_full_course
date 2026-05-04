# Assignment — Dashboard Layout with Flexbox Items

## What You Are Building

Build a complete dashboard layout using flexbox item properties.

---

## Requirements

Create `dashboard.html` and `dashboard.css` with:

### Layout Structure
- Fixed sidebar (250px, `flex: 0 0 250px`)
- Main content area (`flex: 1`)
- Header that spans full width

### Inside the Main Content
- Stats row: 4 equal cards (`flex: 1` each)
- Chart + sidebar: chart takes 2/3, sidebar takes 1/3
- Recent activity: full width

### Use These Item Properties
- `flex-grow` — for the main content area
- `flex-shrink: 0` — for the sidebar (never shrinks)
- `flex-basis` — for fixed-size elements
- `align-self` — for at least one element
- `order` — to reorder elements on mobile (use media query)
- `margin-left: auto` — to push an element to the end

---

## Submission

Submit `dashboard.html` and `dashboard.css`.
