# Notes — CSS Performance

## will-change

```css
/* Tell browser to prepare for animation */
.card { will-change: transform; }
.modal { will-change: opacity; }

/* Remove after animation */
.card.animated { will-change: auto; }
```

**Use sparingly** — creates a new compositing layer (uses GPU memory).

## contain

```css
/* Isolate layout calculations */
.card { contain: layout; }

/* Isolate paint */
.card { contain: paint; }

/* Isolate both */
.card { contain: layout paint; }

/* Strict containment */
.card { contain: strict; }

/* Content containment (most common) */
.card { contain: content; }
```

## content-visibility

```css
/* Skip rendering off-screen elements */
.card { content-visibility: auto; }

/* Provide estimated size to prevent layout shift */
.card {
  content-visibility: auto;
  contain-intrinsic-size: 0 300px;
}
```

## Performance Rules

1. Animate only `transform` and `opacity`
2. Use `will-change` sparingly (only when needed)
3. Use `contain: content` on independent components
4. Use `content-visibility: auto` for long lists
5. Avoid animating `width`, `height`, `top`, `left`

## Common Mistakes

- Using `will-change` on everything (wastes GPU memory)
- Not removing `will-change` after animation
- Animating layout-triggering properties
- Not using `contain` on isolated components
