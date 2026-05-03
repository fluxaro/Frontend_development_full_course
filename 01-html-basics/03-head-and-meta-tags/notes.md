# Notes — Head and Meta Tags

## Meta Tags Cheat Sheet

### Essential Meta Tags
```html
<meta charset="UTF-8">                          <!-- Character encoding — ALWAYS FIRST -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">  <!-- Mobile -->
<meta name="description" content="150-160 char description">            <!-- SEO snippet -->
<meta name="author" content="Name">                                      <!-- Author -->
<meta name="robots" content="index, follow">                            <!-- Search crawling -->
<meta name="keywords" content="word1, word2">                           <!-- Largely ignored by Google -->
```

### Open Graph Tags
```html
<meta property="og:title" content="Title">
<meta property="og:description" content="Description">
<meta property="og:image" content="https://site.com/image.jpg">
<meta property="og:url" content="https://site.com/page">
<meta property="og:type" content="website">          <!-- or "article", "video.movie", etc. -->
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
```

### Twitter Card Tags
```html
<meta name="twitter:card" content="summary_large_image">  <!-- or "summary" -->
<meta name="twitter:title" content="Title">
<meta name="twitter:description" content="Description">
<meta name="twitter:image" content="https://site.com/image.jpg">
<meta name="twitter:site" content="@handle">
<meta name="twitter:creator" content="@authorhandle">
```

### Article-Specific OG Tags
```html
<meta property="article:published_time" content="2025-01-15T10:00:00Z">
<meta property="article:modified_time" content="2025-01-20T14:30:00Z">
<meta property="article:author" content="Author Name">
<meta property="article:section" content="Technology">
<meta property="article:tag" content="HTML">
```

---

## Link Tags Cheat Sheet
```html
<!-- CSS stylesheet -->
<link rel="stylesheet" href="style.css">

<!-- Favicon (simple) -->
<link rel="icon" href="/favicon.ico">

<!-- Favicon (modern, multiple sizes) -->
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">

<!-- Emoji favicon (no image file needed!) -->
<link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>🚀</text></svg>">

<!-- Canonical URL -->
<link rel="canonical" href="https://yoursite.com/page">

<!-- Preload critical resources -->
<link rel="preload" href="hero.jpg" as="image">
<link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>

<!-- DNS prefetch (speed up external resources) -->
<link rel="dns-prefetch" href="//fonts.googleapis.com">

<!-- Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap" rel="stylesheet">
```

---

## Viewport Meta Explained

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

| Property | Value | Meaning |
|----------|-------|---------|
| `width` | `device-width` | Page width = device screen width |
| `initial-scale` | `1.0` | No zoom on initial load |
| `maximum-scale` | `1.0` | Prevent user zoom (⚠️ bad for accessibility) |
| `user-scalable` | `no` | Disable pinch zoom (⚠️ bad for accessibility) |

> ⚠️ **Never use** `user-scalable=no` or `maximum-scale=1.0` — it prevents users from zooming in, which is an accessibility violation.

---

## OG Tags Explained

### og:type values
| Value | Use for |
|-------|---------|
| `website` | Homepage, general pages |
| `article` | Blog posts, news articles |
| `video.movie` | Movie pages |
| `music.song` | Music pages |
| `profile` | User profile pages |

### og:image requirements
| Property | Requirement |
|----------|------------|
| Minimum size | 1200 × 630 pixels |
| Aspect ratio | 1.91:1 |
| Max file size | 8MB |
| Format | JPG or PNG (not GIF) |
| URL | Must be absolute (https://...) |

---

## Title Tag Best Practices

```html
<!-- Format: Page Name — Site Name -->
<title>How to Learn HTML — Frontend Bootcamp</title>

<!-- For homepage: Site Name — Tagline -->
<title>Frontend Bootcamp — Learn Web Development</title>

<!-- Length: 50-60 characters (Google truncates at ~60) -->
```

| ❌ Bad | ✅ Good |
|--------|---------|
| `<title>Home</title>` | `<title>Frontend Bootcamp — Learn Web Dev</title>` |
| `<title>Page</title>` | `<title>HTML Basics: Tags, Elements & Attributes</title>` |
| `<title>My Amazing Website That Has Everything You Need</title>` | `<title>Web Dev Resources — Frontend Bootcamp</title>` |

---

## Meta Description Best Practices

```html
<!-- 150-160 characters, compelling, includes keywords naturally -->
<meta name="description" content="Learn HTML from scratch with hands-on exercises. Build real web pages in your first lesson. Perfect for complete beginners.">
```

| ❌ Bad | ✅ Good |
|--------|---------|
| Too short: "HTML tutorial" | "Learn HTML from scratch with hands-on exercises and real projects." |
| Too long (gets cut off in search results) | Keep under 160 characters |
| Keyword stuffing: "HTML HTML HTML tutorial HTML" | Natural language with keywords |
| Same description on every page | Unique description per page |

---

## Robots Meta Tag

```html
<meta name="robots" content="index, follow">    <!-- Default — allow indexing and following links -->
<meta name="robots" content="noindex, follow">  <!-- Don't index this page, but follow links -->
<meta name="robots" content="index, nofollow">  <!-- Index page, but don't follow links -->
<meta name="robots" content="noindex, nofollow"> <!-- Don't index, don't follow -->
```

**When to use `noindex`:**
- Thank you pages after form submission
- Admin/login pages
- Duplicate content pages
- Pages under construction

---

## Testing Tools

| Tool | URL | Purpose |
|------|-----|---------|
| Facebook Debugger | developers.facebook.com/tools/debug | Test OG tags |
| Twitter Card Validator | cards-dev.twitter.com/validator | Test Twitter cards |
| LinkedIn Post Inspector | linkedin.com/post-inspector | Test LinkedIn sharing |
| Meta Tags Preview | metatags.io | Preview all social sharing |
| Open Graph Check | opengraph.xyz | Check OG tags |
| Google Rich Results | search.google.com/test/rich-results | Test structured data |
