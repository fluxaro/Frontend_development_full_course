# Class Work — What is Tailwind and Setup

## What You Will Build

A side-by-side comparison page showing the same card built two ways: once with traditional CSS and once with Tailwind. You will set up Tailwind via CDN and write your first utility classes.

**Time:** 35 minutes  
**Output:** `tailwind-setup-practice.html`

---

## Step 1 — Create the File and Add the CDN

Create `tailwind-setup-practice.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tailwind Setup Practice</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    /* Traditional CSS card — for comparison only */
    .traditional-card {
      background: white;
      border-radius: 12px;
      padding: 1.5rem;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      max-width: 320px;
    }
    .traditional-card h2 {
      font-size: 1.25rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
    }
    .traditional-card p {
      color: #6b7280;
      font-size: 0.875rem;
    }
  </style>
</head>
<body class="bg-gray-100 p-8 font-sans">

</body>
</html>
```

**What the CDN does:** The `<script>` tag loads the full Tailwind framework. Every utility class becomes available immediately — no build step needed.

---

## Step 2 — Add a Page Heading

Inside `<body>`, add:

```html
<h1 class="text-2xl font-bold text-gray-800 mb-8">Tailwind vs Traditional CSS</h1>

<div class="flex gap-8 flex-wrap">
  <!-- cards go here -->
</div>
```

**What each class does:**
- `text-2xl` — sets font size to 1.5rem
- `font-bold` — sets font-weight to 700
- `text-gray-800` — dark gray text color
- `mb-8` — margin-bottom of 2rem
- `flex gap-8 flex-wrap` — side-by-side layout with wrapping

---

## Step 3 — Build the Traditional CSS Card

Inside the `<div class="flex gap-8 flex-wrap">`:

```html
<!-- Traditional CSS version -->
<div>
  <p class="text-sm font-semibold text-red-500 mb-2 uppercase tracking-wide">Traditional CSS</p>
  <div class="traditional-card">
    <h2>Alex Rivera</h2>
    <p>Frontend Developer — building things for the web since 2023.</p>
  </div>
</div>
```

---

## Step 4 — Build the Tailwind Card

Right after the traditional card:

```html
<!-- Tailwind version -->
<div>
  <p class="text-sm font-semibold text-green-600 mb-2 uppercase tracking-wide">Tailwind CSS</p>
  <div class="bg-white rounded-xl p-6 shadow-md max-w-xs">
    <h2 class="text-xl font-bold text-gray-800 mb-2">Alex Rivera</h2>
    <p class="text-sm text-gray-500">Frontend Developer — building things for the web since 2023.</p>
  </div>
</div>
```

**What each class does:**
- `bg-white` — white background
- `rounded-xl` — large border radius (12px)
- `p-6` — padding of 1.5rem on all sides
- `shadow-md` — medium drop shadow
- `max-w-xs` — max-width of 20rem (320px)
- `text-xl` — font size 1.25rem
- `font-bold` — font-weight 700
- `text-gray-800` — dark gray text
- `mb-2` — margin-bottom 0.5rem
- `text-sm` — font size 0.875rem
- `text-gray-500` — medium gray text

---

## Step 5 — Add a "What I Learned" Section

Below the flex container:

```html
<div class="mt-12 bg-white rounded-xl p-6 shadow-sm max-w-lg">
  <h2 class="text-lg font-bold text-gray-800 mb-4">Key Takeaways</h2>
  <ul class="space-y-2 text-sm text-gray-600">
    <li>✅ Tailwind classes are applied directly in HTML</li>
    <li>✅ No separate CSS file needed</li>
    <li>✅ Each class does exactly one thing</li>
    <li>✅ The CDN makes it work instantly for learning</li>
  </ul>
</div>
```

---

## Step 6 — Verify It Works

Open the file in your browser and check:

- [ ] The page background is light gray (not white)
- [ ] Both cards look visually similar — same rounded corners, shadow, and padding
- [ ] The Tailwind card has no `<style>` block driving its appearance
- [ ] The heading is large and bold

---

## Checklist

- [ ] CDN `<script>` tag is in the `<head>`
- [ ] Page uses `bg-gray-100` as the body background
- [ ] Traditional card uses a `<style>` block with custom CSS
- [ ] Tailwind card uses only utility classes — no custom CSS
- [ ] Both cards look visually equivalent
- [ ] At least 10 different Tailwind classes used across the page

---

## Bonus Challenges

1. Add a third card using Tailwind with a colored gradient header: `<div class="h-24 bg-gradient-to-r from-blue-500 to-purple-600 rounded-t-xl"></div>`
2. Add a `hover:shadow-xl transition-shadow` to the Tailwind card and observe the hover effect
3. Try removing the CDN `<script>` tag and reload — confirm that all Tailwind styling disappears
