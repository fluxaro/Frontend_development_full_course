# Class Work — Build a Pricing Card with Utilities

## What You Will Build

A pricing card component built entirely with Tailwind utility classes. You will practice composing utilities for spacing, color, typography, borders, and shadows.

**Time:** 30 minutes  
**Output:** `pricing-card.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pricing Card</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="min-h-screen bg-gray-100 flex items-center justify-center p-8 font-sans">

  <!-- Cards go here -->

</body>
</html>
```

---

## Step 2 — Build the Free Card

Inside `<body>`, add:

```html
<div class="flex flex-wrap gap-6 justify-center">

  <!-- Free Plan -->
  <div class="bg-white rounded-2xl border border-gray-200 shadow-sm p-8 w-72">
    <h3 class="text-lg font-bold text-gray-800 mb-1">Free</h3>
    <p class="text-sm text-gray-400 mb-6">Perfect for getting started</p>

    <div class="flex items-end gap-1 mb-6">
      <span class="text-4xl font-extrabold text-gray-900">$0</span>
      <span class="text-gray-400 text-sm mb-1">/month</span>
    </div>

    <ul class="space-y-3 mb-8">
      <li class="flex items-center gap-2 text-sm text-gray-600">
        <span class="text-green-500 font-bold">✓</span> 10 projects
      </li>
      <li class="flex items-center gap-2 text-sm text-gray-600">
        <span class="text-green-500 font-bold">✓</span> Community support
      </li>
      <li class="flex items-center gap-2 text-sm text-gray-400">
        <span class="text-gray-300 font-bold">✗</span> Priority support
      </li>
      <li class="flex items-center gap-2 text-sm text-gray-400">
        <span class="text-gray-300 font-bold">✗</span> Custom domain
      </li>
    </ul>

    <button class="w-full border-2 border-gray-200 text-gray-700 font-semibold py-3 rounded-xl hover:border-gray-300 transition-colors text-sm">
      Get Started Free
    </button>
  </div>
```

**What each class does:**
- `rounded-2xl` — large border radius (1rem)
- `border border-gray-200` — subtle 1px border
- `shadow-sm` — very subtle shadow
- `p-8` — 2rem padding on all sides
- `w-72` — fixed width of 18rem
- `space-y-3` — 0.75rem gap between list items
- `flex items-end gap-1` — align price and "/month" to bottom

---

## Step 3 — Build the Pro Card (Featured)

Right after the Free card, still inside the flex container:

```html
  <!-- Pro Plan (featured) -->
  <div class="bg-blue-600 rounded-2xl shadow-xl p-8 w-72 relative">

    <!-- Popular badge -->
    <div class="absolute -top-3 left-1/2 -translate-x-1/2 bg-yellow-400 text-yellow-900 text-xs font-bold px-4 py-1 rounded-full">
      MOST POPULAR
    </div>

    <h3 class="text-lg font-bold text-white mb-1">Pro</h3>
    <p class="text-sm text-blue-200 mb-6">For serious developers</p>

    <div class="flex items-end gap-1 mb-6">
      <span class="text-4xl font-extrabold text-white">$29</span>
      <span class="text-blue-200 text-sm mb-1">/month</span>
    </div>

    <ul class="space-y-3 mb-8">
      <li class="flex items-center gap-2 text-sm text-blue-100">
        <span class="text-green-300 font-bold">✓</span> Unlimited projects
      </li>
      <li class="flex items-center gap-2 text-sm text-blue-100">
        <span class="text-green-300 font-bold">✓</span> Priority support
      </li>
      <li class="flex items-center gap-2 text-sm text-blue-100">
        <span class="text-green-300 font-bold">✓</span> Custom domain
      </li>
      <li class="flex items-center gap-2 text-sm text-blue-100">
        <span class="text-green-300 font-bold">✓</span> Analytics dashboard
      </li>
    </ul>

    <button class="w-full bg-white text-blue-600 font-bold py-3 rounded-xl hover:bg-blue-50 transition-colors text-sm">
      Start Pro Trial
    </button>
  </div>

</div>
```

**New classes introduced:**
- `relative` — creates positioning context for the badge
- `absolute -top-3 left-1/2 -translate-x-1/2` — centers badge above the card
- `bg-yellow-400 text-yellow-900` — yellow badge with dark text
- `shadow-xl` — large shadow for the featured card

---

## Step 4 — Verify

Open in browser and check:
- [ ] Free card has a white background with subtle border
- [ ] Pro card has a blue background
- [ ] "MOST POPULAR" badge floats above the Pro card
- [ ] Both cards are the same width
- [ ] Checkmarks are green, X marks are gray

---

## Checklist

- [ ] CDN script tag in `<head>`
- [ ] No custom CSS written — utilities only
- [ ] Free card: white bg, border, shadow-sm
- [ ] Pro card: blue bg, shadow-xl, relative positioning
- [ ] Badge uses absolute positioning
- [ ] Both cards have consistent spacing using `p-8`, `mb-6`, `space-y-3`

---

## Bonus Challenges

1. Add a third "Team" card at `$99/month` with a dark (`bg-gray-900`) background
2. Add `hover:scale-105 transition-transform` to each card and observe the hover effect
3. Make the layout responsive: stack cards vertically on mobile using `flex-col sm:flex-row`
