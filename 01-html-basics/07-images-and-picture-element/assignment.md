# Assignment — Responsive Photo Gallery

## What You Are Building

Create an HTML page called `responsive-gallery.html` — a photo gallery that uses all the image techniques from this lesson.

No CSS. No JavaScript. Pure HTML structure only.

---

## Requirements

### 1. Page Structure
- Proper `<!DOCTYPE html>`, `<html lang>`, `<head>`, `<body>`
- Meaningful `<title>` and `<meta name="description">`
- `<header>` with the gallery title and a short description
- `<main>` wrapping all gallery content
- `<footer>` with attribution

### 2. Gallery Sections (at least 3 sections)

**Section 1: Featured Photo**
- A `<figure>` with a large image and a `<figcaption>`
- The image must have proper alt text, width, height, and `loading="lazy"`

**Section 2: Responsive Images**
- At least 2 `<picture>` elements with responsive sources
- Each must have a mobile source and a desktop source using the `media` attribute
- Each must have a fallback `<img>`

**Section 3: Format Optimization**
- At least 2 `<picture>` elements with WebP source and JPEG fallback
- Use the `type` attribute on `<source>`

**Section 4: Gallery Grid**
- A `<ul>` with at least 6 `<li>` items
- Each `<li>` contains a `<figure>` with an `<img>` and `<figcaption>`
- All images must have `loading="lazy"`

### 3. Alt Text Quality
Every image must have meaningful, descriptive alt text. Decorative images must have `alt=""`.

---

## What Good Looks Like

- Every `<img>` has `alt`, `width`, and `height` attributes
- Every below-fold image has `loading="lazy"`
- `<picture>` elements are used correctly with proper fallbacks
- `<figure>` and `<figcaption>` are used for captioned images
- The page passes W3C validation

---

## Bonus Challenges

- Add a `<nav>` with anchor links to each gallery section
- Add `decoding="async"` to all non-critical images
- Use `srcset` with multiple resolutions (1x, 2x) for retina displays
- Add an image that is also a link

---

## Submission

Save as `responsive-gallery.html` and submit via GitHub.
