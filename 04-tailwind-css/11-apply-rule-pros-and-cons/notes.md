# Notes — @apply Rule

## What It Does

`@apply` extracts Tailwind utilities into a CSS class (requires build step):

```css
/* In your CSS file (requires PostCSS/Vite build) */
.btn-primary {
  @apply bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-lg font-semibold;
}
```

```html
<!-- In your HTML -->
<button class="btn-primary">Click me</button>
```

---

## CDN Limitation

**`@apply` does NOT work with the CDN.** It requires a build step.

With CDN, simulate it manually:

```html
<style>
  /* Manual extraction — no @apply needed -->
  .btn-primary {
    background-color: #2563eb;
    color: white;
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    font-weight: 600;
  }
</style>
```

---

## When to Use @apply ✅

```css
/* 1. Highly repeated components (50+ uses) */
.btn { @apply inline-flex items-center font-semibold rounded-lg transition-all; }
.btn-primary { @apply btn bg-blue-600 hover:bg-blue-700 text-white; }

/* 2. Base HTML element styles */
h1 { @apply text-4xl font-bold tracking-tight; }
p  { @apply text-base leading-relaxed text-gray-600; }

/* 3. Third-party/CMS content you can't add classes to */
.prose h2 { @apply text-2xl font-bold text-gray-900 mb-4; }
.prose p  { @apply text-base leading-relaxed mb-4; }
```

---

## When NOT to Use @apply ❌

```css
/* ❌ One-off styles — just use utilities in HTML */
.hero-title { @apply text-5xl font-bold; }

/* ❌ Recreating CSS abstractions */
.card { @apply bg-white rounded-xl p-6 shadow; }
.card-header { @apply font-bold text-lg; }

/* ❌ Everything — defeats utility-first purpose */
```

---

## Pros vs Cons

| Pros | Cons |
|---|---|
| Reduces repetition | Hides styles from HTML |
| Good for base element styles | Requires build step |
| Works for CMS/third-party content | Encourages over-abstraction |
| | Loses "scan HTML" benefit |

---

## Alternatives (Preferred)

```jsx
// 1. React/Vue component (best approach)
function Button({ variant }) {
  return <button className={`px-4 py-2 rounded-lg ${variants[variant]}`}>

// 2. Template partials (Jinja, Nunjucks)
{% macro button(text) %}<button class="px-4 py-2 ...">{{ text }}</button>{% endmacro %}

// 3. JavaScript utility function
const btn = (variant) => `px-4 py-2 rounded-lg ${variantClasses[variant]}`
```

---

## Tailwind Team's Recommendation

> Avoid `@apply` for most things. Write utilities in HTML. Extract to components (React/Vue). Use `@apply` only for base styles and truly global patterns.

---

## Common Mistakes

- Using `@apply` with CDN — won't work
- Using `@apply` for every component — defeats utility-first
- Creating deep CSS hierarchies — same problems as traditional CSS
- Forgetting `@apply` extracts CSS values, not class names
