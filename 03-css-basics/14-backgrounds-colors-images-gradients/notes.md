# Notes — Backgrounds

## Quick Reference

```css
background-color: #3498db;
background-image: url('image.jpg');
background-size: cover | contain | 100% | 300px;
background-position: center | top left | 50% 50%;
background-repeat: no-repeat | repeat | repeat-x;
background-attachment: scroll | fixed | local;
background-clip: border-box | padding-box | content-box | text;
background-origin: border-box | padding-box | content-box;
```

## Gradients

```css
/* Linear */
background: linear-gradient(to right, #3498db, #9b59b6);
background: linear-gradient(135deg, #667eea, #764ba2);

/* Radial */
background: radial-gradient(circle, #3498db, #1a1a2e);

/* Conic */
background: conic-gradient(from 0deg, red, yellow, green, red);

/* Repeating */
background: repeating-linear-gradient(
  45deg, #f0f0f0 0px, #f0f0f0 10px, white 10px, white 20px
);
```

## Multiple Backgrounds

```css
background:
  url('overlay.png') center/cover no-repeat,
  linear-gradient(to bottom, #1a1a2e, #2c3e50);
```

## Hero Pattern

```css
.hero {
  background:
    linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
    url('hero.jpg') center/cover no-repeat;
  color: white;
}
```

## Common Mistakes

- Forgetting `background-size: cover` for full-cover images
- Not adding a fallback `background-color` for images
- Using `background-attachment: fixed` on mobile (performance issue)
