# 03 — Layout Utilities: Container, Padding, Margin

## What Is This Lesson About?

Tailwind provides a complete set of layout utilities for controlling spacing, sizing, display, and positioning. This lesson covers the most-used layout classes: `container`, padding (`p-*`), margin (`m-*`), width (`w-*`), height (`h-*`), and display utilities.

---

## Container

`container` sets a max-width that snaps to Tailwind's breakpoints. Always pair it with `mx-auto` to center it and `px-4` for side padding:

```html
<div class="container mx-auto px-4">
  <!-- content is centered and has max-width -->
</div>
```

| Breakpoint | Max-width |
|---|---|
| `sm` (640px+) | 640px |
| `md` (768px+) | 768px |
| `lg` (1024px+) | 1024px |
| `xl` (1280px+) | 1280px |
| `2xl` (1536px+) | 1536px |

---

## Padding

```html
p-4      <!-- all sides: 1rem -->
px-6     <!-- left + right: 1.5rem -->
py-3     <!-- top + bottom: 0.75rem -->
pt-8     <!-- top only: 2rem -->
pr-4     <!-- right only: 1rem -->
pb-6     <!-- bottom only: 1.5rem -->
pl-2     <!-- left only: 0.5rem -->
```

---

## Margin

```html
m-4          <!-- all sides: 1rem -->
mx-auto      <!-- center horizontally -->
my-8         <!-- top + bottom: 2rem -->
mt-4         <!-- top only: 1rem -->
mb-6         <!-- bottom only: 1.5rem -->
-mt-4        <!-- negative margin: -1rem -->
```

`space-y-*` and `space-x-*` add margin between children without touching the first/last child:

```html
<div class="space-y-4">
  <div>Item 1</div>  <!-- no top margin -->
  <div>Item 2</div>  <!-- margin-top: 1rem -->
  <div>Item 3</div>  <!-- margin-top: 1rem -->
</div>
```

---

## Width & Height

```html
w-full      <!-- width: 100% -->
w-1/2       <!-- width: 50% -->
w-1/3       <!-- width: 33.333% -->
w-64        <!-- width: 16rem (256px) -->
w-screen    <!-- width: 100vw -->
max-w-sm    <!-- max-width: 24rem -->
max-w-lg    <!-- max-width: 32rem -->
max-w-xl    <!-- max-width: 36rem -->
max-w-2xl   <!-- max-width: 42rem -->
max-w-7xl   <!-- max-width: 80rem -->

h-16        <!-- height: 4rem -->
h-screen    <!-- height: 100vh -->
min-h-screen <!-- min-height: 100vh -->
```

---

## Display

```html
block         <!-- display: block -->
inline-block  <!-- display: inline-block -->
inline        <!-- display: inline -->
hidden        <!-- display: none -->
flex          <!-- display: flex -->
grid          <!-- display: grid -->
```

---

## Position

```html
relative      <!-- position: relative -->
absolute      <!-- position: absolute -->
fixed         <!-- position: fixed -->
sticky        <!-- position: sticky -->
inset-0       <!-- top:0 right:0 bottom:0 left:0 -->
top-4         <!-- top: 1rem -->
right-0       <!-- right: 0 -->
z-10          <!-- z-index: 10 -->
z-50          <!-- z-index: 50 -->
```

---

## Common Patterns

```html
<!-- Centered page container -->
<div class="max-w-4xl mx-auto px-4 py-8">...</div>

<!-- Full-height page -->
<div class="min-h-screen bg-gray-50">...</div>

<!-- Sticky navbar -->
<nav class="sticky top-0 z-50 bg-white shadow-sm">...</nav>

<!-- Centered modal overlay -->
<div class="fixed inset-0 bg-black/50 flex items-center justify-center z-50">...</div>
```

---

## Common Mistakes

- Forgetting `mx-auto` with `container` — the container won't be centered
- Using `w-screen` inside a container (causes horizontal scroll)
- Using `h-screen` on a div that has content taller than the viewport
- Forgetting `px-4` on the container — content touches the screen edges on mobile
