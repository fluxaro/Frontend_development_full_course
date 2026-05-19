# Notes — Tailwind Plugins and Extensions

## Official Plugins Quick Reference

| Plugin | What it adds | Key class |
|---|---|---|
| `@tailwindcss/typography` | Beautiful prose styles | `prose` |
| `@tailwindcss/forms` | Consistent form resets | (automatic) |
| `@tailwindcss/aspect-ratio` | Aspect ratio utilities | `aspect-video`, `aspect-square` |

## Typography Plugin

```html
<!-- Basic prose -->
<article class="prose">...</article>

<!-- Size variants -->
<article class="prose prose-sm">...</article>
<article class="prose prose-lg">...</article>
<article class="prose prose-xl">...</article>

<!-- Dark mode -->
<article class="prose prose-invert">...</article>

<!-- Custom color -->
<article class="prose prose-blue">...</article>
```

## Aspect Ratio

```html
<div class="aspect-video">   <!-- 16:9 -->
<div class="aspect-square">  <!-- 1:1 -->
<div class="aspect-[4/3]">   <!-- custom -->
```

## Install (CLI)

```bash
npm install -D @tailwindcss/typography @tailwindcss/forms
```

```js
// tailwind.config.js
plugins: [
  require('@tailwindcss/typography'),
  require('@tailwindcss/forms'),
]
```

## CDN (learning only)

```html
<script src="https://cdn.tailwindcss.com?plugins=typography,forms"></script>
```

## VS Code Extension

- Name: **Tailwind CSS IntelliSense**
- Publisher: Tailwind Labs
- Features: autocomplete, hover preview, linting

## Common Mistakes

- Forgetting to add plugins to `tailwind.config.js` after installing
- Using `prose` without the typography plugin
- Not using the VS Code extension — makes Tailwind much slower to write
