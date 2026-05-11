# 07 — Backgrounds, Borders, and Shadows

## What Is This Lesson About?

Tailwind gives you a complete set of utilities for backgrounds, borders, border radius, shadows, rings, and visual effects like backdrop blur and gradients. These are the classes that make your UI look polished and professional. This lesson covers every utility in this category and shows you how to combine them to build beautiful cards, buttons, and hero sections.

---

## Background Color — `bg-*`

```html
<div class="bg-white">White background</div>
<div class="bg-gray-100">Light gray</div>
<div class="bg-blue-600">Blue</div>
<div class="bg-transparent">Transparent</div>
```

Every color in Tailwind's palette is available: `bg-{color}-{shade}` where shade goes from 50 (lightest) to 950 (darkest).

---

## Background Gradients

| Class | CSS |
|---|---|
| `bg-gradient-to-r` | `background-image: linear-gradient(to right, ...)` |
| `bg-gradient-to-br` | diagonal, top-left to bottom-right |
| `bg-gradient-to-b` | top to bottom |
| `bg-gradient-to-l` | right to left |
| `from-{color}` | gradient start color |
| `via-{color}` | gradient middle color |
| `to-{color}` | gradient end color |

```html
<!-- Simple two-color gradient -->
<div class="bg-gradient-to-r from-blue-500 to-purple-600">
  Gradient background
</div>

<!-- Three-color gradient -->
<div class="bg-gradient-to-br from-pink-500 via-red-500 to-yellow-500">
  Sunset gradient
</div>

<!-- Gradient text -->
<h1 class="text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-purple-600 text-5xl font-black">
  Gradient Text
</h1>
```

---

## Background Size and Position

| Class | CSS |
|---|---|
| `bg-cover` | `background-size: cover` |
| `bg-contain` | `background-size: contain` |
| `bg-auto` | `background-size: auto` |
| `bg-center` | `background-position: center` |
| `bg-top` | `background-position: top` |
| `bg-no-repeat` | `background-repeat: no-repeat` |

```html
<div class="bg-cover bg-center bg-no-repeat h-64" style="background-image: url('photo.jpg')">
  Image background
</div>
```

---

## Border Width

| Class | CSS |
|---|---|
| `border` | `border-width: 1px` |
| `border-2` | `border-width: 2px` |
| `border-4` | `border-width: 4px` |
| `border-8` | `border-width: 8px` |
| `border-0` | `border-width: 0px` |
| `border-t` | top border only |
| `border-b` | bottom border only |
| `border-l` | left border only |
| `border-r` | right border only |
| `border-x` | left + right |
| `border-y` | top + bottom |

---

## Border Color

```html
<div class="border border-gray-200">Light gray border</div>
<div class="border-2 border-blue-500">Blue border</div>
<div class="border border-transparent">Invisible border (useful for hover states)</div>
```

---

## Border Style

| Class | CSS |
|---|---|
| `border-solid` | `border-style: solid` (default) |
| `border-dashed` | `border-style: dashed` |
| `border-dotted` | `border-style: dotted` |
| `border-double` | `border-style: double` |
| `border-none` | `border-style: none` |

---

## Border Radius — `rounded-*`

| Class | CSS |
|---|---|
| `rounded-none` | `border-radius: 0` |
| `rounded-sm` | `border-radius: 0.125rem` |
| `rounded` | `border-radius: 0.25rem` |
| `rounded-md` | `border-radius: 0.375rem` |
| `rounded-lg` | `border-radius: 0.5rem` |
| `rounded-xl` | `border-radius: 0.75rem` |
| `rounded-2xl` | `border-radius: 1rem` |
| `rounded-3xl` | `border-radius: 1.5rem` |
| `rounded-full` | `border-radius: 9999px` (pill/circle) |

```html
<button class="rounded-lg px-4 py-2">Slightly rounded</button>
<button class="rounded-full px-6 py-2">Pill button</button>
<div class="rounded-2xl p-6">Card with large radius</div>
<img class="rounded-full w-12 h-12" src="avatar.jpg" alt="Avatar">
```

