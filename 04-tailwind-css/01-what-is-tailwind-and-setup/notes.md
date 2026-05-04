# Notes — What is Tailwind and Setup

## Quick Reference

```html
<!-- CDN (learning only) -->
<script src="https://cdn.tailwindcss.com"></script>

<!-- CLI install (production) -->
npm install -D tailwindcss @tailwindcss/vite

<!-- Basic usage -->
<div class="bg-white rounded-xl p-6 shadow-md">
  <h1 class="text-2xl font-bold text-gray-800">Hello</h1>
  <p class="text-gray-500 mt-2">Styled with utility classes only.</p>
</div>
```

## What is Tailwind CSS?

Tailwind is a **utility-first CSS framework**. Instead of writing custom CSS classes like `.card` or `.hero`, you apply small, single-purpose classes directly in your HTML.

- Each class does exactly one thing: `text-lg` sets font size, `p-4` sets padding, `bg-blue-500` sets background color
- No separate CSS file needed for most styling
- No inventing class names

## Tailwind vs Traditional CSS

| | Traditional CSS | Tailwind |
|---|---|---|
| Where styles live | `.css` file | HTML `class` attribute |
| Class names | You invent them | Pre-defined utilities |
| Context switching | Yes (HTML ↔ CSS) | No |
| Production CSS size | All styles included | Only used classes |

## Setup Methods

**CDN — for learning:**
```html
<script src="https://cdn.tailwindcss.com"></script>
```
No install, no build step. Works instantly. Not for production — loads the full framework.

**CLI / Vite — for real projects:**
```bash
npm install -D tailwindcss @tailwindcss/vite
```
Tree-shakes unused classes. Tiny output. Supports `tailwind.config.js` customization.

## Common Mistakes

- Using the CDN in a production project (it loads the entire framework, ~3MB)
- Forgetting to add the CDN `<script>` tag when learning
- Expecting Tailwind to work without any setup or CDN link
- Confusing Tailwind with Bootstrap — Tailwind gives you utilities, not pre-built components
