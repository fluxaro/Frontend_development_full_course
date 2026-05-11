# Class Work — Responsive Card Grid

## What You Will Build

A responsive card grid that changes from 1 column on mobile to 2 on tablet to 3 on desktop, plus a magazine layout with a featured card.

**Time:** 30 minutes  
**Output:** `grid-layout.html`

---

## Step 1 — Setup

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Grid Layout</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 font-sans p-8">
  <h1 class="text-3xl font-bold text-gray-900 mb-2">Grid in Tailwind</h1>
  <p class="text-gray-500 mb-10">Resize the window to see the responsive grid change</p>
</body>
</html>
```

---

## Step 2 — Responsive Card Grid

```html
<section class="mb-16">
  <h2 class="text-xl font-bold text-gray-800 mb-6">
    Responsive Grid
    <span class="text-sm font-normal text-gray-400 ml-2">1 → 2 → 3 columns</span>
  </h2>

  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">

    <div class="bg-white rounded-2xl overflow-hidden shadow-sm border border-gray-100 hover:shadow-md transition-shadow">
      <div class="h-40 bg-gradient-to-br from-blue-400 to-blue-600"></div>
      <div class="p-5">
        <span class="text-xs font-bold text-blue-500 uppercase tracking-wide">Design</span>
        <h3 class="font-bold text-gray-900 mt-1 mb-2">Card One</h3>
        <p class="text-sm text-gray-500">1 column on mobile, 2 on tablet, 3 on desktop.</p>
      </div>
    </div>

    <div class="bg-white rounded-2xl overflow-hidden shadow-sm border border-gray-100 hover:shadow-md transition-shadow">
      <div class="h-40 bg-gradient-to-br from-green-400 to-emerald-600"></div>
      <div class="p-5">
        <span class="text-xs font-bold text-green-500 uppercase tracking-wide">Code</span>
        <h3 class="font-bold text-gray-900 mt-1 mb-2">Card Two</h3>
        <p class="text-sm text-gray-500">No media queries written — Tailwind handles it.</p>
      </div>
    </div>

    <div class="bg-white rounded-2xl overflow-hidden shadow-sm border border-gray-100 hover:shadow-md transition-shadow">
      <div class="h-40 bg-gradient-to-br from-purple-400 to-violet-600"></div>
      <div class="p-5">
        <span class="text-xs font-bold text-purple-500 uppercase tracking-wide">Layout</span>
        <h3 class="font-bold text-gray-900 mt-1 mb-2">Card Three</h3>
        <p class="text-sm text-gray-500">Just add sm: and lg: prefixes to grid-cols-*.</p>
      </div>
    </div>

    <div class="bg-white rounded-2xl overflow-hidden shadow-sm border border-gray-100 hover:shadow-md transition-shadow">
      <div class="h-40 bg-gradient-to-br from-orange-400 to-red-500"></div>
      <div class="p-5">
        <span class="text-xs font-bold text-orange-500 uppercase tracking-wide">Tools</span>
        <h3 class="font-bold text-gray-900 mt-1 mb-2">Card Four</h3>
        <p class="text-sm text-gray-500">gap-6 adds consistent spacing between all cards.</p>
      </div>
    </div>

    <div class="bg-white rounded-2xl overflow-hidden shadow-sm border border-gray-100 hover:shadow-md transition-shadow">
      <div class="h-40 bg-gradient-to-br from-pink-400 to-rose-600"></div>
      <div class="p-5">
        <span class="text-xs font-bold text-pink-500 uppercase tracking-wide">Tips</span>
        <h3 class="font-bold text-gray-900 mt-1 mb-2">Card Five</h3>
        <p class="text-sm text-gray-500">Cards automatically wrap to the next row.</p>
      </div>
    </div>

    <div class="bg-white rounded-2xl overflow-hidden shadow-sm border border-gray-100 hover:shadow-md transition-shadow">
      <div class="h-40 bg-gradient-to-br from-cyan-400 to-teal-600"></div>
      <div class="p-5">
        <span class="text-xs font-bold text-cyan-500 uppercase tracking-wide">Grid</span>
        <h3 class="font-bold text-gray-900 mt-1 mb-2">Card Six</h3>
        <p class="text-sm text-gray-500">All equal width — no flex-1 needed in grid.</p>
      </div>
    </div>

  </div>
</section>
```

---

## Step 3 — Magazine Layout

```html
<section class="mb-16">
  <h2 class="text-xl font-bold text-gray-800 mb-6">Magazine Layout — col-span + row-span</h2>

  <div class="grid grid-cols-3 grid-rows-2 gap-4 h-80">

    <!-- Featured: spans 2 cols × 2 rows -->
    <div class="col-span-2 row-span-2 bg-gradient-to-br from-slate-800 to-blue-900 rounded-2xl p-6 flex flex-col justify-end text-white">
      <span class="text-xs font-bold uppercase tracking-widest text-blue-300 mb-2">Featured</span>
      <h3 class="text-2xl font-bold mb-1">col-span-2 row-span-2</h3>
      <p class="text-sm text-slate-300">This card spans 2 columns and 2 rows</p>
    </div>

    <!-- Story 2 -->
    <div class="bg-gradient-to-br from-green-500 to-emerald-600 rounded-2xl p-4 flex flex-col justify-end text-white">
      <span class="text-xs font-bold uppercase tracking-widest text-green-200 mb-1">Story</span>
      <h3 class="text-sm font-bold">Normal cell</h3>
    </div>

    <!-- Story 3 -->
    <div class="bg-gradient-to-br from-orange-500 to-red-600 rounded-2xl p-4 flex flex-col justify-end text-white">
      <span class="text-xs font-bold uppercase tracking-widest text-orange-200 mb-1">Story</span>
      <h3 class="text-sm font-bold">Normal cell</h3>
    </div>

  </div>
</section>
```

---

## Step 4 — Full-Width Item

```html
<section>
  <h2 class="text-xl font-bold text-gray-800 mb-6">col-span-full — Full Width in Grid</h2>

  <div class="grid grid-cols-3 gap-4">
    <div class="bg-white rounded-xl p-4 border border-gray-200 shadow-sm text-center text-sm font-mono text-gray-500">col 1</div>
    <div class="bg-white rounded-xl p-4 border border-gray-200 shadow-sm text-center text-sm font-mono text-gray-500">col 2</div>
    <div class="bg-white rounded-xl p-4 border border-gray-200 shadow-sm text-center text-sm font-mono text-gray-500">col 3</div>
    <div class="col-span-full bg-blue-500 text-white rounded-xl p-4 text-center text-sm font-bold">col-span-full — spans all 3 columns</div>
    <div class="bg-white rounded-xl p-4 border border-gray-200 shadow-sm text-center text-sm font-mono text-gray-500">col 1</div>
    <div class="col-span-2 bg-purple-100 rounded-xl p-4 border border-purple-200 text-center text-sm font-mono text-purple-600">col-span-2</div>
  </div>
</section>
```

---

## Checklist

- [ ] Responsive grid uses `grid-cols-1 sm:grid-cols-2 lg:grid-cols-3`
- [ ] `gap-6` between all cards
- [ ] Magazine layout uses `col-span-2 row-span-2` for featured card
- [ ] `col-span-full` demo shows a full-width item
- [ ] Resize the window to verify responsive behavior

---

## Bonus Challenges

1. Add `hover:scale-105 transition-transform` to the gallery cards
2. Create a 4-column stats grid: `grid-cols-2 lg:grid-cols-4`
3. Add `aspect-square` to the card images to make them perfectly square
