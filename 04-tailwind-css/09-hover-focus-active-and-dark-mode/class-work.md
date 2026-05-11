# Class Work — Build Interactive Buttons and a Dark Mode Toggle

## What You Will Build

A page with interactive button variants, hover cards, and a working dark mode toggle — all using Tailwind state variants.

**Time:** 40 minutes  
**Output file:** `state-variants-practice.html`

---

## Step 1 — Boilerplate with Dark Mode Config

Create `state-variants-practice.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>State Variants Practice</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    // Enable class-based dark mode
    tailwind.config = { darkMode: 'class' }
  </script>
</head>
<body class="bg-gray-50 dark:bg-gray-950 text-gray-900 dark:text-white transition-colors duration-300">

  <!-- Content goes here -->

</body>
</html>
```

The `transition-colors duration-300` on `<body>` makes the dark mode switch animate smoothly.

---

## Step 2 — Navbar with Dark Mode Toggle

```html
<nav class="bg-white dark:bg-gray-900 border-b border-gray-200 dark:border-gray-800 px-6 py-4 transition-colors">
  <div class="max-w-4xl mx-auto flex items-center justify-between">

    <span class="font-bold text-lg text-gray-900 dark:text-white">State Variants</span>

    <!-- Dark mode toggle button -->
    <button
      id="darkToggle"
      onclick="document.documentElement.classList.toggle('dark')"
      class="w-10 h-10 rounded-xl bg-gray-100 dark:bg-gray-800 flex items-center justify-center
             hover:bg-gray-200 dark:hover:bg-gray-700
             focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-500
             transition-colors duration-200"
      aria-label="Toggle dark mode"
    >
      <!-- Sun icon (shown in dark mode) -->
      <span class="hidden dark:block text-yellow-400">☀️</span>
      <!-- Moon icon (shown in light mode) -->
      <span class="block dark:hidden text-gray-600">🌙</span>
    </button>

  </div>
</nav>
```

**Test it:** Click the button — the whole page should switch between light and dark.

---

## Step 3 — Button Variants

```html
<section class="max-w-4xl mx-auto px-6 py-12">
  <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">Button States</h2>
  <p class="text-gray-500 dark:text-gray-400 mb-8">Hover, press, focus, and disable each button</p>

  <div class="flex flex-wrap gap-4">

    <!-- Primary -->
    <button class="bg-blue-600 hover:bg-blue-700 active:bg-blue-800 active:scale-95
                   text-white px-5 py-2.5 rounded-xl font-semibold
                   focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-2
                   transition-all duration-150">
      Primary
    </button>

    <!-- Secondary -->
    <button class="bg-gray-100 dark:bg-gray-800 hover:bg-gray-200 dark:hover:bg-gray-700
                   active:bg-gray-300 dark:active:bg-gray-600 active:scale-95
                   text-gray-900 dark:text-white px-5 py-2.5 rounded-xl font-semibold
                   focus:outline-none focus-visible:ring-2 focus-visible:ring-gray-500 focus-visible:ring-offset-2
                   transition-all duration-150">
      Secondary
    </button>

    <!-- Outlined -->
    <button class="border-2 border-blue-600 text-blue-600 dark:text-blue-400 dark:border-blue-400
                   hover:bg-blue-50 dark:hover:bg-blue-950 active:scale-95
                   px-5 py-2.5 rounded-xl font-semibold
                   focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-2
                   transition-all duration-150">
      Outlined
    </button>

    <!-- Danger -->
    <button class="bg-red-600 hover:bg-red-700 active:bg-red-800 active:scale-95
                   text-white px-5 py-2.5 rounded-xl font-semibold
                   focus:outline-none focus-visible:ring-2 focus-visible:ring-red-500 focus-visible:ring-offset-2
                   transition-all duration-150">
      Danger
    </button>

    <!-- Disabled -->
    <button class="bg-blue-600 text-white px-5 py-2.5 rounded-xl font-semibold
                   disabled:opacity-50 disabled:cursor-not-allowed disabled:pointer-events-none"
            disabled>
      Disabled
    </button>

  </div>

  <p class="text-xs text-gray-400 dark:text-gray-600 mt-4 font-mono">
    Tab through the buttons to see focus-visible rings (keyboard only)
  </p>
</section>
```

**What's happening:**
- `active:scale-95` — button shrinks slightly when pressed
- `focus-visible:ring-2` — ring only shows on keyboard focus
- `disabled:opacity-50 disabled:cursor-not-allowed` — visual disabled state

---

## Step 4 — Hover Cards with Group

