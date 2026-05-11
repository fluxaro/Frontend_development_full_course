# Class Work — Make a Card Grid Responsive

## What You Will Build

A card grid that starts as a single column on mobile and expands to 3 columns on desktop, with a responsive navbar and hero section.

**Time:** 35 minutes  
**Output file:** `responsive-grid.html`

---

## Step 1 — Boilerplate with Breakpoint Indicator

Create `responsive-grid.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Grid</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 text-gray-900">

  <!-- Breakpoint indicator (dev tool) -->
  <div class="fixed bottom-4 right-4 z-50 bg-gray-900 text-white text-xs font-mono px-3 py-1.5 rounded-full shadow-lg">
    <span class="sm:hidden">📱 xs</span>
    <span class="hidden sm:inline md:hidden">📱 sm</span>
    <span class="hidden md:inline lg:hidden">💻 md</span>
    <span class="hidden lg:inline xl:hidden">🖥️ lg</span>
    <span class="hidden xl:inline 2xl:hidden">🖥️ xl</span>
    <span class="hidden 2xl:inline">🖥️ 2xl</span>
  </div>

  <!-- Content goes here -->

</body>
</html>
```

Open the file and resize the window — you'll see the indicator change as you cross breakpoints.

---

## Step 2 — Responsive Navbar

```html
<nav class="bg-white border-b border-gray-200 px-4 md:px-6 py-4">
  <div class="max-w-6xl mx-auto flex items-center justify-between">

    <!-- Logo (always visible) -->
    <a href="#" class="text-xl font-bold text-blue-600">Responsive</a>

    <!-- Nav links: hidden on mobile, visible on md+ -->
    <ul class="hidden md:flex items-center gap-6">
      <li><a href="#" class="text-gray-600 hover:text-gray-900 font-medium text-sm">Features</a></li>
      <li><a href="#" class="text-gray-600 hover:text-gray-900 font-medium text-sm">Pricing</a></li>
      <li><a href="#" class="text-gray-600 hover:text-gray-900 font-medium text-sm">About</a></li>
    </ul>

    <!-- CTA: hidden on mobile, visible on md+ -->
    <a href="#" class="hidden md:block bg-blue-600 text-white px-4 py-2 rounded-lg text-sm font-semibold hover:bg-blue-700">
      Get Started
    </a>

    <!-- Hamburger: visible on mobile, hidden on md+ -->
    <button class="md:hidden p-2 rounded-lg hover:bg-gray-100">
      <div class="w-5 h-0.5 bg-gray-700 mb-1"></div>
      <div class="w-5 h-0.5 bg-gray-700 mb-1"></div>
      <div class="w-5 h-0.5 bg-gray-700"></div>
    </button>

  </div>
</nav>
```

**What's happening:**
- `hidden md:flex` — nav links are hidden on mobile, flex on md+
- `hidden md:block` — CTA button hidden on mobile, block on md+
- `md:hidden` — hamburger visible on mobile, hidden on md+

---

## Step 3 — Responsive Hero

```html
<section class="bg-white px-4 md:px-8 lg:px-16 py-12 md:py-20 lg:py-28">
  <div class="max-w-6xl mx-auto flex flex-col md:flex-row items-center gap-8 md:gap-16">

    <!-- Text content -->
    <div class="flex-1 text-center md:text-left">
      <span class="text-xs font-bold uppercase tracking-widest text-blue-600 mb-4 block">
        Responsive Design
      </span>
      <h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-4 md:mb-6">
        Looks great<br>on every screen
      </h1>
      <p class="text-base md:text-lg text-gray-500 leading-relaxed mb-6 md:mb-8 max-w-lg mx-auto md:mx-0">
        Resize this window to see the layout adapt. Mobile-first design with Tailwind responsive prefixes.
      </p>
      <div class="flex flex-col sm:flex-row gap-3 justify-center md:justify-start">
        <a href="#" class="bg-blue-600 text-white px-6 py-3 rounded-xl font-semibold hover:bg-blue-700 text-center">
          Get Started
        </a>
        <a href="#" class="border border-gray-300 text-gray-700 px-6 py-3 rounded-xl font-semibold hover:bg-gray-50 text-center">
          Learn More
        </a>
      </div>
    </div>

    <!-- Visual -->
    <div class="flex-1 w-full max-w-sm md:max-w-none">
      <div class="bg-gradient-to-br from-blue-100 to-indigo-200 rounded-2xl h-48 md:h-64 lg:h-80 flex items-center justify-center">
        <span class="text-blue-400 text-5xl md:text-7xl">📱</span>
      </div>
    </div>

  </div>
</section>
```

**What's happening:**
- `flex-col md:flex-row` — stacked on mobile, side by side on desktop
- `text-center md:text-left` — centered on mobile, left-aligned on desktop
- `text-3xl sm:text-4xl md:text-5xl lg:text-6xl` — heading scales up with screen size
- `flex-col sm:flex-row` — buttons stack on mobile, row on sm+

---

## Step 4 — Responsive Card Grid

