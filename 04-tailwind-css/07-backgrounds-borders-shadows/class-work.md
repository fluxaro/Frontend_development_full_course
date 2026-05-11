# Class Work — Build a Glassmorphism Card and Gradient Hero

## What You Will Build

A hero section with a gradient background and a glassmorphism card floating over it, plus a row of polished cards demonstrating different shadow and border techniques.

**Time:** 40 minutes  
**Output file:** `bg-borders-practice.html`

---

## Step 1 — Boilerplate

Create `bg-borders-practice.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Backgrounds, Borders & Shadows</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 text-gray-900">

  <!-- Hero goes here -->
  <!-- Cards go here -->

</body>
</html>
```

---

## Step 2 — Gradient Hero with Glassmorphism Card

Replace the hero comment with:

```html
<!-- GRADIENT HERO -->
<section class="relative bg-gradient-to-br from-indigo-900 via-purple-900 to-pink-800 py-24 px-6 overflow-hidden">

  <!-- Decorative blobs -->
  <div class="absolute top-0 left-0 w-96 h-96 bg-blue-500/20 rounded-full blur-3xl -translate-x-1/2 -translate-y-1/2"></div>
  <div class="absolute bottom-0 right-0 w-96 h-96 bg-pink-500/20 rounded-full blur-3xl translate-x-1/2 translate-y-1/2"></div>

  <div class="relative max-w-5xl mx-auto flex flex-col items-center text-center gap-8">

    <!-- Gradient text heading -->
    <h1 class="text-6xl font-black text-transparent bg-clip-text bg-gradient-to-r from-white via-purple-200 to-pink-200 leading-tight">
      Visual Effects<br>with Tailwind
    </h1>

    <p class="text-purple-200 text-xl max-w-xl leading-relaxed">
      Backgrounds, borders, shadows, and blur — all without writing a single line of CSS.
    </p>

    <!-- GLASSMORPHISM CARD -->
    <div class="backdrop-blur-md bg-white/10 border border-white/20 rounded-2xl p-8 max-w-md w-full shadow-2xl">
      <div class="flex items-center gap-4 mb-4">
        <div class="w-12 h-12 rounded-xl bg-white/20 flex items-center justify-center text-2xl">✨</div>
        <div class="text-left">
          <p class="font-bold text-white">Glassmorphism</p>
          <p class="text-purple-200 text-sm">backdrop-blur-md bg-white/10</p>
        </div>
      </div>
      <p class="text-purple-100 text-sm leading-relaxed text-left">
        This card uses <code class="bg-white/10 px-1.5 py-0.5 rounded text-pink-200 font-mono text-xs">backdrop-blur-md</code> and a semi-transparent white background to create the frosted glass effect.
      </p>
      <button class="mt-6 w-full bg-white/20 hover:bg-white/30 text-white font-semibold py-2.5 rounded-xl transition-colors border border-white/20">
        Learn More
      </button>
    </div>

  </div>
</section>
```

**What's happening:**
- `bg-gradient-to-br from-indigo-900 via-purple-900 to-pink-800` — three-color diagonal gradient
- `blur-3xl` on the decorative blobs — creates soft ambient glow
- `text-transparent bg-clip-text bg-gradient-to-r` — gradient text effect
- `backdrop-blur-md bg-white/10 border border-white/20` — the glassmorphism recipe

---

## Step 3 — Shadow Variants

Replace the cards comment with:

```html
<section class="max-w-5xl mx-auto px-6 py-16">
  <h2 class="text-2xl font-bold text-gray-900 mb-2">Shadow Variants</h2>
  <p class="text-gray-500 mb-8">From subtle to dramatic</p>

  <div class="grid grid-cols-2 md:grid-cols-4 gap-6">

    <div class="bg-white rounded-2xl p-6 shadow-sm text-center">
      <div class="w-10 h-10 bg-gray-100 rounded-xl mx-auto mb-3"></div>
      <p class="font-semibold text-sm text-gray-900">shadow-sm</p>
      <p class="text-xs text-gray-400 mt-1">Subtle lift</p>
    </div>

    <div class="bg-white rounded-2xl p-6 shadow text-center">
      <div class="w-10 h-10 bg-gray-100 rounded-xl mx-auto mb-3"></div>
      <p class="font-semibold text-sm text-gray-900">shadow</p>
      <p class="text-xs text-gray-400 mt-1">Default</p>
    </div>

    <div class="bg-white rounded-2xl p-6 shadow-lg text-center">
      <div class="w-10 h-10 bg-gray-100 rounded-xl mx-auto mb-3"></div>
      <p class="font-semibold text-sm text-gray-900">shadow-lg</p>
      <p class="text-xs text-gray-400 mt-1">Elevated</p>
    </div>

    <div class="bg-white rounded-2xl p-6 shadow-2xl text-center">
      <div class="w-10 h-10 bg-gray-100 rounded-xl mx-auto mb-3"></div>
      <p class="font-semibold text-sm text-gray-900">shadow-2xl</p>
      <p class="text-xs text-gray-400 mt-1">Floating</p>
    </div>

  </div>
</section>
```

