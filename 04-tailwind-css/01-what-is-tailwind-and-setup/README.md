# 01 — What is Tailwind CSS and Setup

## What Is This Lesson About?

Tailwind CSS is a utility-first CSS framework. Instead of writing custom CSS classes like `.card` or `.hero`, you apply small, single-purpose classes directly in your HTML. This lesson covers what Tailwind is, how it differs from traditional CSS, and how to set it up.

---

## Tailwind vs Traditional CSS

| | Traditional CSS | Tailwind |
|---|---|---|
| Where styles live | `.css` file | HTML `class` attribute |
| Class names | You invent them | Pre-defined utilities |
| Context switching | Yes (HTML ↔ CSS) | No |
| Production CSS size | All styles included | Only used classes |
| Naming things | Required | Not needed |
| Onboarding new devs | Must learn your naming | Classes are self-documenting |

---

## Setup Methods

### CDN (Learning Only)

Add this `<script>` tag inside your `<head>`. No install, no build step — works instantly:

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Page</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
```

> ⚠️ The CDN loads the entire Tailwind framework (~3MB). It's great for learning but not for production.

### CLI with Vite (Production)

For real projects, install Tailwind via npm. It tree-shakes unused classes so your final CSS is tiny:

```bash
npm install -D tailwindcss @tailwindcss/vite
```

Then add the Vite plugin to `vite.config.js` and import Tailwind in your main CSS file:

```css
/* main.css */
@import "tailwindcss";
```

---

## How Tailwind Classes Work

Each Tailwind class maps to exactly one CSS property. You compose many classes to build a design:

```html
<div class="bg-white rounded-xl p-6 shadow-md max-w-sm">
  <h2 class="text-xl font-bold text-gray-800 mb-2">Hello Tailwind</h2>
  <p class="text-sm text-gray-500 leading-relaxed">Styled with utility classes only.</p>
</div>
```

What each class does:
- `bg-white` → `background-color: white`
- `rounded-xl` → `border-radius: 0.75rem`
- `p-6` → `padding: 1.5rem`
- `shadow-md` → medium drop shadow
- `max-w-sm` → `max-width: 24rem`
- `text-xl` → `font-size: 1.25rem`
- `font-bold` → `font-weight: 700`
- `text-gray-800` → dark gray text color
- `mb-2` → `margin-bottom: 0.5rem`
- `text-sm` → `font-size: 0.875rem`
- `text-gray-500` → medium gray text
- `leading-relaxed` → `line-height: 1.625`

---

## The Spacing Scale

Tailwind uses a consistent spacing scale where 1 unit = 4px:

| Class | Value |
|---|---|
| `p-1` | 4px |
| `p-2` | 8px |
| `p-4` | 16px (1rem) |
| `p-6` | 24px (1.5rem) |
| `p-8` | 32px (2rem) |
| `p-12` | 48px (3rem) |
| `p-16` | 64px (4rem) |

The same scale applies to `m-*` (margin), `gap-*`, `w-*`, `h-*`, and more.

---

## Common Mistakes

- **Using the CDN in production** — it loads the full framework (~3MB). Use the CLI for real projects.
- **Forgetting the CDN `<script>` tag** — without it, no Tailwind classes will work and the page will look unstyled.
- **Expecting Tailwind to work like Bootstrap** — Tailwind gives you utilities, not pre-built components. You compose the design yourself.
- **Trying to keep class lists short** — long class lists are normal and expected in Tailwind. That's the whole point.
