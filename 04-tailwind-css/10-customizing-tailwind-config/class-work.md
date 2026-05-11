# Class Work — Extend Tailwind Config with Brand Colors

## What You Will Build

A branded page using a custom Tailwind config that adds a complete color palette, custom font, custom spacing, and a custom animation — all via the CDN config approach.

**Time:** 40 minutes  
**Output file:** `custom-config-practice.html`

---

## Step 1 — Boilerplate with Config

Create `custom-config-practice.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Custom Config Practice</title>

  <!-- Google Font for custom font-display -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">

  <!-- Tailwind CDN -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Custom config — MUST come after the CDN script -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            brand: {
              50:  '#faf5ff',
              100: '#f3e8ff',
              200: '#e9d5ff',
              300: '#d8b4fe',
              400: '#c084fc',
              500: '#a855f7',
              600: '#9333ea',
              700: '#7e22ce',
              800: '#6b21a8',
              900: '#581c87',
            },
            accent: {
              400: '#fb923c',
              500: '#f97316',
              600: '#ea580c',
            },
            success: '#22c55e',
            danger:  '#ef4444',
          },
          fontFamily: {
            display: ['"Plus Jakarta Sans"', 'sans-serif'],
          },
          spacing: {
            '18': '4.5rem',
            '88': '22rem',
          },
          boxShadow: {
            'glow': '0 0 30px rgba(168, 85, 247, 0.4)',
            'glow-sm': '0 0 15px rgba(168, 85, 247, 0.3)',
          },
          keyframes: {
            'fade-up': {
              '0%': { opacity: '0', transform: 'translateY(20px)' },
              '100%': { opacity: '1', transform: 'translateY(0)' },
            },
            'pulse-glow': {
              '0%, 100%': { boxShadow: '0 0 15px rgba(168, 85, 247, 0.3)' },
              '50%': { boxShadow: '0 0 30px rgba(168, 85, 247, 0.6)' },
            }
          },
          animation: {
            'fade-up': 'fade-up 0.5s ease-out',
            'pulse-glow': 'pulse-glow 2s ease-in-out infinite',
          }
        }
      }
    }
  </script>
</head>
<body class="bg-white text-gray-900 font-display">

  <!-- Content goes here -->

</body>
</html>
```

**What's happening:**
- The config script comes **after** the CDN script — this is required
- `theme.extend` — adds to defaults, doesn't replace them
- `brand` color has 9 shades — enables `bg-brand-50` through `bg-brand-900`
- `font-display` maps to Plus Jakarta Sans
- Custom `shadow-glow` and `animate-fade-up` are now available

---

## Step 2 — Verify the Config Works

Add this test section inside `<body>`:

```html
<!-- Config test: if these look right, the config is working -->
<div class="p-8 space-y-4">
  <div class="bg-brand-500 text-white p-4 rounded-xl font-display font-bold">
    bg-brand-500 + font-display ✓
  </div>
  <div class="bg-brand-100 text-brand-800 p-4 rounded-xl">
    bg-brand-100 text-brand-800 ✓
  </div>
  <div class="shadow-glow bg-white p-4 rounded-xl border border-brand-200">
    shadow-glow ✓
  </div>
  <div class="animate-fade-up bg-accent-500 text-white p-4 rounded-xl">
    animate-fade-up + bg-accent-500 ✓
  </div>
  <div class="p-18 bg-brand-50 rounded-xl text-brand-700 text-sm">
    p-18 (custom spacing: 4.5rem) ✓
  </div>
</div>
```

Open the file and confirm each box looks correct. Then remove this test section.

---

## Step 3 — Build the Navbar

Replace the test section with:

```html
<nav class="bg-brand-900 text-white px-6 py-4">
  <div class="max-w-5xl mx-auto flex items-center justify-between">
    <a href="#" class="font-display font-bold text-xl text-white">
      Violet<span class="text-brand-300">UI</span>
    </a>
    <div class="flex items-center gap-6">
      <a href="#" class="text-brand-300 hover:text-white text-sm font-medium transition-colors">Features</a>
      <a href="#" class="text-brand-300 hover:text-white text-sm font-medium transition-colors">Pricing</a>
      <a href="#" class="bg-brand-500 hover:bg-brand-400 text-white px-4 py-2 rounded-lg text-sm font-semibold transition-colors shadow-glow-sm">
        Get Started
      </a>
    </div>
  </div>
</nav>
```

