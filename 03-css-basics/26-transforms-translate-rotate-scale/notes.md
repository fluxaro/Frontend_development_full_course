# Notes — CSS Transforms

## Quick Reference

```css
transform: translateX(20px);
transform: translateY(-10px);
transform: translate(20px, -10px);
transform: scale(1.1);
transform: scaleX(1.5);
transform: rotate(45deg);
transform: skewX(10deg);

/* Multiple transforms */
transform: translateY(-4px) scale(1.02);

/* 3D */
transform: rotateX(45deg);
transform: rotateY(45deg);
transform: perspective(500px) rotateY(30deg);
```

## transform-origin

```css
transform-origin: center;       /* default */
transform-origin: top left;
transform-origin: 50% 50%;
transform-origin: 0 0;
```

## Common Patterns

```css
/* Center with transform */
.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* Hover lift */
.card:hover { transform: translateY(-4px); }

/* Hover scale */
.img:hover { transform: scale(1.05); }

/* Rotate icon */
.arrow.open { transform: rotate(180deg); }
```

## Performance

Transforms only trigger compositing — they are the cheapest CSS property to animate. Always prefer `transform: translateX()` over `left:` for animations.
