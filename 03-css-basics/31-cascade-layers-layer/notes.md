# Notes — Cascade Layers

## Quick Reference

```css
/* Define order */
@layer reset, base, components, utilities;

/* Define layer content */
@layer components {
  .btn { background: blue; }
}

/* Import into layer */
@import url('lib.css') layer(framework);
```

## Priority Order

Later layers win. Unlayered styles win over all layers.

```
unlayered > utilities > components > base > reset
```

## Common Pattern

```css
@layer reset, base, components, utilities;

@layer reset { /* CSS reset */ }
@layer base { /* body, typography */ }
@layer components { /* buttons, cards */ }
@layer utilities { /* .hidden, .sr-only */ }
```

## Common Mistakes

- Not defining layer order at the top (order is determined by first appearance)
- Forgetting that unlayered styles beat all layers
- Using layers when specificity is enough
