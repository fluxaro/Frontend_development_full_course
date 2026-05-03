# Assignment — Media Center Page

## What You Are Building

Create an HTML page called `media-center.html` — a complete media center with video, audio, and embedded content.

No CSS. No JavaScript. Pure HTML structure only.

---

## Requirements

### 1. Page Structure
- Proper `<!DOCTYPE html>`, `<html lang>`, `<head>`, `<body>`
- `<header>` with the page title
- `<main>` wrapping all content
- `<footer>` with attribution

### 2. Video Section
- An `<h2>` heading
- An HTML5 `<video>` element with:
  - `controls` attribute
  - `poster` attribute (any image URL)
  - At least 2 `<source>` elements (MP4 and WebM or OGG)
  - A fallback `<p>` with a download link
  - `width` and `height` attributes
- A `<figure>` wrapping the video with a `<figcaption>`

### 3. Audio Section
- An `<h2>` heading
- An HTML5 `<audio>` element with:
  - `controls` attribute
  - At least 2 `<source>` elements
  - A fallback `<p>` with a download link
- A description of the audio content

### 4. YouTube Embed Section
- An `<h2>` heading
- An `<iframe>` embedding a YouTube video with:
  - `title` attribute (required for accessibility)
  - `allowfullscreen` attribute
  - `loading="lazy"` attribute
  - Proper `width` and `height`

### 5. Map Embed Section
- An `<h2>` heading
- An `<iframe>` embedding a Google Map with:
  - `title` attribute
  - `loading="lazy"` attribute
  - An address below the map

---

## What Good Looks Like

- All `<iframe>` elements have `title` attributes
- All `<video>` and `<audio>` elements have fallback content
- All iframes have `loading="lazy"`
- The page passes W3C validation

---

## Bonus Challenges

- Add a `<track>` element to the video for subtitles
- Add a second video with `autoplay muted loop` for a background video effect
- Add `preload="metadata"` to the audio element and explain what it does
- Add `sandbox` attribute to one iframe and explain what it restricts

---

## Submission

Save as `media-center.html` and submit via GitHub.