```html
<section class="max-w-6xl mx-auto px-4 md:px-6 py-12 md:py-16">

  <div class="text-center mb-8 md:mb-12">
    <h2 class="text-2xl md:text-3xl font-bold text-gray-900 mb-3">Features</h2>
    <p class="text-gray-500 md:text-lg">Resize the window to see the grid change</p>
  </div>

  <!-- THE RESPONSIVE GRID -->
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 md:gap-6">

    <div class="bg-white rounded-2xl p-6 shadow-sm border border-gray-100">
      <div class="w-12 h-12 bg-blue-100 rounded-xl flex items-center justify-center text-2xl mb-4">⚡</div>
      <h3 class="text-lg font-bold text-gray-900 mb-2">Fast</h3>
      <p class="text-gray-500 text-sm leading-relaxed">
        Optimized for performance. Your users will notice the difference.
      </p>
    </div>

    <div class="bg-white rounded-2xl p-6 shadow-sm border border-gray-100">
      <div class="w-12 h-12 bg-green-100 rounded-xl flex items-center justify-center text-2xl mb-4">🎨</div>
      <h3 class="text-lg font-bold text-gray-900 mb-2">Beautiful</h3>
      <p class="text-gray-500 text-sm leading-relaxed">
        Every component looks great out of the box. No design skills required.
      </p>
    </div>

    <div class="bg-white rounded-2xl p-6 shadow-sm border border-gray-100">
      <div class="w-12 h-12 bg-purple-100 rounded-xl flex items-center justify-center text-2xl mb-4">📱</div>
      <h3 class="text-lg font-bold text-gray-900 mb-2">Responsive</h3>
      <p class="text-gray-500 text-sm leading-relaxed">
        Mobile-first design that works on every screen size.
      </p>
    </div>

    <div class="bg-white rounded-2xl p-6 shadow-sm border border-gray-100">
      <div class="w-12 h-12 bg-orange-100 rounded-xl flex items-center justify-center text-2xl mb-4">🔧</div>
      <h3 class="text-lg font-bold text-gray-900 mb-2">Customizable</h3>
      <p class="text-gray-500 text-sm leading-relaxed">
        Tweak every detail to match your brand and design system.
      </p>
    </div>

    <div class="bg-white rounded-2xl p-6 shadow-sm border border-gray-100">
      <div class="w-12 h-12 bg-red-100 rounded-xl flex items-center justify-center text-2xl mb-4">🔒</div>
      <h3 class="text-lg font-bold text-gray-900 mb-2">Secure</h3>
      <p class="text-gray-500 text-sm leading-relaxed">
        Built with security best practices from the ground up.
      </p>
    </div>

    <div class="bg-white rounded-2xl p-6 shadow-sm border border-gray-100">
      <div class="w-12 h-12 bg-teal-100 rounded-xl flex items-center justify-center text-2xl mb-4">📊</div>
      <h3 class="text-lg font-bold text-gray-900 mb-2">Analytics</h3>
      <p class="text-gray-500 text-sm leading-relaxed">
        Understand your users with built-in analytics and reporting.
      </p>
    </div>

  </div>
</section>
```

---

## Step 5 — Responsive Footer

```html
<footer class="bg-gray-900 text-white px-4 md:px-8 py-12 md:py-16 mt-8">
  <div class="max-w-6xl mx-auto">

    <!-- Footer grid: 1 col → 2 col → 4 col -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mb-12">

      <div class="md:col-span-2 lg:col-span-1">
        <a href="#" class="text-xl font-bold text-white mb-3 block">Responsive</a>
        <p class="text-gray-400 text-sm leading-relaxed">
          Building beautiful, responsive interfaces with Tailwind CSS.
        </p>
      </div>

      <div>
        <h4 class="font-semibold text-white mb-4 text-sm uppercase tracking-widest">Product</h4>
        <ul class="space-y-2">
          <li><a href="#" class="text-gray-400 hover:text-white text-sm">Features</a></li>
          <li><a href="#" class="text-gray-400 hover:text-white text-sm">Pricing</a></li>
          <li><a href="#" class="text-gray-400 hover:text-white text-sm">Changelog</a></li>
        </ul>
      </div>

      <div>
        <h4 class="font-semibold text-white mb-4 text-sm uppercase tracking-widest">Company</h4>
        <ul class="space-y-2">
          <li><a href="#" class="text-gray-400 hover:text-white text-sm">About</a></li>
          <li><a href="#" class="text-gray-400 hover:text-white text-sm">Blog</a></li>
          <li><a href="#" class="text-gray-400 hover:text-white text-sm">Careers</a></li>
        </ul>
      </div>

      <div>
        <h4 class="font-semibold text-white mb-4 text-sm uppercase tracking-widest">Legal</h4>
        <ul class="space-y-2">
          <li><a href="#" class="text-gray-400 hover:text-white text-sm">Privacy</a></li>
          <li><a href="#" class="text-gray-400 hover:text-white text-sm">Terms</a></li>
        </ul>
      </div>

    </div>

    <div class="border-t border-gray-800 pt-8 flex flex-col md:flex-row items-center justify-between gap-4">
      <p class="text-gray-500 text-sm">© 2025 Responsive. All rights reserved.</p>
      <p class="text-gray-600 text-xs font-mono">Built with Tailwind CSS responsive prefixes</p>
    </div>

  </div>
</footer>
```

---

## Checklist

- [ ] Breakpoint indicator shows the correct label as you resize
- [ ] Navbar links are hidden on mobile, visible on md+
- [ ] Hamburger is visible on mobile, hidden on md+
- [ ] Hero stacks on mobile (`flex-col`), side by side on desktop (`md:flex-row`)
- [ ] Hero heading scales: `text-3xl sm:text-4xl md:text-5xl lg:text-6xl`
- [ ] Card grid: 1 col on mobile, 2 on sm, 3 on lg
- [ ] Footer: 1 col on mobile, 2 on md, 4 on lg
- [ ] No horizontal scrollbar at any viewport width

## Bonus Challenges

- Make the hamburger button actually toggle the mobile menu using JavaScript
- Add `xl:grid-cols-4` to the card grid for a 4th column on large screens
- Make the hero image section `hidden md:block` so it only shows on desktop
- Add `sticky top-0 z-50 bg-white/95 backdrop-blur-sm` to the navbar