You can also target specific corners:

```html
<div class="rounded-t-xl">   <!-- top corners only -->
<div class="rounded-b-lg">   <!-- bottom corners only -->
<div class="rounded-tl-2xl"> <!-- top-left only -->
```

---

## Box Shadow — `shadow-*`

| Class | CSS |
|---|---|
| `shadow-none` | no shadow |
| `shadow-sm` | subtle shadow |
| `shadow` | default shadow |
| `shadow-md` | medium shadow |
| `shadow-lg` | large shadow |
| `shadow-xl` | extra large shadow |
| `shadow-2xl` | very large shadow |
| `shadow-inner` | inset shadow |

```html
<div class="shadow-sm">Subtle lift</div>
<div class="shadow-md">Card shadow</div>
<div class="shadow-xl">Modal shadow</div>
<div class="shadow-inner">Inset shadow (pressed look)</div>
```

Colored shadows (Tailwind v3+):

```html
<button class="shadow-lg shadow-blue-500/50 bg-blue-600 text-white px-6 py-3 rounded-xl">
  Colored shadow
</button>
```

---

## Ring — `ring-*`

Rings are box-shadows that look like outlines. They're perfect for focus states.

| Class | CSS |
|---|---|
| `ring` | `box-shadow: 0 0 0 3px ...` |
| `ring-1` | 1px ring |
| `ring-2` | 2px ring |
| `ring-4` | 4px ring |
| `ring-{color}` | ring color |
| `ring-offset-2` | gap between element and ring |

```html
<button class="ring-2 ring-blue-500 ring-offset-2">Focused button</button>
<input class="focus:ring-2 focus:ring-blue-500 focus:outline-none border rounded-lg px-3 py-2">
```

---

## Backdrop Blur

| Class | CSS |
|---|---|
| `backdrop-blur-none` | no blur |
| `backdrop-blur-sm` | slight blur |
| `backdrop-blur` | default blur |
| `backdrop-blur-md` | medium blur |
| `backdrop-blur-lg` | large blur |
| `backdrop-blur-xl` | extra large blur |

```html
<!-- Glassmorphism card -->
<div class="backdrop-blur-md bg-white/20 border border-white/30 rounded-2xl p-6">
  Glass card
</div>
```

---

## Opacity — `opacity-*` and `bg-opacity-*`

```html
<div class="bg-blue-600 opacity-50">50% opacity (affects everything)</div>
<div class="bg-blue-600/50">50% background opacity only (modern syntax)</div>
<div class="bg-black/40 text-white">Dark overlay with 40% opacity</div>
```

---

## Real-World Patterns

### Card

```html
<div class="bg-white rounded-2xl shadow-sm border border-gray-100 p-6">
  Card content
</div>
```

### Glassmorphism Card

```html
<div class="relative overflow-hidden rounded-2xl">
  <!-- Background -->
  <div class="absolute inset-0 bg-gradient-to-br from-blue-600 to-purple-700"></div>
  <!-- Glass card -->
  <div class="relative backdrop-blur-md bg-white/10 border border-white/20 rounded-2xl p-8 text-white">
    Glass card content
  </div>
</div>
```

### Gradient Hero

```html
<section class="bg-gradient-to-br from-indigo-900 via-purple-900 to-pink-900 text-white py-24 px-6">
  <h1 class="text-6xl font-black text-transparent bg-clip-text bg-gradient-to-r from-white to-purple-200">
    Hero Title
  </h1>
</section>
```

---

## Common Mistakes

- Using `shadow` without `bg-white` — shadows are invisible on transparent backgrounds
- Forgetting `overflow-hidden` on rounded containers — child elements can bleed outside the radius
- Using `opacity-50` when you only want the background to be transparent — use `bg-blue-600/50` instead
- Using `ring` and `border` together without understanding they stack
- Forgetting `backdrop-blur` requires a semi-transparent background to be visible
