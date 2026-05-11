# Notes — Grid in Tailwind

## Quick Reference

```html
<!-- Container -->
grid grid-cols-3 gap-4

<!-- Columns -->
grid-cols-1  grid-cols-2  grid-cols-3
grid-cols-4  grid-cols-6  grid-cols-12

<!-- Spanning -->
col-span-2    <!-- span 2 columns -->
col-span-full <!-- span all columns -->
row-span-2    <!-- span 2 rows -->

<!-- Alignment -->
place-items-center  <!-- center all items -->
place-self-center   <!-- center one item -->
```

## Responsive Pattern

```html
grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6
```

## Flex vs Grid

| Use Flex | Use Grid |
|---|---|
| Navbar | Page layout |
| Card row | Photo gallery |
| Centering | Magazine layout |
| One direction | Two directions |

## Common Patterns

```html
<!-- Equal columns -->
<div class="grid grid-cols-3 gap-6">

<!-- Full-width item in grid -->
<div class="col-span-full">

<!-- Magazine: featured item spans 2x2 -->
<div class="grid grid-cols-3 grid-rows-2 gap-4">
  <div class="col-span-2 row-span-2">Featured</div>
  <div>Story 2</div>
  <div>Story 3</div>
</div>
```

## Common Mistakes

- `grid-cols-3` needs `grid` on the same element
- Use `gap` — items touch without it
- `col-span-full` spans all columns regardless of count
