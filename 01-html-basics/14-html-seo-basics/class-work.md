# Class Work — Optimize a Page for SEO

## What You Will Do

You will take an existing HTML page and optimize it for search engines, then use Lighthouse to check the SEO score.

**Time:** 35 minutes

---

## Part 1: Audit an Existing Page (10 minutes)

Open your `about-me.html` from Lesson 01 (or any HTML page you have built).

Run a Lighthouse audit:
1. Open Chrome DevTools (F12)
2. Click the **Lighthouse** tab
3. Check "SEO" and "Accessibility"
4. Click "Analyze page load"

Write down:
- What is the SEO score?
- What SEO issues are listed?
- What accessibility issues are listed?

---

## Part 2: Fix the SEO Issues (15 minutes)

Based on the Lighthouse report, fix the issues. Common fixes:

### Add a proper title
```html
<title>Alex Johnson — Frontend Developer Student | Portfolio</title>
```

### Add a meta description
```html
<meta name="description" content="Alex Johnson is a frontend developer student learning HTML, CSS, and JavaScript. View my projects and get in touch.">
```

### Fix heading hierarchy
Make sure you have exactly one `<h1>` and that headings go in order.

### Add alt text to all images
```html
<img src="profile.jpg" alt="Alex Johnson smiling in front of a laptop">
```

### Add a canonical URL
```html
<link rel="canonical" href="https://alexjohnson.github.io/portfolio">
```

### Add Open Graph tags
```html
<meta property="og:title" content="Alex Johnson — Frontend Developer">
<meta property="og:description" content="Frontend developer student. View my projects.">
<meta property="og:type" content="website">
<meta property="og:url" content="https://alexjohnson.github.io/portfolio">
```

---

## Part 3: Build an SEO-Optimized Page (10 minutes)

Create a file called `seo-demo.html`. Build a page for a fictional product or service that includes:

1. A proper `<title>` (50–60 chars)
2. A `<meta name="description">` (150–160 chars)
3. Open Graph tags (og:title, og:description, og:image, og:url, og:type)
4. One `<h1>` with the primary keyword
5. At least 3 `<h2>` sections
6. At least 2 images with descriptive alt text
7. A `<link rel="canonical">`
8. Internal anchor links in a `<nav>`

---

## Checklist

- [ ] Lighthouse SEO score is 90+
- [ ] Title is 50–60 characters
- [ ] Meta description is 150–160 characters
- [ ] One `<h1>` per page
- [ ] All images have alt text
- [ ] Canonical URL present
- [ ] Open Graph tags present
- [ ] Heading hierarchy is correct
