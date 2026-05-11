# Class Work — Extract Button and Card Components

## What You Will Build

A page that demonstrates the concept of `@apply` by showing a "before" (utility-heavy HTML) and "after" (extracted CSS classes) comparison — using a `<style>` block since we're on the CDN.

**Time:** 35 minutes  
**Output file:** `apply-practice.html`

---

## Step 1 — Boilerplate

Create `apply-practice.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>@apply Practice</title>
  <script src="https://cdn.tailwindcss.com"></script>

  <style>
    /*
     * In a real project with a build step (Vite, PostCSS), these would use @apply:
     *
     * .btn { @apply inline-flex items-center justify-center font-semibold rounded-xl transition-all duration-150; }
     * .btn-primary { @apply btn bg-blue-600 hover:bg-blue-700 active:bg-blue-800 text-white px-5 py-2.5; }
     *
     * With the CDN, @apply is NOT supported, so we write the CSS values manually.
     * The concept is identical — we're just skipping the @apply directive.
     */

    /* Base button */
    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-weight: 600;
      border-radius: 0.75rem;
      transition: all 150ms;
      cursor: pointer;
      border: none;
      font-family: inherit;
    }

    /* Button sizes */
    .btn-sm  { padding: 0.375rem 0.75rem;  font-size: 0.875rem; }
    .btn-md  { padding: 0.625rem 1.25rem;  font-size: 0.875rem; }
    .btn-lg  { padding: 0.75rem 1.5rem;    font-size: 1rem; }

    /* Button variants */
    .btn-primary {
      background-color: #2563eb;
      color: white;
    }
    .btn-primary:hover  { background-color: #1d4ed8; }
    .btn-primary:active { background-color: #1e40af; transform: scale(0.97); }

    .btn-secondary {
      background-color: #f3f4f6;
      color: #111827;
    }
    .btn-secondary:hover  { background-color: #e5e7eb; }
    .btn-secondary:active { background-color: #d1d5db; transform: scale(0.97); }

    .btn-danger {
      background-color: #dc2626;
      color: white;
    }
    .btn-danger:hover  { background-color: #b91c1c; }
    .btn-danger:active { transform: scale(0.97); }

    .btn-outline {
      background-color: transparent;
      color: #2563eb;
      border: 2px solid #2563eb;
    }
    .btn-outline:hover { background-color: #eff6ff; }

    /* Card */
    .card {
      background-color: white;
      border-radius: 1rem;
      padding: 1.5rem;
      border: 1px solid #f3f4f6;
      box-shadow: 0 1px 3px rgba(0,0,0,0.06), 0 0 1px rgba(0,0,0,0.06);
    }

    .card-title {
      font-size: 1.125rem;
      font-weight: 700;
      color: #111827;
      margin-bottom: 0.5rem;
    }

    .card-body {
      font-size: 0.875rem;
      color: #6b7280;
      line-height: 1.625;
    }

    /* Input */
    .input {
      width: 100%;
      border: 1px solid #d1d5db;
      border-radius: 0.75rem;
      padding: 0.625rem 1rem;
      font-size: 0.875rem;
      color: #111827;
      background-color: white;
      outline: none;
      transition: all 150ms;
      font-family: inherit;
    }
    .input:focus {
      border-color: transparent;
      box-shadow: 0 0 0 2px #3b82f6;
    }

    /* Badge */
    .badge {
      display: inline-flex;
      align-items: center;
      padding: 0.25rem 0.75rem;
      border-radius: 9999px;
      font-size: 0.75rem;
      font-weight: 600;
    }
    .badge-blue   { background-color: #dbeafe; color: #1d4ed8; }
    .badge-green  { background-color: #dcfce7; color: #15803d; }
    .badge-red    { background-color: #fee2e2; color: #b91c1c; }
    .badge-yellow { background-color: #fef9c3; color: #a16207; }
    .badge-purple { background-color: #f3e8ff; color: #7e22ce; }
  </style>
</head>
<body class="bg-gray-50 text-gray-900 p-8">

  <!-- Content goes here -->

</body>
</html>
```

---

## Step 2 — Before: Utility-Heavy HTML

Add this section inside `<body>`:

