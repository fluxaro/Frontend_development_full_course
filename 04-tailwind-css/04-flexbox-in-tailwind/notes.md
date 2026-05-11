# Notes — Flexbox in Tailwind

## Quick Reference

```html
<!-- Container -->
flex flex-col flex-row flex-wrap gap-4

<!-- Main axis (justify-content) -->
justify-start justify-center justify-end
justify-between justify-around justify-evenly

<!-- Cross axis (align-items) -->
items-start items-center items-end items-stretch

<!-- Items -->
flex-1      <!-- fill remaining space -->
shrink-0    <!-- don't shrink -->
flex-none   <!-- don't grow or shrink -->
self-center <!-- override align-items for one item -->
ml-auto     <!-- push item to the end -->
```

## Axis Reference

| flex-direction | justify-* controls | items-* controls |
|---|---|---|
| `flex-row` (default) | horizontal | vertical |
| `flex-col` | vertical | horizontal |

## Common Patterns

```html
<!-- Navbar -->
<nav class="flex items-center justify-between px-6 h-16">

<!-- Perfect center -->
<div class="flex items-center justify-center min-h-screen">

<!-- Sidebar + main -->
<div class="flex">
  <aside class="w-64 shrink-0">
  <main class="flex-1">

<!-- Card row that wraps -->
<div class="flex flex-wrap gap-4">
  <div class="flex-1 min-w-64">card</div>
```

## Common Mistakes

- `flex` goes on the **parent**, not the children
- Use `flex-1` not `w-full` to fill remaining space
- Add `shrink-0` to fixed-width sidebars
- `ml-auto` pushes an item to the far end of the main axis
