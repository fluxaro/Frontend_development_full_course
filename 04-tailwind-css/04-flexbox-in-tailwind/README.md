# 04 — Flexbox in Tailwind

## What Is This Lesson About?

Tailwind maps every CSS flexbox property to a utility class. Instead of writing `display: flex; justify-content: space-between; align-items: center;` in a CSS file, you write `flex justify-between items-center` directly in your HTML. This lesson covers every flex utility and shows real-world layout patterns.

---

## Enabling Flexbox

```html
<div class="flex">...</div>
```

This sets `display: flex` on the element. All children become flex items.

---

## flex-direction

```html
flex-row          <!-- row (default) → -->
flex-row-reverse  <!-- row reversed ← -->
flex-col          <!-- column ↓ -->
flex-col-reverse  <!-- column reversed ↑ -->
```

---

## justify-content (Main Axis)

```html
justify-start    <!-- flex-start (default) -->
justify-end      <!-- flex-end -->
justify-center   <!-- center -->
justify-between  <!-- space-between -->
justify-around   <!-- space-around -->
justify-evenly   <!-- space-evenly -->
```

---

## align-items (Cross Axis)

```html
items-start    <!-- flex-start -->
items-end      <!-- flex-end -->
items-center   <!-- center -->
items-stretch  <!-- stretch (default) -->
items-baseline <!-- baseline -->
```

---

## flex-wrap

```html
flex-wrap        <!-- wrap to next line -->
flex-nowrap      <!-- no wrap (default) -->
flex-wrap-reverse <!-- wrap in reverse -->
```

---

## gap

```html
gap-2    <!-- 0.5rem between all items -->
gap-4    <!-- 1rem between all items -->
gap-x-4  <!-- horizontal gap only -->
gap-y-2  <!-- vertical gap only -->
```

---

## Flex Item Properties

```html
flex-1      <!-- grow and shrink equally (flex: 1 1 0%) -->
flex-auto   <!-- grow and shrink based on content -->
flex-none   <!-- don't grow or shrink -->
shrink-0    <!-- never shrink -->
grow        <!-- always grow -->

order-first  <!-- order: -9999 -->
order-last   <!-- order: 9999 -->
order-1      <!-- order: 1 -->

self-start   <!-- align-self: flex-start -->
self-center  <!-- align-self: center -->
self-end     <!-- align-self: flex-end -->
self-stretch <!-- align-self: stretch -->
```

---

## Real-World Patterns

### Navbar
```html
<nav class="flex items-center justify-between px-6 h-16 bg-white shadow-sm">
  <span class="font-bold text-lg">Brand</span>
  <div class="flex items-center gap-4">
    <a href="#" class="text-gray-600 hover:text-gray-900">Home</a>
    <a href="#" class="text-gray-600 hover:text-gray-900">About</a>
  </div>
  <button class="bg-blue-500 text-white px-4 py-2 rounded-lg">Sign Up</button>
</nav>
```

### Perfect Center
```html
<div class="flex items-center justify-center min-h-screen">
  <div class="bg-white p-8 rounded-xl shadow-lg">Centered</div>
</div>
```

### Sidebar Layout
```html
<div class="flex min-h-screen">
  <aside class="w-64 shrink-0 bg-gray-900 text-white p-6">Sidebar</aside>
  <main class="flex-1 p-8">Main content</main>
</div>
```

### Push Item to End
```html
<div class="flex items-center gap-4">
  <span>Logo</span>
  <nav class="flex gap-4">...</nav>
  <button class="ml-auto">CTA</button>  <!-- ml-auto pushes right -->
</div>
```

---

## Common Mistakes

- Applying `flex` to the wrong element — it must go on the **parent**, not the children
- Forgetting `items-center` when you want vertical centering
- Using `w-full` on a flex child when you want it to fill space — use `flex-1` instead
- Not using `shrink-0` on fixed-width sidebars (they'll shrink on small screens)
- Using `flex-col` and forgetting that `justify-*` now controls vertical alignment
