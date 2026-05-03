# 14 — HTML SEO Basics

## What Is This Lesson About?

SEO (Search Engine Optimization) is the practice of making your website rank higher in search results. HTML plays a huge role in SEO — the structure, tags, and content of your HTML directly affect how search engines understand and rank your page.

---

## How Search Engines Work

1. **Crawling** — Search engine bots visit your page and follow links
2. **Indexing** — They analyze your HTML and store information about your page
3. **Ranking** — They decide where to show your page in search results

Your HTML tells search engines: what your page is about, how important each piece of content is, and how to display your page in search results.

---

## The Most Important SEO HTML Elements

### 1. Title Tag

The most important SEO element. Appears in browser tabs, search results, and social shares.

```html
<title>Learn HTML in 30 Days — Free Beginner Course | Frontend Bootcamp</title>
```

**Rules:**
- 50–60 characters
- Include your primary keyword
- Include your brand name at the end
- Every page must have a unique title

### 2. Meta Description

Appears under the title in search results. Does not directly affect ranking but affects click-through rate.

```html
<meta name="description" content="A free, beginner-friendly HTML course that takes you from zero to building real websites in 30 days. No experience required.">
```

**Rules:**
- 150–160 characters
- Include your primary keyword naturally
- Write it like an ad — make people want to click
- Every page must have a unique description

### 3. Heading Hierarchy

Search engines use headings to understand your content structure. The `<h1>` is the most important.

```html
<h1>Learn HTML in 30 Days</h1>  <!-- One per page — your main topic -->
<h2>What You Will Learn</h2>    <!-- Major sections -->
<h3>HTML Basics</h3>            <!-- Subsections -->
```

**Rules:**
- One `<h1>` per page
- Use headings in order (h1 → h2 → h3, never skip)
- Include keywords naturally in headings

### 4. Semantic HTML

Search engines understand semantic elements better than divs:

```html
<article>  <!-- Self-contained content -->
<section>  <!-- Thematic group -->
<nav>      <!-- Navigation -->
<main>     <!-- Main content -->
```

### 5. Alt Text on Images

Search engines cannot see images — they read the alt text:

```html
<img src="html-course.jpg" alt="Screenshot of HTML code in VS Code editor">
```

### 6. Internal Links

Links between your own pages help search engines discover and understand your site:

```html
<a href="/html-basics">Learn HTML Basics</a>
<a href="/css-basics">Learn CSS Basics</a>
```

### 7. Canonical URL

Tells search engines which URL is the "official" version of a page:

```html
<link rel="canonical" href="https://bootcamp.example.com/html-course">
```

---

## Open Graph Tags

Control how your page looks when shared on social media:

```html
<meta property="og:title" content="Learn HTML in 30 Days">
<meta property="og:description" content="Free beginner HTML course.">
<meta property="og:image" content="https://example.com/og-image.jpg">
<meta property="og:url" content="https://example.com/html-course">
<meta property="og:type" content="website">
```

---

## Structured Data (JSON-LD)

Structured data helps search engines understand your content and can enable rich results (star ratings, FAQs, etc.):

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Course",
  "name": "Learn HTML in 30 Days",
  "description": "A free beginner HTML course",
  "provider": {
    "@type": "Organization",
    "name": "Frontend Bootcamp"
  }
}
</script>
```

---

## SEO Checklist

- [ ] Unique, descriptive `<title>` (50–60 chars)
- [ ] Unique `<meta name="description">` (150–160 chars)
- [ ] One `<h1>` per page
- [ ] Heading hierarchy is correct
- [ ] All images have descriptive `alt` text
- [ ] Semantic HTML used throughout
- [ ] `<link rel="canonical">` present
- [ ] Open Graph tags present
- [ ] Page loads fast (images optimized, lazy loading)
- [ ] Mobile-friendly (viewport meta tag)
- [ ] HTTPS (not HTTP)
