# Notes — Container Queries

## Quick Reference

```css
/* 1. Define container */
.wrapper {
  container-type: inline-size;
  container-name: card;
}

/* 2. Query the container */
@container (min-width: 400px) {
  .card { display: flex; }
}

/* Named container */
@container card (min-width: 400px) {
  .card { display: flex; }
}
```

## Container Units

```css
cqw  /* 1% of container width */
cqh  /* 1% of container height */
cqi  /* 1% of container inline size */
cqb  /* 1% of container block size */
```

## vs Media Queries

| | Media Query | Container Query |
|---|---|---|
| Responds to | Viewport | Container |
| Good for | Page layout | Components |
| Reusable | No | Yes |

## Common Mistakes

- Forgetting `container-type` on the parent
- Querying the container from inside itself (must be on parent)
- Using `container-type: size` when `inline-size` is enough
