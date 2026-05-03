# Class Work — Building a Complete Head Section

## What You Will Build

You will add all important meta tags to an HTML page step by step, understanding what each one does and why it matters.

**Time:** 35 minutes  
**Tools:** VS Code and a browser

---

## Step 1 — Start with the Basics

Create a new file called `my-article.html`. Start with the minimal structure:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>5 Tips for Learning HTML Fast</title>
  </head>
  <body>
    <h1>5 Tips for Learning HTML Fast</h1>
    <p>Learning HTML does not have to take months. Here are five proven strategies.</p>
  </body>
</html>
```

Open in browser. Check the tab title.

---

## Step 2 — Add SEO Meta Tags

Add these inside `<head>`, after the `<title>`:

```html
<meta name="description" content="Discover 5 practical tips to learn HTML quickly and start building real websites. Perfect for complete beginners.">
<meta name="author" content="Your Name">
```

**Why the description matters:** This is the text that appears under your page title in Google search results. It does not directly affect your ranking, but it affects whether people click your link. Keep it between 150 and 160 characters.

Right-click your page → View Page Source. You should see your meta tags in the source code.

---

## Step 3 — Add Open Graph Tags

Open Graph tags control how your page looks when someone shares it on social media (Facebook, LinkedIn, Slack, etc.).

Add these inside `<head>`:

```html
<meta property="og:title" content="5 Tips for Learning HTML Fast">
<meta property="og:description" content="Discover 5 practical tips to learn HTML quickly and start building real websites.">
<meta property="og:type" content="article">
<meta property="og:url" content="https://yoursite.com/html-tips">
<meta property="og:image" content="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=1200&h=630">
```

**What each one does:**
- `og:title` — the title shown in the social media preview card
- `og:description` — the description shown in the preview card
- `og:type` — what kind of content this is (article, website, video, etc.)
- `og:url` — the canonical URL of the page
- `og:image` — the image shown in the preview card (should be at least 1200×630 pixels)

---

## Step 4 — Add Twitter Card Tags

Twitter uses its own set of meta tags (though it also reads OG tags as a fallback):

```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="5 Tips for Learning HTML Fast">
<meta name="twitter:description" content="Discover 5 practical tips to learn HTML quickly.">
```

The `twitter:card` value `summary_large_image` shows a large image preview when the link is shared on Twitter/X.

---

## Step 5 — Add a Favicon

A favicon is the small icon that appears in the browser tab.

```html
<link rel="icon" href="favicon.png">
```

If you do not have an image file, you can use an emoji as a favicon with this trick:

```html
<link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>📝</text></svg>">
```

Save and refresh. Check your browser tab — you should see the emoji icon.

---

## Step 6 — Add a CSS Link

Even if the CSS file does not exist yet, practice adding the link:

```html
<link rel="stylesheet" href="style.css">
```

If the CSS file does not exist, the browser ignores the link. No error is shown to users, but you will see a 404 in the Network tab of DevTools.

---

## Step 7 — Add a Canonical URL

The canonical URL tells search engines which URL is the "official" version of this page:

```html
<link rel="canonical" href="https://yoursite.com/html-tips">
```

This is important when the same content is accessible at multiple URLs.

---

## Your Complete Head Section

By the end, your `<head>` should look like this:

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>5 Tips for Learning HTML Fast</title>
  <meta name="description" content="Discover 5 practical tips to learn HTML quickly and start building real websites.">
  <meta name="author" content="Your Name">

  <meta property="og:title" content="5 Tips for Learning HTML Fast">
  <meta property="og:description" content="Discover 5 practical tips to learn HTML quickly.">
  <meta property="og:type" content="article">
  <meta property="og:url" content="https://yoursite.com/html-tips">
  <meta property="og:image" content="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=1200&h=630">

  <meta name="twitter:card" content="summary_large_image">

  <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>📝</text></svg>">
  <link rel="canonical" href="https://yoursite.com/html-tips">
  <link rel="stylesheet" href="style.css">
</head>
```

---

## Checklist

- [ ] `charset` meta tag is first in head
- [ ] `viewport` meta tag present
- [ ] `title` is descriptive and under 60 characters
- [ ] `description` meta is 150–160 characters
- [ ] All 5 OG tags present (title, description, type, url, image)
- [ ] Twitter card tag present
- [ ] Favicon shows in browser tab
- [ ] CSS link present
- [ ] Canonical link present

---

## Bonus Challenges

1. Visit `https://metatags.io/` and preview how your OG tags look when shared
2. Add `<meta name="robots" content="index, follow">` — research what this does
3. Add `<meta property="article:published_time" content="2025-01-15T10:00:00Z">` — what is this for?
4. Try changing `og:type` from `"article"` to `"website"` — what is the difference?
