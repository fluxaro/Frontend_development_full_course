# Notes — Backgrounds, Borders, and Shadows

## Background Color

```html
bg-white        bg-black        bg-transparent
bg-gray-{50-950}
bg-blue-{50-950}
bg-red-{50-950}
bg-green-{50-950}
bg-purple-{50-950}
```

---

## Gradients

```html
<!-- Direction -->
bg-gradient-to-r    bg-gradient-to-l
bg-gradient-to-b    bg-gradient-to-t
bg-gradient-to-br   bg-gradient-to-bl
bg-gradient-to-tr   bg-gradient-to-tl

<!-- Colors -->
from-blue-500   via-purple-500   to-pink-500

<!-- Gradient text -->
<h1 class="text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-purple-600">
```

---

## Background Image

```html
bg-cover        <!-- fill container -->
bg-contain      <!-- fit inside container -->
bg-center       <!-- center position -->
bg-top          <!-- top position -->
bg-no-repeat    <!-- don't tile -->
```

---

## Border Width

```html
border      <!-- 1px all sides -->
border-2    <!-- 2px all sides -->
border-4    <!-- 4px all sides -->
border-0    <!-- remove border -->
border-t    border-b    border-l    border-r
border-x    border-y
```

---

## Border Color & Style

```html
border-gray-200     border-blue-500     border-transparent
border-solid        border-dashed       border-dotted
```

---

## Border Radius

| Class | Radius |
|---|---|
| `rounded-sm` | 2px |
| `rounded` | 4px |
| `rounded-md` | 6px |
| `rounded-lg` | 8px |
| `rounded-xl` | 12px |
| `rounded-2xl` | 16px |
| `rounded-3xl` | 24px |
| `rounded-full` | 9999px |

```html
rounded-t-xl    <!-- top corners -->
rounded-b-lg    <!-- bottom corners -->
rounded-tl-2xl  <!-- top-left only -->
```

---

## Box Shadow

```html
shadow-none   shadow-sm   shadow   shadow-md
shadow-lg     shadow-xl   shadow-2xl   shadow-inner

<!-- Colored shadow -->
shadow-lg shadow-blue-500/50
```

---

## Ring (Outline Shadow)

```html
ring        <!-- 3px ring -->
ring-1      ring-2      ring-4
ring-blue-500   ring-offset-2
focus:ring-2 focus:ring-blue-500 focus:outline-none
```

---

## Opacity

```html
opacity-0    opacity-25    opacity-50    opacity-75    opacity-100

<!-- Background opacity only (preferred) -->
bg-blue-600/50    bg-black/40    bg-white/20
```

---

## Backdrop Blur

```html
backdrop-blur-none   backdrop-blur-sm   backdrop-blur
backdrop-blur-md     backdrop-blur-lg   backdrop-blur-xl
```

---

## Common Patterns

```html
<!-- Standard card -->
<div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6">

<!-- Glassmorphism -->
<div class="backdrop-blur-md bg-white/10 border border-white/20 rounded-2xl p-6">

<!-- Gradient hero -->
<section class="bg-gradient-to-br from-indigo-900 to-purple-900">

<!-- Colored shadow button -->
<button class="bg-blue-600 shadow-lg shadow-blue-500/50 rounded-xl px-6 py-3">

<!-- Dark overlay -->
<div class="absolute inset-0 bg-black/50">
```

---

## Common Mistakes

- `shadow` invisible on transparent backgrounds — need `bg-white` or similar
- Forgetting `overflow-hidden` on rounded containers
- `opacity-50` affects text too — use `bg-blue-600/50` for background only
- `backdrop-blur` needs a semi-transparent background to show the blur effect