```html
<section class="max-w-4xl mx-auto px-6 pb-12">
  <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">Hover Cards</h2>
  <p class="text-gray-500 dark:text-gray-400 mb-8">Hover over each card</p>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">

    <div class="group bg-white dark:bg-gray-800 rounded-2xl p-6 shadow-sm border border-gray-100 dark:border-gray-700
                hover:shadow-xl hover:-translate-y-1 transition-all duration-200 cursor-pointer">
      <div class="w-12 h-12 bg-blue-100 dark:bg-blue-900/50 rounded-xl flex items-center justify-center text-2xl mb-4
                  group-hover:scale-110 transition-transform duration-200">
        🎨
      </div>
      <h3 class="font-bold text-gray-900 dark:text-white mb-2 group-hover:text-blue-600 dark:group-hover:text-blue-400 transition-colors">
        Design
      </h3>
      <p class="text-gray-500 dark:text-gray-400 text-sm leading-relaxed">
        Beautiful components that look great out of the box.
      </p>
      <span class="inline-block mt-4 text-blue-600 dark:text-blue-400 text-sm font-semibold
                   opacity-0 group-hover:opacity-100 translate-x-0 group-hover:translate-x-1
                   transition-all duration-200">
        Explore →
      </span>
    </div>

    <div class="group bg-white dark:bg-gray-800 rounded-2xl p-6 shadow-sm border border-gray-100 dark:border-gray-700
                hover:shadow-xl hover:-translate-y-1 transition-all duration-200 cursor-pointer">
      <div class="w-12 h-12 bg-green-100 dark:bg-green-900/50 rounded-xl flex items-center justify-center text-2xl mb-4
                  group-hover:scale-110 transition-transform duration-200">
        ⚡
      </div>
      <h3 class="font-bold text-gray-900 dark:text-white mb-2 group-hover:text-green-600 dark:group-hover:text-green-400 transition-colors">
        Performance
      </h3>
      <p class="text-gray-500 dark:text-gray-400 text-sm leading-relaxed">
        Optimized for speed. Your users will feel the difference.
      </p>
      <span class="inline-block mt-4 text-green-600 dark:text-green-400 text-sm font-semibold
                   opacity-0 group-hover:opacity-100 translate-x-0 group-hover:translate-x-1
                   transition-all duration-200">
        Explore →
      </span>
    </div>

    <div class="group bg-white dark:bg-gray-800 rounded-2xl p-6 shadow-sm border border-gray-100 dark:border-gray-700
                hover:shadow-xl hover:-translate-y-1 transition-all duration-200 cursor-pointer">
      <div class="w-12 h-12 bg-purple-100 dark:bg-purple-900/50 rounded-xl flex items-center justify-center text-2xl mb-4
                  group-hover:scale-110 transition-transform duration-200">
        🔒
      </div>
      <h3 class="font-bold text-gray-900 dark:text-white mb-2 group-hover:text-purple-600 dark:group-hover:text-purple-400 transition-colors">
        Security
      </h3>
      <p class="text-gray-500 dark:text-gray-400 text-sm leading-relaxed">
        Built with security best practices from the ground up.
      </p>
      <span class="inline-block mt-4 text-purple-600 dark:text-purple-400 text-sm font-semibold
                   opacity-0 group-hover:opacity-100 translate-x-0 group-hover:translate-x-1
                   transition-all duration-200">
        Explore →
      </span>
    </div>

  </div>
</section>
```

**What's happening:**
- `group` on the card — enables `group-hover:` on children
- `group-hover:text-blue-600` — title changes color when card is hovered
- `opacity-0 group-hover:opacity-100` — "Explore →" fades in on hover
- `group-hover:translate-x-1` — arrow slides right on hover

---

## Step 5 — Form with Focus States

```html
<section class="max-w-4xl mx-auto px-6 pb-16">
  <h2 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">Form Focus States</h2>
  <p class="text-gray-500 dark:text-gray-400 mb-8">Click or tab into each field</p>

  <div class="bg-white dark:bg-gray-800 rounded-2xl p-8 shadow-sm border border-gray-100 dark:border-gray-700 max-w-md">

    <div class="space-y-5">

      <div>
        <label class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1.5">Email</label>
        <input
          type="email"
          placeholder="you@example.com"
          class="w-full border border-gray-300 dark:border-gray-600 rounded-xl px-4 py-2.5
                 bg-white dark:bg-gray-900 text-gray-900 dark:text-white
                 placeholder-gray-400 dark:placeholder-gray-500
                 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent
                 transition-all duration-150"
        >
      </div>

      <div>
        <label class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1.5">Password</label>
        <input
          type="password"
          placeholder="••••••••"
          class="w-full border border-gray-300 dark:border-gray-600 rounded-xl px-4 py-2.5
                 bg-white dark:bg-gray-900 text-gray-900 dark:text-white
                 placeholder-gray-400 dark:placeholder-gray-500
                 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent
                 transition-all duration-150"
        >
      </div>

      <!-- Custom checkbox using peer -->
      <label class="flex items-center gap-3 cursor-pointer group">
        <input type="checkbox" class="peer sr-only">
        <div class="w-5 h-5 rounded border-2 border-gray-300 dark:border-gray-600
                    peer-checked:bg-blue-600 peer-checked:border-blue-600
                    flex items-center justify-center shrink-0
                    group-hover:border-blue-400 transition-colors duration-150">
          <svg class="w-3 h-3 text-white hidden peer-checked:block" fill="currentColor" viewBox="0 0 20 20">
            <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd"/>
          </svg>
        </div>
        <span class="text-sm text-gray-700 dark:text-gray-300 peer-checked:text-blue-600 dark:peer-checked:text-blue-400 transition-colors">
          Remember me
        </span>
      </label>

      <button class="w-full bg-blue-600 hover:bg-blue-700 active:bg-blue-800 active:scale-[0.98]
                     text-white py-2.5 rounded-xl font-semibold
                     focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-2
                     transition-all duration-150">
        Sign In
      </button>

    </div>
  </div>
</section>
```

---

## Checklist

- [ ] Dark mode toggle switches the page between light and dark
- [ ] Sun icon shows in dark mode, moon icon in light mode
- [ ] Buttons have visible hover, active (press), and focus-visible states
- [ ] Disabled button has reduced opacity and not-allowed cursor
- [ ] Hover cards lift and show "Explore →" on hover
- [ ] Card title changes color on hover using `group-hover:`
- [ ] Form inputs show a blue ring on focus
- [ ] Custom checkbox checks/unchecks and changes color using `peer-checked:`

## Bonus Challenges

- Add a `peer` pattern to show/hide a password strength indicator
- Create a "like" button that toggles between filled and outline heart using JavaScript + `active:scale-125`
- Add `hover:bg-gray-50 dark:hover:bg-gray-700/50` to table rows for a hover highlight effect
- Make the dark mode preference persist using `localStorage`
