# 11 — Video, Audio, and iframes

## What Is This Lesson About?

HTML5 introduced native support for video and audio without plugins. The `<iframe>` element lets you embed external content like YouTube videos, Google Maps, and other websites directly in your page.

---

## The `<video>` Element

```html
<video controls width="800" height="450">
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  <p>Your browser does not support HTML5 video. <a href="video.mp4">Download the video</a>.</p>
</video>
```

### Video Attributes

| Attribute | Purpose |
|---|---|
| `controls` | Show play/pause/volume controls |
| `autoplay` | Start playing automatically |
| `muted` | Start muted (required for autoplay in most browsers) |
| `loop` | Loop the video |
| `poster` | Image shown before video plays |
| `width` / `height` | Dimensions |
| `preload` | `auto`, `metadata`, or `none` |
| `playsinline` | Play inline on iOS (not fullscreen) |

### Video Formats

| Format | Extension | Browser Support |
|---|---|---|
| MP4 (H.264) | `.mp4` | All browsers |
| WebM (VP9) | `.webm` | Chrome, Firefox, Edge |
| Ogg | `.ogv` | Firefox |

**Best practice:** Always provide MP4 as the primary source. Add WebM as a secondary source for smaller file sizes in supporting browsers.

---

## The `<audio>` Element

```html
<audio controls>
  <source src="podcast.mp3" type="audio/mpeg">
  <source src="podcast.ogg" type="audio/ogg">
  <p>Your browser does not support HTML5 audio. <a href="podcast.mp3">Download the audio</a>.</p>
</audio>
```

### Audio Attributes

| Attribute | Purpose |
|---|---|
| `controls` | Show play/pause/volume controls |
| `autoplay` | Start playing automatically |
| `muted` | Start muted |
| `loop` | Loop the audio |
| `preload` | `auto`, `metadata`, or `none` |

### Audio Formats

| Format | Extension | Browser Support |
|---|---|---|
| MP3 | `.mp3` | All browsers |
| OGG Vorbis | `.ogg` | Chrome, Firefox |
| WAV | `.wav` | All browsers (large files) |
| AAC | `.aac` | Safari, Chrome |

---

## The `<iframe>` Element

`<iframe>` embeds another webpage inside your page.

```html
<iframe
  src="https://www.youtube.com/embed/VIDEO_ID"
  width="560"
  height="315"
  title="Video title"
  allowfullscreen
  loading="lazy"
></iframe>
```

### Embedding YouTube

1. Go to a YouTube video
2. Click Share → Embed
3. Copy the `<iframe>` code
4. Paste it into your HTML

The URL format is: `https://www.youtube.com/embed/VIDEO_ID`

### Embedding Google Maps

1. Go to Google Maps
2. Find a location
3. Click Share → Embed a map
4. Copy the `<iframe>` code

### iframe Attributes

| Attribute | Purpose |
|---|---|
| `src` | URL to embed |
| `width` / `height` | Dimensions |
| `title` | Accessible description (required) |
| `allowfullscreen` | Allow fullscreen mode |
| `loading="lazy"` | Lazy load the iframe |
| `sandbox` | Restrict what the iframe can do |
| `allow` | Permissions (camera, microphone, etc.) |

### iframe Security

The `sandbox` attribute restricts what the embedded content can do:

```html
<iframe
  src="https://example.com"
  sandbox="allow-scripts allow-same-origin"
></iframe>
```

---

## Accessibility

- Always add `title` to `<iframe>` elements
- Always provide a text fallback inside `<video>` and `<audio>` for browsers that do not support them
- Add captions/subtitles to videos using `<track>`

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track kind="subtitles" src="subtitles-en.vtt" srclang="en" label="English">
</video>
```
