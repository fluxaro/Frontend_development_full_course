# Notes — z-index and Stacking Context

## z-index Rules

1. Only works on positioned elements (not `static`)
2. Higher value = on top
3. Negative values go behind normal flow
4. Only meaningful within the same stacking context

## Stacking Context Creators

```css
position + z-index (not auto)
opacity < 1
transform: any
filter: any
will-change: transform/opacity
isolation: isolate
```

## Recommended z-index Scale

```css
:root {
  --z-below:    -1;
  --z-base:      0;
  --z-raised:    1;
  --z-dropdown: 100;
  --z-sticky:   200;
  --z-overlay:  300;
  --z-modal:    400;
  --z-toast:    500;
}
```

## isolation: isolate

```css
.component {
  isolation: isolate;
  /* z-index values inside won't leak out */
}
```

## Common Mistakes

- Using z-index on `position: static` (no effect)
- Using 9999 everywhere (creates z-index wars)
- Not knowing that `opacity < 1` creates a stacking context
- Trying to z-index an element above a sibling that has a higher stacking context
