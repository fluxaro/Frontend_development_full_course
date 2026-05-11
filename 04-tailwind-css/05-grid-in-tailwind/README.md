# 05 — Grid in Tailwind

## What Is This Lesson About?

Tailwind maps every CSS Grid property to a utility class. Grid is the best tool for two-dimensional layouts — page structures, card galleries, dashboards, and magazine layouts. This lesson covers every grid utility and shows real-world patterns.

---

## Enabling Grid

```html
<div class="grid">...</div>
```

---

## grid-template-columns

```html
grid-cols-1   <!-- 1 equal column -->
grid-cols-2   <!-- 2 equal columns -->
grid-cols-3   <!-- 3 equal columns -->
grid-cols-4   <!-- 4 equal columns -->
grid-cols-6   <!-- 6 equal columns -->
grid-cols-12  <!-- 12 equal columns -->
```

---

## gap

```html
gap-2    <!-- 0.5rem all sides -->
gap-4    <!-- 1rem all sides -->
gap-6    <!-- 1.5rem all sides -->
gap-x-4  <!-- horizontal only -->
gap-y-6  <!-- vertical only -->
```

---

## Column Spanning

```html
col-span-1   <!-- span 1 column -->
col-span-2   <!-- span 2 columns -->
col-span-3   <!-- span 3 columns -->
col-span-full <!-- span all columns -->
col-start-1  <!-- start at column line 1 -->
col-end-3    <!-- end at column line 3 -->
```

---

## Row Spanning

```html
row-span-1   <!-- span 1 row -->
row-span-2   <!-- span 2 rows -->
row-span-3   <!-- span 3 rows -->
row-span-full <!-- span all rows -->
```

---

## Alignment

```html
place-items-center  <!-- center in both axes -->
place-items-start   <!-- start in both axes -->
justify-items-center <!-- horizontal centering -->
items-center        <!-- vertical centering -->

<!-- Per item -->
place-self-center   <!-- center this item -->
col-start-2         <!-- start at column 2 -->
```

---

## Responsive Grid Pattern

```html
<!-- 1 col → 2 col → 3 col -->
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
  <div>Card</div>
  <div>Card</div>
  <div>Card</div>
</div>
```

---

## Real-World Patterns

### Photo Gallery
```html
<div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-3">
  <img class="w-full aspect-square object-cover rounded-lg" src="..." alt="">
</div>
```

### Magazine Layout
```html
<div class="grid grid-cols-3 grid-rows-2 gap-4 h-96">
  <div class="col-span-2 row-span-2 bg-blue-500 rounded-xl">Featured</div>
  <div class="bg-green-400 rounded-xl">Story 2</div>
  <div class="bg-orange-400 rounded-xl">Story 3</div>
</div>
```

### Dashboard Stats
```html
<div class="grid grid-cols-2 lg:grid-cols-4 gap-4">
  <div class="bg-white rounded-xl p-5 shadow-sm">Stat 1</div>
  <div class="bg-white rounded-xl p-5 shadow-sm">Stat 2</div>
  <div class="bg-white rounded-xl p-5 shadow-sm">Stat 3</div>
  <div class="bg-white rounded-xl p-5 shadow-sm">Stat 4</div>
</div>
```

---

## Common Mistakes

- Forgetting `grid` on the parent — `grid-cols-3` alone does nothing
- Using `grid` when `flex` is better (one-dimensional layouts)
- Not using `col-span-full` for full-width items inside a grid
- Forgetting `gap` — grid items touch each other without it
- Using fixed heights on grid rows when content height varies
