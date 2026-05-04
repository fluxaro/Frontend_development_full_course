# Notes — Flexbox Item Properties

## Quick Reference

```css
.item {
  flex-grow: 0;      /* how much to grow (default: 0) */
  flex-shrink: 1;    /* how much to shrink (default: 1) */
  flex-basis: auto;  /* initial size (default: auto) */
  flex: 0 1 auto;    /* shorthand: grow shrink basis */
  align-self: auto;  /* override align-items */
  order: 0;          /* visual order (default: 0) */
}
```

## flex Shorthand

```css
flex: 1;          /* flex: 1 1 0 — grow and shrink equally */
flex: auto;       /* flex: 1 1 auto */
flex: none;       /* flex: 0 0 auto — don't grow or shrink */
flex: 0 0 250px;  /* fixed 250px, no grow, no shrink */
```

## Common Patterns

```css
/* Sidebar: fixed width */
.sidebar { flex: 0 0 280px; }

/* Main content: fill remaining */
.main { flex: 1; }

/* Equal columns */
.col { flex: 1; }

/* Push last item to end */
.nav-end { margin-left: auto; }
```

## Common Mistakes

- Confusing `flex-grow: 0` (don't grow) with `flex-shrink: 0` (don't shrink)
- Using `flex: 1` when you want a fixed size (use `flex: 0 0 200px`)
- Forgetting that `flex-basis: 0` is different from `flex-basis: auto`
