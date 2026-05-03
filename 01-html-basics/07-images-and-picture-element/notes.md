# Notes — Images and the Picture Element

## Quick Reference

### Basic Image
```html
<img src="photo.jpg" alt="Description of the image">
```

### Image with Size
```html
<img src="photo.jpg" alt="Description" width="800" height="600">
```

### Lazy Loading
```html
<img src="photo.jpg" alt="Description" loading="lazy">
```

### Picture Element (format fallback)
```html
<picture>
  <source srcset="photo.webp" type="image/webp">
  <img src="photo.jpg" alt="Description">
</picture>
```

### Picture Element (responsive)
```html
<picture>
  <source media="(max-width: 600px)" srcset="photo-small.jpg">
  <source media="(min-width: 601px)" srcset="photo-large.jpg">
  <img src="photo-large.jpg" alt="Description">
</picture>
```

### Figure with Caption
```html
<figure>
  <img src="chart.png" alt="Sales chart">
  <figcaption>Figure 1: Annual sales 2020–2025</figcaption>
</figure>
```

## Alt Text Rules

| Situation | Alt Text |
|---|---|
| Meaningful image | Describe what is in it |
| Decorative image | `alt=""` (empty) |
| Image is a link | Describe the destination |
| Image contains text | Include the text in alt |
| Complex chart | Describe the data |

## Image Formats

| Format | Use For |
|---|---|
| JPEG | Photos |
| PNG | Transparency, screenshots |
| WebP | Everything (modern) |
| SVG | Icons, logos |
| AVIF | Photos (newest, smallest) |

## Common Mistakes

- Missing `alt` attribute (accessibility failure)
- Using `alt="image"` or `alt="photo"` (useless)
- Not specifying `width` and `height` (causes layout shift)
- Not using `loading="lazy"` on below-fold images
- Using PNG for photos (use JPEG or WebP instead)
- Forgetting the `<img>` fallback inside `<picture>`
- Using `<img>` for decorative backgrounds (use CSS instead)

## Performance Tips

- Always specify `width` and `height` to prevent Cumulative Layout Shift (CLS)
- Use `loading="lazy"` for all images below the fold
- Use WebP format when possible (25–35% smaller than JPEG)
- Use `decoding="async"` for non-critical images
- Compress images before uploading (use squoosh.app or tinypng.com)
