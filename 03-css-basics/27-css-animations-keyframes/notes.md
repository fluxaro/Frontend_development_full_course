# Notes — CSS Animations

## Quick Reference

```css
@keyframes name {
  from { /* start */ }
  to   { /* end */ }
}

@keyframes name {
  0%   { /* start */ }
  50%  { /* middle */ }
  100% { /* end */ }
}

.element {
  animation: name duration timing delay count direction fill-mode;
  animation: fadeIn 0.5s ease 0.2s 1 normal forwards;
}
```

## Common Keyframes

```css
@keyframes fadeIn    { from { opacity: 0; } to { opacity: 1; } }
@keyframes slideUp   { from { transform: translateY(20px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
@keyframes spin      { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
@keyframes pulse     { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.05); } }
@keyframes shake     { 0%, 100% { transform: translateX(0); } 25% { transform: translateX(-8px); } 75% { transform: translateX(8px); } }
```

## Stagger Pattern

```css
.card:nth-child(1) { animation-delay: 0s; }
.card:nth-child(2) { animation-delay: 0.1s; }
.card:nth-child(3) { animation-delay: 0.2s; }
```

## Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
  }
}
```
