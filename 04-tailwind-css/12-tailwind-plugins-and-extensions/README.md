# 12 — Tailwind Plugins and Extensions

## What Is This Lesson About?

Tailwind's plugin system lets you extend the framework with additional utilities, components, and base styles. The official plugins add commonly needed features like rich typography, form styling, and aspect ratios. The VS Code extension makes writing Tailwind dramatically faster with autocomplete.

---

## Official Plugins

### @tailwindcss/typography

Adds the `prose` class — a beautiful set of typographic defaults for HTML content you don't control (blog posts, markdown, CMS content):

```html
<article class="prose lg:prose-xl">
  <h1>Article Title</h1>
  <p>This paragraph gets beautiful default styling automatically.</p>
  <ul>
    <li>List items look great</li>
    <li>No custom CSS needed</li>
  </ul>
</article>
```

Prose modifiers: `prose-sm`, `prose-base`, `prose-lg`, `prose-xl`, `prose-2xl`

Dark mode: `prose-invert` (white text on dark backgrounds)

### @tailwindcss/forms

Resets browser form styles so inputs look consistent and are easy to style:

```html
<input type="text" class="border border-gray-300 rounded-lg px-3 py-2 w-full focus:ring-2 focus:ring-blue-500 focus:border-transparent">
```

Without this plugin, browser default form styles are hard to override consistently.

### @tailwindcss/aspect-ratio

Adds `aspect-*` utilities for maintaining aspect ratios:

```html
<div class="aspect-video bg-gray-200">
  <!-- 16:9 ratio -->
</div>
<div class="aspect-square bg-gray-200">
  <!-- 1:1 ratio -->
</div>
```

---

## Installing Plugins (CLI project)

```bash
npm install -D @tailwindcss/typography @tailwindcss/forms
```

```js
// tailwind.config.js
module.exports = {
  plugins: [
    require('@tailwindcss/typography'),
    require('@tailwindcss/forms'),
  ],
}
```

---

## VS Code Extension — Tailwind CSS IntelliSense

Install from the VS Code marketplace: **Tailwind CSS IntelliSense** by Tailwind Labs.

Features:
- **Autocomplete** — suggests class names as you type
- **Hover preview** — shows the CSS a class generates
- **Linting** — warns about invalid or conflicting classes
- **Class sorting** — works with Prettier plugin

This extension is essential for productive Tailwind development.

---

## Prettier Plugin

```bash
npm install -D prettier-plugin-tailwindcss
```

Automatically sorts Tailwind classes in a consistent order. Add to `.prettierrc`:

```json
{
  "plugins": ["prettier-plugin-tailwindcss"]
}
```

---

## Common Mistakes

- Installing plugins but forgetting to add them to `tailwind.config.js`
- Using `prose` without the typography plugin installed
- Not installing the VS Code IntelliSense extension (makes Tailwind much harder)
- Using CDN in production (plugins don't work with the CDN)
