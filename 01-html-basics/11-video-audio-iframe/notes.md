# Notes — Video, Audio, and iframes

## Video Cheat Sheet

```html
<video controls width="800" height="450" poster="thumb.jpg">
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  <p>Browser does not support video. <a href="video.mp4">Download</a>.</p>
</video>
```

## Audio Cheat Sheet

```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
  <source src="audio.ogg" type="audio/ogg">
  <p>Browser does not support audio. <a href="audio.mp3">Download</a>.</p>
</audio>
```

## iframe Cheat Sheet

```html
<iframe
  src="https://www.youtube.com/embed/VIDEO_ID"
  width="560"
  height="315"
  title="Descriptive title"
  allowfullscreen
  loading="lazy"
></iframe>
```

## Video Attributes

| Attribute | Effect |
|---|---|
| `controls` | Show player controls |
| `autoplay` | Auto-start (needs `muted`) |
| `muted` | Start muted |
| `loop` | Repeat forever |
| `poster="url"` | Thumbnail image |
| `playsinline` | Inline on iOS |
| `preload="metadata"` | Load only metadata |

## Common Mistakes

- Using `autoplay` without `muted` (browsers block it)
- Missing `title` on `<iframe>` (accessibility failure)
- Not providing fallback content inside `<video>` and `<audio>`
- Using the full YouTube URL instead of the embed URL
- Not adding `loading="lazy"` to iframes (performance)

## YouTube Embed URL Format

```
Full URL:   https://www.youtube.com/watch?v=VIDEO_ID
Embed URL:  https://www.youtube.com/embed/VIDEO_ID
```

Always use the embed URL in `<iframe src>`.
