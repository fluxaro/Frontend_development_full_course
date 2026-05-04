# Class Work — Spacing and Layout Explorer

## What You Will Build

A visual reference page that demonstrates every major layout utility in action — spacing, sizing, display, and positioning.

**Time:** 30 minutes  
**Output:** `layout-explorer.html`

---

## Step 1 — Setup

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Layout Explorer</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 font-sans">

  <!-- Sticky header -->
  <header class="sticky top-0 z-50 bg-white border-b border-gray-200 shadow-sm">
    <div class="container mx-auto px-4 h-14 flex items-center">
      <span class="font-bold text-gray-800">Layout Explorer</span>
    </div>
  </header>

  <main class="container mx-auto px-4 py-10 space-y-12">
    <!-- sections go here -->
  </main>

</body>
</html>
```

---

## Step 2 — Padding Demo

Inside `<main>`, add:

```html
<section>
  <h2 class="text-lg font-bold text-gray-700 mb-4">Padding (p-*, px-*, py-*)</h2>
  <div class="flex flex-wrap gap-4">
    <div class="bg-blue-50 border-2 border-blue-200 rounded-lg">
      <div class="bg-blue-500 text-white text-xs font-mono p-2 rounded">p-2</div>
    </div>
    <div class="bg-blue-50 border-2 border-blue-200 rounded-lg">
      <div class="bg-blue-500 text-white text-xs font-mono p-4 rounded">p-4</div>
    </div>
    <div class="bg-blue-50 border-2 border-blue-200 rounded-lg">
      <div class="bg-blue-500 text-white text-xs font-mono px-8 py-2 rounded">px-8 py-2</div>
    </div>
    <div class="bg-blue-50 border-2 border-blue-200 rounded-lg">
      <div class="bg-blue-500 text-white text-xs font-mono pt-6 pb-1 px-4 rounded">pt-6 pb-1</div>
    </div>
  </div>
</section>
```

---

## Step 3 — Width Demo

```html
<section>
  <h2 class="text-lg font-bold text-gray-700 mb-4">Width (w-*)</h2>
  <div class="space-y-2">
    <div class="h-6 bg-green-400 rounded w-1/4 flex items-center px-2 text-xs text-white font-mono">w-1/4</div>
    <div class="h-6 bg-green-500 rounded w-1/2 flex items-center px-2 text-xs text-white font-mono">w-1/2</div>
    <div class="h-6 bg-green-600 rounded w-3/4 flex items-center px-2 text-xs text-white font-mono">w-3/4</div>
    <div class="h-6 bg-green-700 rounded w-full flex items-center px-2 text-xs text-white font-mono">w-full</div>
  </div>
</section>
```

---

## Step 4 — Margin / space-y Demo

```html
<section>
  <h2 class="text-lg font-bold text-gray-700 mb-4">space-y-* (gap between children)</h2>
  <div class="space-y-6 bg-gray-100 p-4 rounded-xl max-w-xs">
    <div class="bg-purple-500 text-white text-xs font-mono px-3 py-2 rounded">Item 1</div>
    <div class="bg-purple-500 text-white text-xs font-mono px-3 py-2 rounded">Item 2 (space-y-6 above)</div>
    <div class="bg-purple-500 text-white text-xs font-mono px-3 py-2 rounded">Item 3 (space-y-6 above)</div>
  </div>
</section>
```

---

## Step 5 — Positioning Demo

```html
<section>
  <h2 class="text-lg font-bold text-gray-700 mb-4">Positioning (relative + absolute)</h2>
  <div class="relative bg-gray-100 rounded-xl h-32 max-w-md">
    <span class="text-xs text-gray-400 p-2">relative parent</span>
    <div class="absolute top-2 right-2 bg-blue-500 text-white text-xs font-mono px-2 py-1 rounded">
      absolute top-2 right-2
    </div>
    <div class="absolute bottom-2 left-2 bg-red-500 text-white text-xs font-mono px-2 py-1 rounded">
      absolute bottom-2 left-2
    </div>
  </div>
</section>
```

---

## Step 6 — Fixed Back-to-Top Button

Before the closing `</body>` tag:

```html
<a href="#" class="fixed bottom-6 right-6 w-12 h-12 bg-blue-500 text-white rounded-full flex items-center justify-center shadow-lg hover:bg-blue-600 transition-colors text-lg z-50">
  ↑
</a>
```

---

## Checklist

- [ ] Sticky header stays at top when scrolling
- [ ] Padding demo shows visual difference between `p-2`, `p-4`, `px-8 py-2`
- [ ] Width bars show 25%, 50%, 75%, 100%
- [ ] `space-y-6` creates visible gaps between items
- [ ] Absolute positioned elements are inside a `relative` parent
- [ ] Fixed back-to-top button stays in corner when scrolling
