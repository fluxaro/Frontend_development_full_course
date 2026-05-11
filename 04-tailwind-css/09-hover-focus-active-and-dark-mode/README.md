# 09 — Hover, Focus, Active, and Dark Mode

## What Is This Lesson About?

Tailwind's state variants let you apply styles conditionally based on user interaction or system preferences. Instead of writing `:hover`, `:focus`, and `@media (prefers-color-scheme: dark)` in CSS, you prefix any utility with `hover:`, `focus:`, `active:`, or `dark:`. This lesson covers every state variant and shows you how to build interactive, accessible, dark-mode-ready UIs.

---

## Hover

```html
<button class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-lg">
  Hover me
</button>

<a class="text-gray-600 hover:text-gray-900 hover:underline">Link</a>

<div class="opacity-80 hover:opacity-100 transition-opacity">Fade in on hover</div>

<div class="shadow-sm hover:shadow-xl transition-shadow">Card lifts on hover</div>
```

---

## Focus

```html
<!-- Input with visible focus ring -->
<input class="border border-gray-300 rounded-lg px-3 py-2 outline-none focus:border-blue-500 focus:ring-2 focus:ring-blue-500/20">

<!-- Button focus state -->
<button class="bg-blue-600 text-white px-4 py-2 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2">
  Focusable button
</button>
```

---

## Focus Visible

`focus-visible:` only applies when the element is focused via keyboard (not mouse click). This is the accessible way to handle focus styles.

```html
<button class="focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-2">
  Keyboard-accessible button
</button>
```

---

## Active

```html
<button class="bg-blue-600 hover:bg-blue-700 active:bg-blue-800 active:scale-95 text-white px-4 py-2 rounded-lg transition-all">
  Press me
</button>
```

---

## Disabled

```html
<button class="bg-blue-600 text-white px-4 py-2 rounded-lg disabled:opacity-50 disabled:cursor-not-allowed" disabled>
  Disabled button
</button>
```

---

## Group Hover

`group` + `group-hover:` lets a parent's hover state affect child elements.

```html
<div class="group bg-white rounded-xl p-6 shadow-sm hover:shadow-xl transition-shadow cursor-pointer">
  <h3 class="text-gray-900 group-hover:text-blue-600 transition-colors font-bold">Card Title</h3>
  <p class="text-gray-500 text-sm mt-2">Card description</p>
  <span class="text-blue-600 opacity-0 group-hover:opacity-100 transition-opacity text-sm font-medium">
    Read more →
  </span>
</div>
```

---

## Peer

`peer` + `peer-*` lets a sibling's state affect another element. Useful for form validation and custom checkboxes.

```html
<!-- Show error message when input is invalid -->
<input class="peer border rounded-lg px-3 py-2 invalid:border-red-500" type="email" required>
<p class="hidden peer-invalid:block text-red-500 text-sm mt-1">Please enter a valid email</p>

<!-- Custom checkbox -->
<label class="flex items-center gap-3 cursor-pointer">
  <input type="checkbox" class="peer sr-only">
  <div class="w-5 h-5 border-2 border-gray-300 rounded peer-checked:bg-blue-600 peer-checked:border-blue-600 flex items-center justify-center">
    <svg class="w-3 h-3 text-white hidden peer-checked:block" fill="currentColor" viewBox="0 0 20 20">
      <path d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"/>
    </svg>
  </div>
  <span class="text-gray-700">Accept terms</span>
</label>
```

---

## Dark Mode

Tailwind's dark mode uses the `dark:` prefix. By default it responds to the OS `prefers-color-scheme` setting. You can also enable class-based dark mode in `tailwind.config.js`.

### OS-based dark mode (default)

```html
<div class="bg-white dark:bg-gray-900 text-gray-900 dark:text-white">
  Adapts to system preference
</div>
```

### Class-based dark mode (toggle with JavaScript)

Add `darkMode: 'class'` to your config, then toggle the `dark` class on `<html>`:

```html
<script>
  tailwind.config = { darkMode: 'class' }
</script>

<button onclick="document.documentElement.classList.toggle('dark')">
  Toggle Dark Mode
</button>

<div class="bg-white dark:bg-gray-900">...</div>
```

### Dark mode patterns

```html
<!-- Background -->
<body class="bg-white dark:bg-gray-950">

<!-- Text -->
<h1 class="text-gray-900 dark:text-white">
<p class="text-gray-600 dark:text-gray-400">

<!-- Card -->
<div class="bg-white dark:bg-gray-800 border border-gray-100 dark:border-gray-700 rounded-xl p-6">

<!-- Input -->
<input class="bg-white dark:bg-gray-800 border-gray-300 dark:border-gray-600 text-gray-900 dark:text-white">

<!-- Button -->
<button class="bg-blue-600 hover:bg-blue-700 dark:bg-blue-500 dark:hover:bg-blue-600 text-white">
```

---

## Combining State Variants

You can combine multiple variants:

```html
<!-- Dark mode + hover -->
<a class="text-gray-600 dark:text-gray-400 hover:text-gray-900 dark:hover:text-white">

<!-- Responsive + hover -->
<div class="p-4 md:p-6 hover:shadow-lg md:hover:shadow-xl">

<!-- Group hover + dark mode -->
<div class="group">
  <h3 class="group-hover:text-blue-600 dark:group-hover:text-blue-400">
```

---

## Transition Utilities

Always pair state variants with transitions for smooth animations:

| Class | CSS |
|---|---|
| `transition` | `transition-property: color, background-color, border-color, ...` |
| `transition-all` | all properties |
| `transition-colors` | color properties only |
| `transition-opacity` | opacity only |
| `transition-shadow` | box-shadow only |
| `transition-transform` | transform only |
| `duration-150` | 150ms |
| `duration-300` | 300ms |
| `ease-in-out` | ease-in-out timing |

```html
<button class="bg-blue-600 hover:bg-blue-700 transition-colors duration-200">
<div class="opacity-0 hover:opacity-100 transition-opacity duration-300">
<div class="scale-100 hover:scale-105 transition-transform duration-200">
```

---

## Common Mistakes

- Forgetting `transition-*` — state changes are instant without it
- Using `focus:` instead of `focus-visible:` — `focus:` shows rings on mouse clicks too, which is visually noisy
- Not pairing `dark:` with a light mode style — `dark:text-white` without `text-gray-900` means no color on light mode
- Using `group-hover:` without adding `group` to the parent element
- Forgetting `outline-none` when adding custom `focus:ring-*` — the browser default outline will show alongside your ring
