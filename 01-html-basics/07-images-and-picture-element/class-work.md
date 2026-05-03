# Class Work — Build a Photo Gallery Page

## What You Will Build

A photo gallery page that demonstrates all the ways to use images in HTML: basic images, alt text, lazy loading, the picture element, and figure/figcaption.

**Time:** 40 minutes

---

## Step 1 — Set Up the Page

Create a file called `photo-gallery.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nature Photo Gallery</title>
  </head>
  <body>
    <h1>Nature Photo Gallery</h1>
    <p>A collection of nature photographs demonstrating proper HTML image usage.</p>
  </body>
</html>
```

---

## Step 2 — Add a Basic Image

We will use images from Unsplash (free, no attribution required for learning):

```html
<h2>Basic Image</h2>

<img
  src="https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=800"
  alt="Snow-capped mountain peaks reflected in a calm alpine lake at sunrise"
  width="800"
  height="533"
>
```

**What to notice:**
- `alt` describes what is actually in the image
- `width` and `height` are specified to prevent layout shift
- The description is specific, not generic

---

## Step 3 — Add a Lazy-Loaded Image

```html
<h2>Lazy Loaded Image</h2>
<p>This image only loads when you scroll to it:</p>

<img
  src="https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=800"
  alt="Sunlight filtering through a dense forest of tall trees"
  width="800"
  height="533"
  loading="lazy"
>
```

---

## Step 4 — Add a Figure with Caption

```html
<h2>Figure with Caption</h2>

<figure>
  <img
    src="https://images.unsplash.com/photo-1518020382113-a7e8fc38eac9?w=800"
    alt="A red fox sitting in a snowy field, looking directly at the camera"
    width="800"
    height="533"
    loading="lazy"
  >
  <figcaption>
    A red fox (<em>Vulpes vulpes</em>) photographed in Yellowstone National Park, January 2024.
    Photo by <a href="https://unsplash.com" target="_blank" rel="noopener noreferrer">Unsplash</a>.
  </figcaption>
</figure>
```

---

## Step 5 — Add a Picture Element with Format Fallback

```html
<h2>Picture Element — Format Fallback</h2>
<p>Modern browsers will use WebP. Older browsers fall back to JPEG.</p>

<picture>
  <!-- WebP for modern browsers (smaller file size) -->
  <source
    srcset="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=800&fm=webp"
    type="image/webp"
  >
  <!-- JPEG fallback for older browsers -->
  <img
    src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=800"
    alt="A humpback whale breaching the ocean surface at sunset"
    width="800"
    height="533"
    loading="lazy"
  >
</picture>
```

---

## Step 6 — Add a Picture Element for Responsive Images

```html
<h2>Picture Element — Responsive (Different Images for Different Screens)</h2>
<p>Resize your browser window to see different images load.</p>

<picture>
  <!-- Portrait crop for mobile screens -->
  <source
    media="(max-width: 600px)"
    srcset="https://images.unsplash.com/photo-1472214103451-9374bd1c798e?w=400&h=600&fit=crop"
  >
  <!-- Landscape for larger screens -->
  <source
    media="(min-width: 601px)"
    srcset="https://images.unsplash.com/photo-1472214103451-9374bd1c798e?w=1200&h=600&fit=crop"
  >
  <img
    src="https://images.unsplash.com/photo-1472214103451-9374bd1c798e?w=800"
    alt="A vast green meadow with wildflowers stretching to the horizon"
    width="800"
    height="533"
    loading="lazy"
  >
</picture>
```

---

## Step 7 — Add a Decorative Image (Empty Alt)

```html
<h2>Decorative Image</h2>
<p>This divider image is purely decorative — it gets an empty alt attribute:</p>

<img
  src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800&h=50&fit=crop"
  alt=""
  width="800"
  height="50"
  loading="lazy"
>
```

---

## Step 8 — Add an Image That Is a Link

```html
<h2>Image as a Link</h2>
<p>When an image is a link, the alt text should describe the destination:</p>

<a href="https://unsplash.com" target="_blank" rel="noopener noreferrer">
  <img
    src="https://images.unsplash.com/photo-1501854140801-50d01698950b?w=400"
    alt="Visit Unsplash — free high-resolution photos"
    width="400"
    height="267"
    loading="lazy"
  >
</a>
```

---

## Checklist

- [ ] Basic image with proper alt text, width, and height
- [ ] Lazy-loaded image with `loading="lazy"`
- [ ] `<figure>` with `<figcaption>`
- [ ] `<picture>` with format fallback (WebP + JPEG)
- [ ] `<picture>` with responsive sources (different images for different screens)
- [ ] Decorative image with `alt=""`
- [ ] Image used as a link with descriptive alt text

---

## Bonus Challenges

1. Add a gallery section with 6 images in a `<ul>` where each `<li>` contains a `<figure>`
2. Add `decoding="async"` to all images below the fold
3. Try using an SVG image (find one on undraw.co)
4. Add a `title` attribute to one image and hover over it to see the tooltip
