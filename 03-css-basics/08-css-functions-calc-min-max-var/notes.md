# Notes — CSS Functions

## Quick Reference

```css
/* calc: mix units */
width: calc(100% - 40px);
height: calc(100vh - 64px);

/* min: smallest value */
width: min(50%, 600px);

/* max: largest value */
width: max(300px, 50%);

/* clamp: min, preferred, max */
font-size: clamp(1rem, 2.5vw, 2rem);

/* var: custom property */
color: var(--primary);
color: var(--primary, #3498db);  /* with fallback */
```

## CSS Custom Properties Pattern

```css
:root {
  /* Colors */
  --color-primary: #3498db;
  --color-secondary: #2ecc71;
  --color-danger: #e74c3c;

  /* Spacing */
  --space-1: 0.25rem;
  --space-2: 0.5rem;
  --space-4: 1rem;
  --space-8: 2rem;

  /* Typography */
  --font-sm: 0.875rem;
  --font-base: 1rem;
  --font-lg: 1.25rem;
  --font-xl: 1.5rem;

  /* Layout */
  --nav-height: 64px;
  --max-width: 1200px;
  --border-radius: 8px;
}
```

## Common Patterns

```css
/* Centered container */
.container {
  width: min(1200px, 100% - 2rem);
  margin-inline: auto;
}

/* Full height minus nav */
.page {
  min-height: calc(100dvh - var(--nav-height));
}

/* Fluid spacing */
padding: clamp(1rem, 5vw, 3rem);
```

## Common Mistakes

- Forgetting spaces around `+` and `-` in `calc()` (required!)
- Using `var()` before defining the custom property
- Defining custom properties inside a component instead of `:root`
- Not providing fallback values for `var()`