```html
<div class="max-w-4xl mx-auto space-y-16">

  <!-- CDN limitation notice -->
  <div class="bg-amber-50 border border-amber-200 rounded-xl p-4 flex gap-3">
    <span class="text-amber-500 text-xl shrink-0">⚠️</span>
    <div>
      <p class="font-semibold text-amber-800 text-sm">CDN Limitation</p>
      <p class="text-amber-700 text-sm mt-1">
        <code class="bg-amber-100 px-1 rounded font-mono">@apply</code> requires a build step and does not work with the Tailwind CDN.
        This demo shows the concept using a <code class="bg-amber-100 px-1 rounded font-mono">&lt;style&gt;</code> block with manual CSS values.
        In a real project with Vite or PostCSS, you would use <code class="bg-amber-100 px-1 rounded font-mono">@apply</code> directly.
      </p>
    </div>
  </div>

  <!-- BEFORE: Utility-heavy HTML -->
  <section>
    <h2 class="text-2xl font-bold text-gray-900 mb-2">Before: Utility-Heavy HTML</h2>
    <p class="text-gray-500 mb-6">Long, repeated utility strings in every element</p>

    <!-- Buttons: long utility strings -->
    <div class="mb-8">
      <h3 class="text-sm font-bold uppercase tracking-widest text-gray-400 mb-4">Buttons</h3>
      <div class="flex flex-wrap gap-3">
        <button class="inline-flex items-center justify-center font-semibold rounded-xl transition-all duration-150 bg-blue-600 hover:bg-blue-700 active:bg-blue-800 text-white px-5 py-2.5 text-sm">
          Save Changes
        </button>
        <button class="inline-flex items-center justify-center font-semibold rounded-xl transition-all duration-150 bg-blue-600 hover:bg-blue-700 active:bg-blue-800 text-white px-5 py-2.5 text-sm">
          Submit Form
        </button>
        <button class="inline-flex items-center justify-center font-semibold rounded-xl transition-all duration-150 bg-blue-600 hover:bg-blue-700 active:bg-blue-800 text-white px-5 py-2.5 text-sm">
          Confirm
        </button>
        <button class="inline-flex items-center justify-center font-semibold rounded-xl transition-all duration-150 bg-gray-100 hover:bg-gray-200 text-gray-900 px-5 py-2.5 text-sm">
          Cancel
        </button>
      </div>
      <p class="text-xs text-gray-400 mt-2 font-mono">Each button has 8+ repeated classes</p>
    </div>

    <!-- Cards: long utility strings -->
    <div class="mb-8">
      <h3 class="text-sm font-bold uppercase tracking-widest text-gray-400 mb-4">Cards</h3>
      <div class="grid grid-cols-3 gap-4">
        <div class="bg-white rounded-2xl p-6 border border-gray-100 shadow-sm">
          <h3 class="text-lg font-bold text-gray-900 mb-2">Card One</h3>
          <p class="text-sm text-gray-500 leading-relaxed">Card description text goes here.</p>
        </div>
        <div class="bg-white rounded-2xl p-6 border border-gray-100 shadow-sm">
          <h3 class="text-lg font-bold text-gray-900 mb-2">Card Two</h3>
          <p class="text-sm text-gray-500 leading-relaxed">Card description text goes here.</p>
        </div>
        <div class="bg-white rounded-2xl p-6 border border-gray-100 shadow-sm">
          <h3 class="text-lg font-bold text-gray-900 mb-2">Card Three</h3>
          <p class="text-sm text-gray-500 leading-relaxed">Card description text goes here.</p>
        </div>
      </div>
    </div>

  </section>
```

---

## Step 3 — After: Extracted Classes

```html
  <!-- AFTER: Extracted CSS classes -->
  <section>
    <h2 class="text-2xl font-bold text-gray-900 mb-2">After: Extracted CSS Classes</h2>
    <p class="text-gray-500 mb-6">Short, semantic class names — same visual result</p>

    <!-- Buttons: short class names -->
    <div class="mb-8">
      <h3 class="text-sm font-bold uppercase tracking-widest text-gray-400 mb-4">Buttons</h3>
      <div class="flex flex-wrap gap-3">
        <button class="btn btn-primary btn-md">Save Changes</button>
        <button class="btn btn-primary btn-md">Submit Form</button>
        <button class="btn btn-primary btn-md">Confirm</button>
        <button class="btn btn-secondary btn-md">Cancel</button>
        <button class="btn btn-danger btn-md">Delete</button>
        <button class="btn btn-outline btn-md">Learn More</button>
      </div>
      <p class="text-xs text-gray-400 mt-2 font-mono">Each button uses 2-3 short class names</p>
    </div>

    <!-- Cards: short class names -->
    <div class="mb-8">
      <h3 class="text-sm font-bold uppercase tracking-widest text-gray-400 mb-4">Cards</h3>
      <div class="grid grid-cols-3 gap-4">
        <div class="card">
          <h3 class="card-title">Card One</h3>
          <p class="card-body">Card description text goes here.</p>
        </div>
        <div class="card">
          <h3 class="card-title">Card Two</h3>
          <p class="card-body">Card description text goes here.</p>
        </div>
        <div class="card">
          <h3 class="card-title">Card Three</h3>
          <p class="card-body">Card description text goes here.</p>
        </div>
      </div>
    </div>

    <!-- Inputs -->
    <div class="mb-8">
      <h3 class="text-sm font-bold uppercase tracking-widest text-gray-400 mb-4">Inputs</h3>
      <div class="grid grid-cols-2 gap-4 max-w-lg">
        <input type="text" placeholder="First name" class="input">
        <input type="text" placeholder="Last name" class="input">
        <input type="email" placeholder="Email address" class="input col-span-2">
      </div>
    </div>

    <!-- Badges -->
    <div>
      <h3 class="text-sm font-bold uppercase tracking-widest text-gray-400 mb-4">Badges</h3>
      <div class="flex flex-wrap gap-2">
        <span class="badge badge-blue">Design</span>
        <span class="badge badge-green">Published</span>
        <span class="badge badge-red">Urgent</span>
        <span class="badge badge-yellow">Pending</span>
        <span class="badge badge-purple">Featured</span>
      </div>
    </div>

  </section>

</div>
```

---

## Checklist

- [ ] CDN limitation notice is visible on the page
- [ ] "Before" section shows long utility strings
- [ ] "After" section uses short class names (`.btn`, `.card`, `.input`, `.badge`)
- [ ] Both sections look visually identical
- [ ] The `<style>` block has comments explaining the `@apply` concept
- [ ] Button variants work: primary, secondary, danger, outline
- [ ] Inputs show a focus ring when clicked
- [ ] Badges use different color variants

## Bonus Challenges

- Add a `.btn-lg` and `.btn-sm` size variant and demonstrate them
- Add a `.card-hover` variant that adds a shadow and lift on hover
- Add a `.badge-outline` variant with a border instead of background
- Write a comment showing what the `@apply` version would look like in a real build setup
