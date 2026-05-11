# Class Work — Navbar, Hero, and Card Row

## What You Will Build

A page with a responsive navbar, a centered hero section, and a row of feature cards — all built with Tailwind flexbox utilities.

**Time:** 35 minutes  
**Output:** `flex-layout.html`

---

## Step 1 — Setup

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flex Layout</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="font-sans bg-gray-50 text-gray-800">
</body>
</html>
```

---

## Step 2 — Navbar

```html
<nav class="sticky top-0 z-50 bg-white border-b border-gray-200 shadow-sm">
  <div class="max-w-6xl mx-auto px-4 h-16 flex items-center justify-between">

    <!-- Logo -->
    <span class="font-bold text-xl text-blue-600">FlexApp</span>

    <!-- Nav links -->
    <div class="hidden md:flex items-center gap-1">
      <a href="#" class="px-3 py-2 rounded-lg text-sm font-medium text-gray-600 hover:bg-gray-100 hover:text-gray-900 transition-colors">Home</a>
      <a href="#" class="px-3 py-2 rounded-lg text-sm font-medium text-gray-600 hover:bg-gray-100 hover:text-gray-900 transition-colors">Features</a>
      <a href="#" class="px-3 py-2 rounded-lg text-sm font-medium text-gray-600 hover:bg-gray-100 hover:text-gray-900 transition-colors">Pricing</a>
    </div>

    <!-- CTA — ml-auto pushes it to the right on mobile -->
    <div class="flex items-center gap-3">
      <a href="#" class="text-sm font-medium text-gray-600 hover:text-gray-900">Log in</a>
      <a href="#" class="bg-blue-600 text-white text-sm font-semibold px-4 py-2 rounded-lg hover:bg-blue-700 transition-colors">Sign up</a>
    </div>

  </div>
</nav>
```

**Key flex classes:**
- `flex items-center justify-between` — horizontal layout, vertically centered, space between logo and CTA
- `hidden md:flex` — hidden on mobile, flex on medium screens+
- `flex items-center gap-1` — nav links side by side with small gap

---

## Step 3 — Hero Section

```html
<section class="min-h-[80vh] flex flex-col items-center justify-center text-center px-4 bg-gradient-to-br from-blue-50 to-indigo-100">
  <h1 class="text-4xl md:text-6xl font-extrabold text-gray-900 mb-4 leading-tight">
    Build Faster with<br>
    <span class="text-blue-600">Flexbox</span>
  </h1>
  <p class="text-lg text-gray-500 max-w-xl mb-8 leading-relaxed">
    Tailwind's flex utilities let you build any layout directly in HTML — no CSS file needed.
  </p>
  <div class="flex flex-wrap gap-4 justify-center">
    <a href="#" class="bg-blue-600 text-white font-bold px-8 py-3.5 rounded-xl hover:bg-blue-700 transition-colors">Get Started</a>
    <a href="#" class="bg-white text-gray-700 font-semibold px-8 py-3.5 rounded-xl border border-gray-200 hover:border-gray-300 transition-colors">Learn More</a>
  </div>
</section>
```

**Key flex classes:**
- `flex flex-col items-center justify-center` — stack children vertically, center both axes
- `flex flex-wrap gap-4 justify-center` — buttons side by side, wrap on small screens

---

## Step 4 — Feature Cards

```html
<section class="py-20 px-4">
  <div class="max-w-5xl mx-auto">
    <h2 class="text-2xl font-bold text-center text-gray-900 mb-12">Why Flexbox?</h2>

    <div class="flex flex-wrap gap-6">

      <div class="flex-1 min-w-64 bg-white rounded-2xl p-6 shadow-sm border border-gray-100">
        <div class="flex items-center gap-3 mb-4">
          <div class="w-10 h-10 bg-blue-100 rounded-xl flex items-center justify-center text-xl">⚡</div>
          <h3 class="font-bold text-gray-900">One Dimension</h3>
        </div>
        <p class="text-sm text-gray-500 leading-relaxed">Flexbox controls layout in one direction at a time — row or column. Perfect for navbars, card rows, and stacked lists.</p>
      </div>

      <div class="flex-1 min-w-64 bg-white rounded-2xl p-6 shadow-sm border border-gray-100">
        <div class="flex items-center gap-3 mb-4">
          <div class="w-10 h-10 bg-green-100 rounded-xl flex items-center justify-center text-xl">🎯</div>
          <h3 class="font-bold text-gray-900">Easy Centering</h3>
        </div>
        <p class="text-sm text-gray-500 leading-relaxed">Centering anything is just <code class="bg-gray-100 px-1 rounded text-xs">flex items-center justify-center</code>. No more margin hacks.</p>
      </div>

      <div class="flex-1 min-w-64 bg-white rounded-2xl p-6 shadow-sm border border-gray-100">
        <div class="flex items-center gap-3 mb-4">
          <div class="w-10 h-10 bg-purple-100 rounded-xl flex items-center justify-center text-xl">📐</div>
          <h3 class="font-bold text-gray-900">Flexible Sizing</h3>
        </div>
        <p class="text-sm text-gray-500 leading-relaxed">Use <code class="bg-gray-100 px-1 rounded text-xs">flex-1</code> to fill space and <code class="bg-gray-100 px-1 rounded text-xs">shrink-0</code> to keep fixed widths.</p>
      </div>

    </div>
  </div>
</section>
```

**Key flex classes:**
- `flex flex-wrap gap-6` — cards side by side, wrap when needed
- `flex-1 min-w-64` — each card grows equally, minimum 16rem wide
- `flex items-center gap-3` — icon and title side by side

---

## Checklist

- [ ] Navbar uses `flex items-center justify-between`
- [ ] Nav links use `flex items-center gap-1`
- [ ] Hero uses `flex flex-col items-center justify-center`
- [ ] Buttons use `flex flex-wrap gap-4 justify-center`
- [ ] Cards use `flex flex-wrap gap-6` with `flex-1 min-w-64`
- [ ] Card headers use `flex items-center gap-3`

---

## Bonus Challenges

1. Add a media object (avatar + text side by side) using `flex gap-4 items-start`
2. Add a footer with `flex justify-between items-center`
3. Make the sidebar layout: `<div class="flex min-h-screen">` with `w-64 shrink-0` sidebar and `flex-1` main
