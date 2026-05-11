# 08 — Responsive Prefixes: sm, md, lg, xl

## What Is This Lesson About?

Tailwind uses a mobile-first responsive system. Every utility can be prefixed with a breakpoint — `sm:`, `md:`, `lg:`, `xl:`, or `2xl:` — to apply it only at that screen size and above. This lesson covers how the breakpoint system works, how to think mobile-first, and how to build layouts that adapt gracefully from phone to desktop.

---

## The Breakpoints

| Prefix | Min-width | Typical device |
|---|---|---|
| *(none)* | 0px | All screens (mobile first) |
| `sm:` | 640px | Large phones, small tablets |
| `md:` | 768px | Tablets |
| `lg:` | 1024px | Laptops |
| `xl:` | 1280px | Desktops |
| `2xl:` | 1536px | Large monitors |

---

## Mobile-First Thinking

Tailwind is **mobile-first**: unprefixed utilities apply to all screen sizes. Prefixed utilities apply at that breakpoint **and above**.

```html
<!-- This text is: small on mobile, medium on tablet, large on desktop -->
<p class="text-sm md:text-base lg:text-lg">Responsive text</p>
```

Think of it as: "start with mobile, then override as the screen gets bigger."

```html
<!-- WRONG way to think about it: -->
<div class="hidden lg:block">  <!-- NOT "hidden on desktop" -->
                               <!-- CORRECT: "hidden everywhere, visible at lg+" -->

<!-- RIGHT: to hide on desktop, show on mobile: -->
<div class="block lg:hidden">  <!-- visible on mobile, hidden at lg+ -->
```

---

## Responsive Layout Patterns

### Stacking to Side-by-Side

```html
<!-- Stack on mobile, side by side on desktop -->
<div class="flex flex-col md:flex-row gap-6">
  <div class="flex-1">Left</div>
  <div class="flex-1">Right</div>
</div>
```

### Responsive Grid

```html
<!-- 1 col → 2 col → 3 col → 4 col -->
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
  <div>Card</div>
</div>
```

### Responsive Sidebar

```html
<!-- Sidebar hidden on mobile, visible on desktop -->
<div class="flex">
  <aside class="hidden lg:block w-64 shrink-0">Sidebar</aside>
  <main class="flex-1">Content</main>
</div>
```

### Responsive Typography

```html
<h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold">
  Big Heading
</h1>
<p class="text-sm md:text-base leading-relaxed md:leading-loose">
  Body text
</p>
```

### Responsive Padding

```html
<section class="px-4 sm:px-6 md:px-8 lg:px-12 py-8 md:py-16 lg:py-24">
  Content
</section>
```

---

## Responsive Visibility

```html
<!-- Show only on mobile -->
<div class="block md:hidden">Mobile only</div>

<!-- Show only on desktop -->
<div class="hidden md:block">Desktop only</div>

<!-- Show on tablet and up -->
<div class="hidden sm:block">Tablet and up</div>

<!-- Show only on tablet (not mobile, not desktop) -->
<div class="hidden sm:block lg:hidden">Tablet only</div>
```

---

## Responsive Flexbox

```html
<!-- Vertical on mobile, horizontal on desktop -->
<nav class="flex flex-col sm:flex-row items-start sm:items-center gap-4">
  <a href="#">Link 1</a>
  <a href="#">Link 2</a>
</nav>

<!-- Wrap on mobile, no wrap on desktop -->
<div class="flex flex-wrap lg:flex-nowrap gap-4">
  <div class="w-full lg:flex-1">Item</div>
</div>
```

---

## Responsive Spacing

```html
<!-- Tighter on mobile, more spacious on desktop -->
<div class="p-4 md:p-8 lg:p-12">
<div class="gap-4 md:gap-6 lg:gap-8">
<div class="mb-8 md:mb-16 lg:mb-24">
```

---

## Responsive Images and Sizes

```html
<!-- Full width on mobile, fixed width on desktop -->
<img class="w-full md:w-96 lg:w-auto" src="photo.jpg" alt="">

<!-- Different aspect ratios -->
<div class="aspect-square md:aspect-video">
```

---

## Breakpoint Indicator (Dev Tool)

A useful trick during development — show the current breakpoint:

```html
<div class="fixed bottom-4 right-4 z-50 bg-black text-white text-xs font-mono px-3 py-1.5 rounded-full">
  <span class="sm:hidden">xs</span>
  <span class="hidden sm:inline md:hidden">sm</span>
  <span class="hidden md:inline lg:hidden">md</span>
  <span class="hidden lg:inline xl:hidden">lg</span>
  <span class="hidden xl:inline 2xl:hidden">xl</span>
  <span class="hidden 2xl:inline">2xl</span>
</div>
```

---

## Common Patterns Table

| Pattern | Classes |
|---|---|
| Stack → row | `flex-col md:flex-row` |
| 1 → 2 → 3 columns | `grid-cols-1 md:grid-cols-2 lg:grid-cols-3` |
| Hide on mobile | `hidden md:block` |
| Hide on desktop | `block md:hidden` |
| Responsive text | `text-2xl md:text-4xl lg:text-6xl` |
| Responsive padding | `p-4 md:p-8 lg:p-16` |
| Sidebar layout | `hidden lg:block w-64` + `flex-1` |
| Full → fixed width | `w-full md:w-auto` |

---

## Common Mistakes

- Thinking `lg:hidden` means "hidden on large screens" — it means "hidden at lg and above"
- Not starting mobile-first — adding `sm:` to everything when you should start with the mobile style
- Using `md:flex-row` without `flex-col` first — the default is `flex-row`, so you need to set `flex-col` for mobile
- Forgetting to test at actual breakpoints — always resize the browser or use DevTools device mode
- Using fixed pixel widths instead of responsive utilities — `w-96` doesn't adapt, `w-full md:w-96` does
