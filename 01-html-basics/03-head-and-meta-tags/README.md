# 03 — Head and Meta Tags

## What Lives in the `<head>`?

The `<head>` section is the control room of your HTML page. Nothing in it is directly visible to users, but it controls how the page behaves, how it looks in search results, and how it appears when shared on social media.

---

## Essential Meta Tags

### 1. Character Encoding
```html
<meta charset="UTF-8">
```
- **Must be the first element in `<head>`**
- UTF-8 supports virtually every character in every language
- Without it, special characters (é, ñ, €, 中文) may display as garbled text

### 2. Viewport (Mobile Responsiveness)
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
- Tells mobile browsers to use the device's actual width
- Without it, mobile browsers zoom out to show a desktop-sized page
- `initial-scale=1.0` means no zoom on load

### 3. Page Title
```html
<title>My Page Title — Site Name</title>
```
- Appears in the browser tab
- Appears as the clickable headline in Google search results
- Keep it under 60 characters
- Should be unique for every page

### 4. Meta Description
```html
<meta name="description" content="A 150-160 character description of this page's content.">
```
- The text snippet shown under your title in Google results
- Doesn't directly affect ranking, but affects click-through rate
- Keep it 150-160 characters
- Should be unique and compelling for each page

### 5. Author
```html
<meta name="author" content="Jane Smith">
```
- Identifies the page author
- Used by some tools and search engines

---

## Open Graph Tags (Social Media Sharing)

Open Graph (OG) tags control how your page looks when shared on Facebook, Twitter, LinkedIn, Slack, Discord, and other platforms.

```html
<!-- Required OG tags -->
<meta property="og:title" content="Page Title for Social Media">
<meta property="og:description" content="Description shown when shared on social media.">
<meta property="og:image" content="https://yoursite.com/images/share-image.jpg">
<meta property="og:url" content="https://yoursite.com/this-page">
<meta property="og:type" content="website">

<!-- Optional but recommended -->
<meta property="og:site_name" content="Your Site Name">
<meta property="og:locale" content="en_US">
```

**OG Image requirements:**
- Minimum: 1200×630 pixels
- Aspect ratio: 1.91:1
- Under 8MB
- JPG or PNG format

### Twitter Card Tags
```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Page Title">
<meta name="twitter:description" content="Description for Twitter.">
<meta name="twitter:image" content="https://yoursite.com/images/twitter-image.jpg">
<meta name="twitter:site" content="@yourtwitterhandle">
```

---

## The `<link>` Tag

Used to link external resources to the page.

### Linking a CSS Stylesheet
```html
<link rel="stylesheet" href="style.css">
```

### Favicon (Browser Tab Icon)
```html
<!-- Modern approach — supports multiple sizes -->
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">

<!-- Simple approach — just one .ico file -->
<link rel="icon" href="/favicon.ico">
```

### Canonical URL (SEO)
```html
<link rel="canonical" href="https://yoursite.com/this-page">
```
Tells search engines which URL is the "official" version of a page (prevents duplicate content issues).

### Preloading Resources
```html
<link rel="preload" href="hero-image.jpg" as="image">
<link rel="preload" href="main-font.woff2" as="font" type="font/woff2" crossorigin>
```

---

## The `<script>` Tag

```html
<!-- External JavaScript file -->
<script src="app.js"></script>

<!-- Inline JavaScript -->
<script>
  console.log('Hello from inline script!');
</script>

<!-- Defer: load after HTML is parsed (recommended) -->
<script src="app.js" defer></script>

<!-- Async: load in parallel, execute when ready -->
<script src="analytics.js" async></script>
```

**Best practice:** Place `<script>` tags at the end of `<body>` or use `defer` attribute to avoid blocking page rendering.

---

## Why Meta Tags Matter

### SEO (Search Engine Optimization)
- `<title>` and `<meta description>` directly affect how your page appears in search results
- Proper meta tags help search engines understand and index your content
- Missing or duplicate meta tags can hurt your search rankings

### Social Media Sharing
- Without OG tags, social platforms guess what to show — often poorly
- A good OG image dramatically increases engagement when content is shared

### Mobile Experience
- The viewport meta tag is essential for any mobile-friendly page
- Without it, your carefully designed page looks terrible on phones

### Accessibility
- `lang` attribute on `<html>` helps screen readers pronounce content correctly
- Proper charset ensures all characters display correctly for all users

---

## Complete Head Section Template

```html
<head>
  <!-- Encoding — always first -->
  <meta charset="UTF-8">
  
  <!-- Mobile viewport -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  <!-- Page title -->
  <title>Page Title — Site Name</title>
  
  <!-- SEO meta tags -->
  <meta name="description" content="150-160 char description.">
  <meta name="author" content="Your Name">
  
  <!-- Open Graph / Social Media -->
  <meta property="og:title" content="Page Title">
  <meta property="og:description" content="Social media description.">
  <meta property="og:image" content="https://yoursite.com/og-image.jpg">
  <meta property="og:url" content="https://yoursite.com/page">
  <meta property="og:type" content="website">
  
  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">
  
  <!-- Favicon -->
  <link rel="icon" href="/favicon.ico">
  
  <!-- Canonical URL -->
  <link rel="canonical" href="https://yoursite.com/page">
  
  <!-- CSS -->
  <link rel="stylesheet" href="style.css">
</head>
```
