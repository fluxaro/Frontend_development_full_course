# 23 — Container Queries (2026)

## What Is This Lesson About?

Container queries let you style elements based on the size of their **container** rather than the viewport. This is a game-changer for component-based design — a card can adapt to its container, not just the screen size.

---

## The Problem with Media Queries

Media queries respond to the viewport. But what if you have a card that appears in a narrow sidebar AND a wide main area? With media queries, you cannot style it differently based on where it is placed.

Container queries solve this.

---

## Enabling Container Queries

```css
/* Step 1: Define a containment context on the parent */
.card-wrapper {
  container-type: inline-size;
  container-name: card;  /* optional name */
}

/* Step 2: Query the container */
@container (min-width: 400px) {
  .card {
    display: flex;
    flex-direction: row;
  }
}
```

---

## container-type Values

```css
container-type: inline-size;  /* query width (most common) */
container-type: size;          /* query width AND height */
container-type: normal;        /* default, no containment */
```

---

## Named Containers

```css
.sidebar { container-type: inline-size; container-name: sidebar; }
.main    { container-type: inline-size; container-name: main; }

/* Target specific container */
@container sidebar (min-width: 300px) { }
@container main (min-width: 600px) { }
```

---

## Container Query Units

```css
/* cqw = 1% of container width */
/* cqh = 1% of container height */
font-size: 5cqw;
padding: 2cqw;
```

---

## Real-World Example

```css
/* Card adapts to its container */
.card-container {
  container-type: inline-size;
}

.card {
  /* Mobile layout: stacked */
  display: grid;
  grid-template-columns: 1fr;
}

@container (min-width: 400px) {
  .card {
    /* Wide container: side by side */
    grid-template-columns: 200px 1fr;
  }
}
```

---

## Browser Support

Container queries are supported in all modern browsers (Chrome 105+, Firefox 110+, Safari 16+). As of 2026, they are safe to use in production.
