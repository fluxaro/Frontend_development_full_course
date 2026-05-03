# 07 — Images and the Picture Element

## What Is This Lesson About?

Images are one of the most important parts of any webpage. This lesson covers how to add images correctly, write good alt text, use the `<picture>` element for responsive images, and optimize images for performance.

---

## The `<img>` Element

The `<img>` tag embeds an image. It is a self-closing (void) element — it has no closing tag.

```html
<img src="photo.jpg" alt="A golden retriever playing in a park">
```

### Required Attributes

| Attribute | Purpose |
|---|---|
| `src` | The path or URL to the image file |
| `alt` | Alternative text — describes the image for screen readers and when the image fails to load |

### Optional Attributes

| Attribute | Purpose | Example |
|---|---|---|
| `width` | Image width in pixels | `width="800"` |
| `height` | Image height in pixels | `height="600"` |
| `loading` | Lazy loading | `loading="lazy"` |
| `decoding` | Decoding hint | `decoding="async"` |
| `title` | Tooltip on hover | `title="My dog Max"` |

---

## Writing Good Alt Text

Alt text is critical for accessibility and SEO. Screen readers read it aloud for visually impaired users.

**Rules for alt text:**
- Describe what is in the image, not what it looks like
- Be specific and concise
- Do not start with "Image of" or "Photo of" — screen readers already say "image"
- For decorative images, use `alt=""` (empty alt) to tell screen readers to skip it

```html
<!-- Good alt text -->
<img src="dog.jpg" alt="Golden retriever catching a frisbee in a park">

<!-- Bad alt text -->
<img src="dog.jpg" alt="image">
<img src="dog.jpg" alt="dog photo">
<img src="dog.jpg" alt="Image of a dog">

<!-- Decorative image — empty alt -->
<img src="divider.png" alt="">
```

---

## Image Paths

```html
<!-- Same folder -->
<img src="photo.jpg" alt="...">

<!-- Subfolder -->
<img src="images/photo.jpg" alt="...">

<!-- Parent folder -->
<img src="../photo.jpg" alt="...">

<!-- Absolute URL -->
<img src="https://example.com/photo.jpg" alt="...">
```

---

## Lazy Loading

By default, browsers load all images when the page loads. Lazy loading defers off-screen images until the user scrolls to them:

```html
<img src="photo.jpg" alt="..." loading="lazy">
```

Always add `loading="lazy"` to images that are not in the initial viewport (below the fold).

---

## The `<picture>` Element

The `<picture>` element lets you provide multiple image sources. The browser picks the best one based on screen size, resolution, or format support.

```html
<picture>
  <!-- WebP for modern browsers -->
  <source srcset="photo.webp" type="image/webp">
  <!-- JPEG fallback for older browsers -->
  <source srcset="photo.jpg" type="image/jpeg">
  <!-- The img is the final fallback — always required -->
  <img src="photo.jpg" alt="A mountain landscape at sunset">
</picture>
```

### Responsive Images with srcset

```html
<picture>
  <!-- Small screens: use a cropped, portrait version -->
  <source media="(max-width: 600px)" srcset="photo-mobile.jpg">
  <!-- Large screens: use the full landscape version -->
  <source media="(min-width: 601px)" srcset="photo-desktop.jpg">
  <img src="photo-desktop.jpg" alt="A mountain landscape at sunset">
</picture>
```

---

## Image Formats

| Format | Best For | Notes |
|---|---|---|
| JPEG / JPG | Photos | Lossy compression, small file size |
| PNG | Graphics with transparency | Lossless, larger files |
| WebP | Everything | Modern format, 25–35% smaller than JPEG |
| SVG | Icons, logos, illustrations | Vector — scales to any size |
| AVIF | Photos | Newest format, even smaller than WebP |
| GIF | Simple animations | Limited colors, use video instead |

---

## The `<figure>` and `<figcaption>` Elements

Use `<figure>` to group an image with its caption:

```html
<figure>
  <img src="chart.png" alt="Bar chart showing sales growth from 2020 to 2025">
  <figcaption>Figure 1: Annual sales growth, 2020–2025</figcaption>
</figure>
```
