# 11 — The @apply Rule: Pros and Cons

## What Is This Lesson About?

`@apply` is a Tailwind directive that lets you use utility classes inside a CSS rule. It's a way to extract repeated utility combinations into a reusable class. This lesson covers when `@apply` is useful, when it's harmful, and what alternatives exist — including why many experienced Tailwind developers avoid it.

---

## What @apply Does

```css
/* Without @apply — repeated utilities in HTML */
/* <button class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-lg font-semibold"> */

/* With @apply — extracted to a CSS class */
.btn-primary {
  @apply bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-lg font-semibold;
}
```

Now you can write `<button class="btn-primary">` instead of the full utility string.

---

## CDN Limitation

**`@apply` does not work with the CDN version of Tailwind.** It requires a build step (PostCSS, Vite, etc.) to process the CSS.

With the CDN, you can simulate the concept using a `<style>` block, but the actual `@apply` directive won't work:

```html
<!-- This does NOT work with CDN -->
<style>
  .btn { @apply bg-blue-600 text-white px-4 py-2 rounded-lg; }
</style>

<!-- This DOES work — manual extraction without @apply -->
<style>
  .btn {
    background-color: #2563eb;
    color: white;
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
  }
</style>
```

In a real project with a build step, `@apply` works as expected.

---

## When @apply Makes Sense

### 1. Highly repeated component classes

```css
/* Good use: a button used 50+ times across the codebase */
.btn {
  @apply inline-flex items-center justify-center font-semibold rounded-lg transition-all duration-150;
  @apply focus:outline-none focus-visible:ring-2 focus-visible:ring-offset-2;
}

.btn-primary {
  @apply btn bg-blue-600 hover:bg-blue-700 active:bg-blue-800 text-white;
  @apply focus-visible:ring-blue-500;
}

.btn-secondary {
  @apply btn bg-gray-100 hover:bg-gray-200 text-gray-900;
  @apply focus-visible:ring-gray-400;
}
```

### 2. Third-party HTML you can't control

```css
/* Styling markdown output or CMS content */
.prose h1 { @apply text-3xl font-bold text-gray-900 mb-4; }
.prose p  { @apply text-base text-gray-600 leading-relaxed mb-4; }
.prose a  { @apply text-blue-600 hover:underline; }
```

### 3. Base styles for HTML elements

```css
/* In a global stylesheet */
h1 { @apply text-4xl font-bold tracking-tight; }
h2 { @apply text-2xl font-semibold; }
a  { @apply text-blue-600 hover:underline; }
```

---

## When @apply Is a Bad Idea

### 1. One-off styles

```css
/* ❌ Don't do this for a single element */
.hero-title {
  @apply text-5xl font-bold text-gray-900;
}
```

Just write the utilities in the HTML. Creating a class for a single use defeats the purpose.

### 2. Recreating CSS abstractions

```css
/* ❌ This is just writing CSS with extra steps */
.card {
  @apply bg-white rounded-xl p-6 shadow-sm border border-gray-100;
}
.card-header {
  @apply font-bold text-lg text-gray-900 mb-4;
}
.card-body {
  @apply text-gray-600 text-sm leading-relaxed;
}
```

If you're building a component system, use a component framework (React, Vue, etc.) instead.

### 3. Losing the benefits of utility-first

The whole point of utility-first CSS is that you can see all styles in the HTML. `@apply` hides styles in a CSS file, making you jump between files to understand what a component looks like.

---

## Pros and Cons

| Pros | Cons |
|---|---|
| Reduces repetition for truly shared components | Hides styles from HTML — harder to understand at a glance |
| Works well for base HTML element styles | Requires a build step (no CDN support) |
| Good for third-party/CMS content | Encourages over-abstraction |
| Keeps HTML clean for heavily reused patterns | Loses the "scan HTML to understand styles" benefit |
| | Creates specificity issues if not careful |

---

## Alternatives to @apply

### 1. Component extraction (preferred in frameworks)

```jsx
// React component — reuse the component, not the CSS
function Button({ children, variant = 'primary' }) {
  const styles = {
    primary: 'bg-blue-600 hover:bg-blue-700 text-white',
    secondary: 'bg-gray-100 hover:bg-gray-200 text-gray-900',
  }
  return (
    <button className={`px-4 py-2 rounded-lg font-semibold ${styles[variant]}`}>
      {children}
    </button>
  )
}
```

### 2. Template partials (in templating engines)

```html
<!-- Jinja2, Nunjucks, etc. -->
{% macro button(text, variant='primary') %}
  <button class="px-4 py-2 rounded-lg font-semibold
    {% if variant == 'primary' %}bg-blue-600 text-white{% endif %}">
    {{ text }}
  </button>
{% endmacro %}
```

### 3. CSS custom properties for theming

```css
:root {
  --btn-bg: theme('colors.blue.600');
  --btn-text: white;
}
.btn {
  background-color: var(--btn-bg);
  color: var(--btn-text);
  @apply px-4 py-2 rounded-lg font-semibold;
}
```

---

## The Tailwind Team's Recommendation

The Tailwind documentation itself recommends **avoiding `@apply` for most cases**. The preferred approach is:

1. Write utilities directly in HTML
2. Extract repeated patterns into components (React, Vue, etc.)
3. Use `@apply` only for base styles and truly global patterns

---

## Common Mistakes

- Using `@apply` for every component — defeats the purpose of utility-first
- Trying to use `@apply` with the CDN — it won't work
- Using `@apply` with `hover:` and `focus:` variants without understanding they work differently in some PostCSS setups
- Creating deep CSS hierarchies with `@apply` — you end up with the same specificity problems as traditional CSS
- Forgetting that `@apply` extracts the CSS values, not the class names — you lose responsive and state variants in some configurations
