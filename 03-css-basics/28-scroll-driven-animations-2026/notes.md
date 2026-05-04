# Notes — Scroll-Driven Animations

## Quick Reference

```css
/* Scroll progress bar */
.progress {
  animation: grow linear;
  animation-timeline: scroll(root);
}

/* Fade in on scroll */
.card {
  animation: fadeIn linear;
  animation-timeline: view();
  animation-range: entry 0% entry 60%;
}
```

## animation-timeline Values

```css
animation-timeline: scroll();        /* page scroll */
animation-timeline: scroll(root);    /* root scroll */
animation-timeline: view();          /* element in viewport */
animation-timeline: --my-timeline;   /* named timeline */
```

## animation-range Values

```css
animation-range: entry 0% entry 100%;    /* entering viewport */
animation-range: exit 0% exit 100%;      /* exiting viewport */
animation-range: contain 0% contain 100%; /* fully visible */
animation-range: cover 0% cover 100%;    /* any overlap */
```

## Fallback Pattern

```css
@supports (animation-timeline: view()) {
  .card {
    animation: fadeIn linear;
    animation-timeline: view();
  }
}
```

## Browser Support (2026)

Chrome 115+, Edge 115+, Safari 18+, Firefox 110+
