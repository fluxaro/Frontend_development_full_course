# Notes — CSS Accessibility and Reduced Motion

## prefers-reduced-motion

```css
/* Default: animations on */
.btn { transition: transform 0.3s ease; }
.btn:hover { transform: translateY(-2px); }

/* Reduced motion: remove animations */
@media (prefers-reduced-motion: reduce) {
  .btn { transition: none; }
  .btn:hover { transform: none; }
}

/* Or: disable all animations globally */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

## Focus Styles

```css
/* Never remove focus outlines */
:focus-visible {
  outline: 2px solid #3498db;
  outline-offset: 2px;
}

/* Remove only for mouse users */
:focus:not(:focus-visible) {
  outline: none;
}
```

## Color Contrast

WCAG AA requirements:
- Normal text: 4.5:1 ratio
- Large text (18px+ or 14px+ bold): 3:1 ratio
- UI components: 3:1 ratio

## Skip Links

```css
.skip-link {
  position: absolute;
  top: -100%;
  left: 0;
  padding: 8px 16px;
  background: #3498db;
  color: white;
  z-index: 1000;
}

.skip-link:focus { top: 0; }
```

## Common Mistakes

- Removing focus outlines with `outline: none`
- Using color alone to convey information
- Animations without reduced-motion fallback
- Low contrast text