---

## Step 4 — Colored Shadows

```html
<section class="max-w-5xl mx-auto px-6 pb-16">
  <h2 class="text-2xl font-bold text-gray-900 mb-2">Colored Shadows</h2>
  <p class="text-gray-500 mb-8">shadow-lg shadow-{color}/50</p>

  <div class="flex flex-wrap gap-6">

    <button class="bg-blue-600 text-white px-6 py-3 rounded-xl font-semibold shadow-lg shadow-blue-500/50">
      Blue Shadow
    </button>

    <button class="bg-purple-600 text-white px-6 py-3 rounded-xl font-semibold shadow-lg shadow-purple-500/50">
      Purple Shadow
    </button>

    <button class="bg-green-600 text-white px-6 py-3 rounded-xl font-semibold shadow-lg shadow-green-500/50">
      Green Shadow
    </button>

    <button class="bg-rose-600 text-white px-6 py-3 rounded-xl font-semibold shadow-lg shadow-rose-500/50">
      Rose Shadow
    </button>

    <button class="bg-amber-500 text-white px-6 py-3 rounded-xl font-semibold shadow-lg shadow-amber-400/50">
      Amber Shadow
    </button>

  </div>
</section>
```

---

## Step 5 — Border Variants

```html
<section class="max-w-5xl mx-auto px-6 pb-16">
  <h2 class="text-2xl font-bold text-gray-900 mb-2">Border Variants</h2>
  <p class="text-gray-500 mb-8">Different border styles and colors</p>

  <div class="grid grid-cols-2 md:grid-cols-4 gap-4">

    <div class="border border-gray-200 rounded-xl p-5 text-center">
      <p class="text-sm font-semibold text-gray-700">border</p>
      <p class="text-xs text-gray-400 mt-1">1px solid gray-200</p>
    </div>

    <div class="border-2 border-blue-500 rounded-xl p-5 text-center">
      <p class="text-sm font-semibold text-blue-700">border-2</p>
      <p class="text-xs text-gray-400 mt-1">2px solid blue-500</p>
    </div>

    <div class="border-2 border-dashed border-gray-300 rounded-xl p-5 text-center">
      <p class="text-sm font-semibold text-gray-700">border-dashed</p>
      <p class="text-xs text-gray-400 mt-1">Dashed style</p>
    </div>

    <div class="border-2 border-dotted border-purple-400 rounded-xl p-5 text-center">
      <p class="text-sm font-semibold text-purple-700">border-dotted</p>
      <p class="text-xs text-gray-400 mt-1">Dotted style</p>
    </div>

  </div>
</section>
```

---

## Step 6 — Border Radius Scale

```html
<section class="max-w-5xl mx-auto px-6 pb-16">
  <h2 class="text-2xl font-bold text-gray-900 mb-2">Border Radius Scale</h2>
  <p class="text-gray-500 mb-8">From sharp to pill</p>

  <div class="flex flex-wrap items-center gap-4">
    <div class="w-20 h-20 bg-blue-500 rounded-none flex items-center justify-center text-white text-xs font-bold">none</div>
    <div class="w-20 h-20 bg-blue-500 rounded flex items-center justify-center text-white text-xs font-bold">rounded</div>
    <div class="w-20 h-20 bg-blue-500 rounded-lg flex items-center justify-center text-white text-xs font-bold">lg</div>
    <div class="w-20 h-20 bg-blue-500 rounded-xl flex items-center justify-center text-white text-xs font-bold">xl</div>
    <div class="w-20 h-20 bg-blue-500 rounded-2xl flex items-center justify-center text-white text-xs font-bold">2xl</div>
    <div class="w-20 h-20 bg-blue-500 rounded-3xl flex items-center justify-center text-white text-xs font-bold">3xl</div>
    <div class="w-20 h-20 bg-blue-500 rounded-full flex items-center justify-center text-white text-xs font-bold">full</div>
  </div>
</section>
```

---

## Checklist

- [ ] Gradient hero uses at least 3 colors with `from-`, `via-`, `to-`
- [ ] Glassmorphism card uses `backdrop-blur-md bg-white/10 border border-white/20`
- [ ] Gradient text uses `text-transparent bg-clip-text bg-gradient-to-r`
- [ ] Shadow variants show visible difference between `shadow-sm` and `shadow-2xl`
- [ ] Colored shadows use `shadow-{color}/50` syntax
- [ ] Border variants show solid, dashed, and dotted styles
- [ ] Border radius scale shows the progression from sharp to full circle

## Bonus Challenges

- Add a `ring-2 ring-offset-2` focus state to the glassmorphism button
- Create a card with `shadow-inner` to simulate a pressed/inset look
- Add a gradient border using `bg-gradient-to-r` with `p-[2px]` and a white inner div
- Add `hover:shadow-xl hover:-translate-y-1 transition-all` to the shadow cards
