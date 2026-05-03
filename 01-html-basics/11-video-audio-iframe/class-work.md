# Class Work — Build a Media Center Page

## What You Will Build

A media center page with an HTML5 video player, an audio player, and an embedded YouTube video.

**Time:** 35 minutes

---

## Step 1 — Set Up the Page

Create a file called `media-page.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Media Center</title>
  </head>
  <body>
    <h1>Media Center</h1>
    <p>A demonstration of HTML5 video, audio, and iframe embedding.</p>
  </body>
</html>
```

---

## Step 2 — Add an HTML5 Video

We will use a free sample video from the internet:

```html
<section>
  <h2>Featured Video</h2>

  <video
    controls
    width="800"
    height="450"
    poster="https://images.unsplash.com/photo-1536240478700-b869ad10e128?w=800&h=450&fit=crop"
  >
    <source
      src="https://www.w3schools.com/html/mov_bbb.mp4"
      type="video/mp4"
    >
    <source
      src="https://www.w3schools.com/html/mov_bbb.ogg"
      type="video/ogg"
    >
    <p>
      Your browser does not support HTML5 video.
      <a href="https://www.w3schools.com/html/mov_bbb.mp4">Download the video</a>.
    </p>
  </video>

  <p>
    <strong>Big Buck Bunny</strong> — A short animated film by the Blender Foundation.
    Licensed under <a href="https://creativecommons.org/licenses/by/3.0/" target="_blank" rel="noopener noreferrer">Creative Commons Attribution 3.0</a>.
  </p>
</section>
```

**What to notice:**
- `controls` shows the play/pause/volume controls
- `poster` shows an image before the video plays
- Two `<source>` elements provide MP4 and OGG formats
- The `<p>` inside `<video>` is the fallback for browsers that do not support video

---

## Step 3 — Add an Audio Player

```html
<section>
  <h2>Podcast Episode</h2>

  <audio controls>
    <source
      src="https://www.w3schools.com/html/horse.mp3"
      type="audio/mpeg"
    >
    <source
      src="https://www.w3schools.com/html/horse.ogg"
      type="audio/ogg"
    >
    <p>
      Your browser does not support HTML5 audio.
      <a href="https://www.w3schools.com/html/horse.mp3">Download the audio</a>.
    </p>
  </audio>

  <p>
    <strong>Episode 1: Introduction to Web Development</strong><br>
    Duration: 45 minutes | Published: January 15, 2025
  </p>
</section>
```

---

## Step 4 — Embed a YouTube Video

Go to YouTube and find any video you like. Click Share → Embed. Copy the `<iframe>` code.

Or use this example (a web development tutorial):

```html
<section>
  <h2>Tutorial Video</h2>

  <iframe
    width="560"
    height="315"
    src="https://www.youtube.com/embed/qz0aGYrrlhU"
    title="HTML Tutorial for Beginners"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen
    loading="lazy"
  ></iframe>

  <p>
    <strong>HTML Tutorial for Beginners</strong> — Learn HTML from scratch.
    Watch on <a href="https://www.youtube.com/watch?v=qz0aGYrrlhU" target="_blank" rel="noopener noreferrer">YouTube</a>.
  </p>
</section>
```

**What to notice:**
- `title` is required for accessibility
- `allowfullscreen` lets users go fullscreen
- `loading="lazy"` defers loading until the user scrolls to it

---

## Step 5 — Embed a Google Map

```html
<section>
  <h2>Our Location</h2>

  <iframe
    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3022.9663095343008!2d-74.00425878459418!3d40.74076684379132!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c259bf5c1654f3%3A0xc80f9cfce5383d5d!2sEmpire%20State%20Building!5e0!3m2!1sen!2sus!4v1620000000000!5m2!1sen!2sus"
    width="600"
    height="450"
    title="Map showing the Empire State Building in New York City"
    loading="lazy"
    allowfullscreen
  ></iframe>

  <p>Empire State Building, 350 5th Ave, New York, NY 10118</p>
</section>
```

---

## Step 6 — Add a Video with Autoplay (Muted)

```html
<section>
  <h2>Background Video (Autoplay)</h2>
  <p>Autoplay only works when the video is muted:</p>

  <video
    autoplay
    muted
    loop
    playsinline
    width="800"
    height="450"
  >
    <source
      src="https://www.w3schools.com/html/mov_bbb.mp4"
      type="video/mp4"
    >
  </video>
</section>
```

---

## Checklist

- [ ] HTML5 video with `controls`, `poster`, and multiple `<source>` elements
- [ ] Fallback text inside `<video>` for unsupported browsers
- [ ] HTML5 audio with `controls` and multiple `<source>` elements
- [ ] YouTube video embedded with `<iframe>` and `title` attribute
- [ ] Google Map embedded with `<iframe>` and `title` attribute
- [ ] Autoplay video with `muted` attribute
- [ ] All iframes have `loading="lazy"`
