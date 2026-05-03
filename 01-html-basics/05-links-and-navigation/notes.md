# Notes — Links and Navigation

## Link Types Cheat Sheet

```html
<!-- External link (absolute URL) -->
<a href="https://example.com">External Site</a>

<!-- Internal link (relative URL) -->
<a href="about.html">About Page</a>
<a href="pages/contact.html">Contact (subfolder)</a>
<a href="../index.html">Home (parent folder)</a>
<a href="/index.html">Home (from root)</a>

<!-- Anchor link (same page) -->
<a href="#section-id">Jump to Section</a>

<!-- Anchor link (different page) -->
<a href="about.html#team">About > Team Section</a>

<!-- Email link -->
<a href="mailto:hello@example.com">Send Email</a>
<a href="mailto:hello@example.com?subject=Hello&body=Hi%20there">Email with subject</a>

<!-- Phone link -->
<a href="tel:+15551234567">Call Us</a>

<!-- SMS link -->
<a href="sms:+15551234567">Text Us</a>

<!-- Download link -->
<a href="file.pdf" download>Download PDF</a>
<a href="file.pdf" download="custom-name.pdf">Download with custom name</a>

<!-- Open in new tab (with security) -->
<a href="https://example.com" target="_blank" rel="noopener noreferrer">New Tab</a>
```

---

## Relative vs Absolute Paths

### Absolute Path
```html
<a href="https://mysite.com/about.html">About</a>
```
- Starts with `https://` or `http://`
- Works from anywhere
- Use for external sites

### Relative Path
```html
<a href="about.html">About</a>
```
- Relative to the current file's location
- Use for internal pages

### Path Navigation
```
project/
├── index.html
├── about.html
├── css/
│   └── style.css
└── pages/
    ├── contact.html
    └── blog/
        └── post.html
```

From `index.html`:
```html
<a href="about.html">About</a>              <!-- same folder -->
<a href="pages/contact.html">Contact</a>    <!-- into subfolder -->
```

From `pages/contact.html`:
```html
<a href="../index.html">Home</a>            <!-- up one level -->
<a href="../about.html">About</a>           <!-- up one level -->
<a href="blog/post.html">Blog Post</a>      <!-- into subfolder -->
```

From `pages/blog/post.html`:
```html
<a href="../../index.html">Home</a>         <!-- up two levels -->
<a href="../contact.html">Contact</a>       <!-- up one level -->
```

---

## `target` Attribute Values

| Value | Behavior |
|-------|---------|
| `_self` | Same tab (default) |
| `_blank` | New tab/window |
| `_parent` | Parent frame |
| `_top` | Full window (breaks out of all frames) |
| `framename` | Named iframe |

---

## `rel` Attribute Values

```html
<!-- Security for external links -->
rel="noopener noreferrer"

<!-- Tell search engines not to follow this link -->
rel="nofollow"

<!-- Canonical URL -->
rel="canonical"

<!-- Stylesheet -->
rel="stylesheet"

<!-- Sponsored/paid links -->
rel="sponsored"

<!-- User-generated content -->
rel="ugc"
```

**Always use `rel="noopener noreferrer"` with `target="_blank"`** to prevent:
- `noopener` — prevents the new page from accessing `window.opener`
- `noreferrer` — prevents sending the referrer header

---

## Anchor Links (Jump Links)

```html
<!-- Step 1: Add id to the target element -->
<section id="about">
  <h2>About Us</h2>
</section>

<!-- Step 2: Link to it with # -->
<a href="#about">Go to About</a>

<!-- Rules for id values: -->
<!-- ✅ Good -->
id="about"
id="contact-form"
id="section-2"

<!-- ❌ Bad -->
id="About"          <!-- case-sensitive: #About ≠ #about -->
id="my section"     <!-- no spaces -->
id="2section"       <!-- don't start with number -->
```

---

## Navigation Best Practices

### Semantic Structure
```html
<!-- ✅ Correct — nav with list -->
<nav aria-label="Main navigation">
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>

<!-- ❌ Avoid — divs instead of semantic elements -->
<div class="nav">
  <div><a href="/">Home</a></div>
  <div><a href="/about">About</a></div>
</div>
```

### Current Page Indicator
```html
<nav>
  <ul>
    <li><a href="/" aria-current="page">Home</a></li>  <!-- current page -->
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>
```

### Skip Navigation Link (Accessibility)
```html
<!-- First element in body — allows keyboard users to skip nav -->
<a href="#main-content" class="skip-link">Skip to main content</a>

<nav>...</nav>

<main id="main-content">
  <!-- Page content -->
</main>
```

---

## Common Mistakes

### ❌ Non-descriptive link text
```html
<!-- Bad — "click here" is meaningless out of context -->
<a href="/report.pdf">Click here</a>

<!-- Good — describes the destination -->
<a href="/report.pdf">Download the 2025 Annual Report (PDF, 2MB)</a>
```

### ❌ Missing `rel` on external links
```html
<!-- Bad — security risk -->
<a href="https://external.com" target="_blank">External</a>

<!-- Good -->
<a href="https://external.com" target="_blank" rel="noopener noreferrer">External</a>
```

### ❌ Using JavaScript for navigation
```html
<!-- Bad — not accessible, not indexable -->
<span onclick="window.location='about.html'">About</span>

<!-- Good — use real links -->
<a href="about.html">About</a>
```

### ❌ Empty href
```html
<!-- Bad — goes to top of page, confusing -->
<a href="#">Click me</a>

<!-- Better — use a button if no navigation -->
<button type="button">Click me</button>
```

### ❌ Broken relative paths
```html
<!-- If you're in pages/contact.html and want to link to index.html: -->
<!-- Bad — this looks for pages/index.html -->
<a href="index.html">Home</a>

<!-- Good — go up one level first -->
<a href="../index.html">Home</a>
```

---

## Email Link Encoding

Special characters in email links must be URL-encoded:

| Character | Encoded |
|-----------|---------|
| Space | `%20` |
| `@` | `%40` |
| `&` | `%26` |
| `=` | `%3D` |
| `+` | `%2B` |
| `#` | `%23` |

```html
<a href="mailto:hello@example.com?subject=Hello%20World&body=Hi%20there%2C%0A%0AHow%20are%20you%3F">
  Email with pre-filled content
</a>
```
