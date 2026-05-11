# Assignment — Dashboard Layout

## What You Are Building

A complete app dashboard layout using only Tailwind flexbox utilities. The layout must have a fixed sidebar, a top navigation bar, and a scrollable main content area with a card grid.

---

## Requirements

Create `dashboard-layout.html` with:

### Sidebar
- Fixed width: `w-64`
- Full height: `min-h-screen`
- Dark background: `bg-gray-900`
- Navigation links with icons (use emoji as icons)
- Active link highlighted
- Logo at the top

### Top Bar
- `flex items-center justify-between`
- Height: `h-16`
- White background with bottom border
- Left: page title
- Right: search input + avatar

### Main Content
- `flex-1` to fill remaining space
- Scrollable: `overflow-y-auto`
- Stats row: 4 stat cards using `flex gap-4`
- Recent activity: a list using `flex flex-col gap-3`

### Overall Structure
```
┌──────────┬─────────────────────────┐
│          │  Top Bar                │
│ Sidebar  ├─────────────────────────┤
│          │  Main Content           │
│          │  (stats + activity)     │
└──────────┴─────────────────────────┘
```

---

## What Good Looks Like

- Sidebar never shrinks (`shrink-0`)
- Main content fills all remaining horizontal space (`flex-1`)
- Top bar spans only the main area (not over the sidebar)
- Stats cards are evenly spaced with `gap-4`
- The layout looks like a real admin dashboard

---

## Submission

Submit `dashboard-layout.html`.