---

## Step 4 — Build the Hero

```html
<section class="bg-gradient-to-br from-brand-900 via-brand-800 to-brand-700 text-white px-6 py-24">
  <div class="max-w-5xl mx-auto text-center">

    <div class="inline-flex items-center gap-2 bg-brand-700/50 border border-brand-500/30 rounded-full px-4 py-2 mb-8 animate-fade-up">
      <span class="w-2 h-2 bg-accent-400 rounded-full animate-pulse"></span>
      <span class="text-brand-200 text-sm font-medium">Now in public beta</span>
    </div>

    <h1 class="font-display text-5xl md:text-7xl font-extrabold leading-tight mb-6 animate-fade-up">
      Build with
      <span class="text-transparent bg-clip-text bg-gradient-to-r from-brand-300 to-accent-400">
        Violet UI
      </span>
    </h1>

    <p class="text-brand-200 text-xl leading-relaxed max-w-2xl mx-auto mb-10 animate-fade-up">
      A complete design system built on custom Tailwind config. Every color, font, and shadow is defined in the config — not hardcoded.
    </p>

    <div class="flex flex-col sm:flex-row gap-4 justify-center animate-fade-up">
      <a href="#" class="bg-brand-500 hover:bg-brand-400 text-white px-8 py-3.5 rounded-xl font-semibold text-lg shadow-glow hover:shadow-glow transition-all animate-pulse-glow">
        Start building
      </a>
      <a href="#" class="bg-white/10 hover:bg-white/20 border border-white/20 text-white px-8 py-3.5 rounded-xl font-semibold text-lg transition-all">
        View docs
      </a>
    </div>

  </div>
</section>
```

---

## Step 5 — Feature Cards

```html
<section class="max-w-5xl mx-auto px-6 py-16">
  <h2 class="font-display text-3xl font-bold text-brand-900 text-center mb-12">
    Why Violet UI?
  </h2>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">

    <div class="bg-brand-50 rounded-2xl p-6 border border-brand-100">
      <div class="w-12 h-12 bg-brand-500 rounded-xl flex items-center justify-center text-white text-2xl mb-4">🎨</div>
      <h3 class="font-display font-bold text-brand-900 text-lg mb-2">Custom Colors</h3>
      <p class="text-brand-700 text-sm leading-relaxed">
        A complete 9-shade palette defined in config. Use <code class="bg-brand-100 px-1 rounded text-brand-800 font-mono text-xs">bg-brand-500</code> anywhere.
      </p>
    </div>

    <div class="bg-accent-500 rounded-2xl p-6 text-white">
      <div class="w-12 h-12 bg-white/20 rounded-xl flex items-center justify-center text-2xl mb-4">✨</div>
      <h3 class="font-display font-bold text-lg mb-2">Custom Animations</h3>
      <p class="text-orange-100 text-sm leading-relaxed">
        Keyframes defined in config. Use <code class="bg-white/10 px-1 rounded font-mono text-xs">animate-fade-up</code> on any element.
      </p>
    </div>

    <div class="bg-white rounded-2xl p-6 border border-brand-200 shadow-glow-sm">
      <div class="w-12 h-12 bg-brand-100 rounded-xl flex items-center justify-center text-2xl mb-4">🔧</div>
      <h3 class="font-display font-bold text-brand-900 text-lg mb-2">Custom Shadows</h3>
      <p class="text-brand-700 text-sm leading-relaxed">
        This card uses <code class="bg-brand-50 px-1 rounded text-brand-800 font-mono text-xs">shadow-glow-sm</code> — a custom shadow defined in config.
      </p>
    </div>

  </div>
</section>
```

---

## Checklist

- [ ] Config script comes **after** the CDN script
- [ ] `theme.extend` is used (not `theme`)
- [ ] `bg-brand-*` classes work with all defined shades
- [ ] `font-display` applies the custom Google Font
- [ ] `shadow-glow` is visible on the hero button
- [ ] `animate-fade-up` plays on page load
- [ ] `p-18` applies the custom spacing (4.5rem)
- [ ] The page looks cohesive — all colors come from the custom palette

## Bonus Challenges

- Add a `darkMode: 'class'` to the config and create dark variants for all brand colors
- Define a custom `borderRadius` value like `'brand': '0.625rem'` and use it
- Add a `3xl` breakpoint at `1920px` and use it for a wider layout
- Create a CSS variable-based color that can be swapped at runtime
