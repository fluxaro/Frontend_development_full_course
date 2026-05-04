# 26 — CSS Transforms: translate, rotate, scale

## What Is This Lesson About?

CSS transforms let you move, rotate, scale, and skew elements without affecting the document flow. They are the most performant way to animate elements.

---

## translate

Moves an element from its current position.

```css
transform: translateX(20px);    /* move right */
transform: translateX(-20px);   /* move left */
transform: translateY(20px);    /* move down */
transform: translateY(-20px);   /* move up */
transform: translate(20px, -10px); /* x and y */
transform: translate(-50%, -50%);  /* relative to own size */
```

---

## scale

Resizes an element.

```css
transform: scale(1.1);     /* 10% larger */
transform: scale(0.9);     /* 10% smaller */
transform: scaleX(1.5);    /* wider */
transform: scaleY(0.5);    /* shorter */
transform: scale(1.1, 0.9); /* x and y */
```

---

## rotate

Rotates an element.

```css
transform: rotate(45deg);    /* clockwise */
transform: rotate(-45deg);   /* counter-clockwise */
transform: rotate(0.5turn);  /* half turn */
transform: rotateX(45deg);   /* 3D rotation */
transform: rotateY(45deg);   /* 3D rotation */
```

---

## skew

Skews an element.

```css
transform: skewX(10deg);
transform: skewY(10deg);
transform: skew(10deg, 5deg);
```

---

## Multiple Transforms

```css
/* Apply multiple transforms */
transform: translateY(-4px) scale(1.02) rotate(2deg);
```

---

## transform-origin

Sets the point around which the transform is applied.

```css
transform-origin: center;      /* default */
transform-origin: top left;
transform-origin: 0 0;
transform-origin: 50% 100%;
```

---

## Centering with transform

```css
.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

---

## Performance

Transforms only trigger compositing — they do NOT cause layout or paint. This makes them the most performant way to animate elements.

Always use `transform: translateX()` instead of `left:` for animations.
