# Notes — Responsive Prefixes

## Breakpoints

| Prefix | Min-width | Device |
|---|---|---|
| *(none)* | 0px | Mobile (default) |
| `sm:` | 640px | Large phone / small tablet |
| `md:` | 768px | Tablet |
| `lg:` | 1024px | Laptop |
| `xl:` | 1280px | Desktop |
| `2xl:` | 1536px | Large monitor |

---

## Mobile-First Rule

Unprefixed = all screens. Prefixed = that size **and above**.

```html
<!-- Small on mobile, large on desktop -->
<p class="text-sm lg:text-xl">

<!-- Stack on mobile, row on desktop -->
<div class="flex flex-col md:flex-row">

<!-- Hidden on mobile, visible on desktop -->
<div class="hidden lg:block">

<!-- Visible on mobile, hidden on desktop -->
<div class="block lg:hidden">
```

---

## Responsive Grid

```html
<!-- 1 → 2 → 3 → 4 columns -->
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
```

---

## Responsive Flex

```html
<!-- Stack → side by side -->
<div class="flex flex-col md:flex-row gap-4">

<!-- Wrap on mobile, no wrap on desktop -->
<div class="flex flex-wrap lg:flex-nowrap gap-4">
```

---

## Responsive Visibility

```html
<div class="block md:hidden">   <!-- mobile only -->
<div class="hidden md:block">   <!-- tablet and up -->
<div class="hidden sm:block lg:hidden"> <!-- tablet only -->
```

---

## Responsive Typography

```html
<h1 class="text-3xl md:text-5xl lg:text-7xl font-bold">
<p class="text-sm md:text-base leading-relaxed">
```

---

## Responsive Spacing

```html
<section class="px-4 md:px-8 lg:px-16 py-8 md:py-16">
<div class="gap-4 md:gap-6 lg:gap-8">
<div class="p-4 md:p-8">
```

---

## Breakpoint Indicator (Dev Helper)

```html
<div class="fixed bottom-4 right-4 bg-black text-white text-xs font-mono px-3 py-1.5 rounded-full z-50">
  <span class="sm:hidden">xs</span>
  <span class="hidden sm:inline md:hidden">sm</span>
  <span class="hidden md:inline lg:hidden">md</span>
  <span class="hidden lg:inline xl:hidden">lg</span>
  <span class="hidden xl:inline 2xl:hidden">xl</span>
  <span class="hidden 2xl:inline">2xl</span>
</div>
```

---

## Common Patterns

```html
<!-- Responsive sidebar layout -->
<div class="flex">
  <aside class="hidden lg:block w-64 shrink-0">Sidebar</aside>
  <main class="flex-1 min-w-0">Content</main>
</div>

<!-- Responsive hero -->
<section class="flex flex-col md:flex-row items-center gap-8 py-16 px-4 md:px-8">

<!-- Responsive card grid -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">

<!-- Responsive navbar -->
<nav class="flex flex-col sm:flex-row items-start sm:items-center justify-between">
```

---

## Common Mistakes

- `lg:hidden` = hidden at lg+, NOT "hidden on large screens only"
- Not setting mobile style first — `md:flex-row` needs `flex-col` for mobile
- Forgetting to test at actual breakpoints
- Using fixed widths instead of responsive ones
