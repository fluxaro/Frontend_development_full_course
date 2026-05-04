# Notes — CSS Nesting

## Quick Reference

```css
.parent {
  color: red;

  /* Descendant */
  .child { color: blue; }

  /* & = parent selector */
  &:hover { color: green; }
  &.active { font-weight: bold; }
  &--modifier { background: blue; }

  /* Nested media query */
  @media (min-width: 768px) {
    font-size: 1.5rem;
  }
}
```

## BEM with Nesting

```css
.block {
  &__element { }
  &__element--modifier { }
  &--modifier { }
}
```

## Common Patterns

```css
/* Button states */
.btn {
  background: blue;
  &:hover  { background: darkblue; }
  &:active { transform: scale(0.98); }
  &:disabled { opacity: 0.4; cursor: not-allowed; }
}

/* Responsive */
.hero {
  font-size: 1.5rem;
  @media (min-width: 768px) { font-size: 2.5rem; }
}
```

## Common Mistakes

- Forgetting `&` for pseudo-classes (`:hover` without `&` selects descendants)
- Over-nesting (more than 3 levels deep is hard to read)
- Using nesting for unrelated styles (keep it semantic)
