# 05 — Links and Navigation

## The Anchor Tag: `<a>`

The `<a>` (anchor) tag creates hyperlinks — the fundamental building block of the web. Without links, the web would just be a collection of isolated pages.

```html
<a href="https://example.com">Link text</a>
```

- `href` (Hypertext REFerence) — the URL the link points to
- The content between the tags is the clickable text (or image)

---

## Types of URLs

### Absolute URLs
A complete URL including the protocol and domain:

```html
<a href="https://www.google.com">Google</a>
<a href="https://developer.mozilla.org/en-US/docs/Web/HTML">MDN HTML Docs</a>
```

Use for: links to **external websites**.

### Relative URLs
A URL relative to the current page's location:

```html
<!-- Same folder -->
<a href="about.html">About</a>

<!-- Subfolder -->
<a href="pages/contact.html">Contact</a>

<!-- Parent folder -->
<a href="../index.html">Home</a>

<!-- Root of site -->
<a href="/index.html">Home</a>
```

Use for: links to **pages within your own website**.

### How Relative Paths Work

```
project/
├── index.html          ← you are here
├── about.html
├── pages/
│   ├── contact.html
│   └── services.html
└── blog/
    └── post.html
```

From `index.html`:
- `about.html` → links to `project/about.html`
- `pages/contact.html` → links to `project/pages/contact.html`

From `pages/contact.html`:
- `../index.html` → goes up one level to `project/index.html`
- `services.html` → links to `project/pages/services.html`

---

## The `target` Attribute

Controls where the link opens:

```html
<!-- Open in same tab (default) -->
<a href="page.html">Same tab</a>
<a href="page.html" target="_self">Same tab (explicit)</a>

<!-- Open in new tab -->
<a href="https://google.com" target="_blank">New tab</a>

<!-- Open in parent frame -->
<a href="page.html" target="_parent">Parent frame</a>

<!-- Open in full window (replaces all frames) -->
<a href="page.html" target="_top">Full window</a>
```

**Security note:** When using `target="_blank"`, always add `rel="noopener noreferrer"`:

```html
<a href="https://external.com" target="_blank" rel="noopener noreferrer">
  External Link
</a>
```

Without `rel="noopener"`, the opened page can access your page via `window.opener` — a security risk.

---

## Special Link Types

### Email Links
```html
<a href="mailto:hello@example.com">Send us an email</a>

<!-- With subject and body pre-filled -->
<a href="mailto:hello@example.com?subject=Hello&body=I%20wanted%20to%20say...">
  Email with subject
</a>
```

### Phone Links
```html
<a href="tel:+15551234567">Call us: (555) 123-4567</a>
```
On mobile, this opens the phone dialer. On desktop, it may open a calling app.

### SMS Links
```html
<a href="sms:+15551234567">Send us a text</a>
```

---

## Anchor Links (Jump to Section)

Link to a specific section on the same page using `id` attributes:

```html
<!-- The link -->
<a href="#about">Jump to About section</a>
<a href="#contact">Jump to Contact</a>

<!-- The target sections (must have matching id) -->
<section id="about">
  <h2>About Us</h2>
  <p>...</p>
</section>

<section id="contact">
  <h2>Contact</h2>
  <p>...</p>
</section>
```

**Rules for `id` attributes:**
- Must be unique on the page
- No spaces (use hyphens: `id="my-section"`)
- Case-sensitive (`#About` ≠ `#about`)

### Link to a section on another page:
```html
<a href="about.html#team">Meet our team</a>
```

---

## The `download` Attribute

Forces the browser to download the file instead of opening it:

```html
<!-- Download with original filename -->
<a href="report.pdf" download>Download Report</a>

<!-- Download with custom filename -->
<a href="report-2025-01.pdf" download="annual-report.pdf">
  Download Annual Report
</a>
```

---

## Navigation Menus

A proper navigation menu uses `<nav>` and a list:

```html
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/services">Services</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>
```

Why a list? Because a navigation menu *is* a list of links. This is semantically correct and helps screen readers understand the structure.

---

## Accessibility for Links

### Descriptive link text
```html
<!-- ❌ Bad — "click here" says nothing -->
<a href="/report.pdf">Click here</a>

<!-- ✅ Good — describes what the link does -->
<a href="/report.pdf">Download the 2025 Annual Report (PDF)</a>
```

### `aria-label` for icon links
```html
<!-- ❌ Bad — screen reader says "link" with no context -->
<a href="https://twitter.com/user">🐦</a>

<!-- ✅ Good — screen reader says "Twitter profile" -->
<a href="https://twitter.com/user" aria-label="Follow us on Twitter">🐦</a>
```

### Indicating external links
```html
<a href="https://external.com" target="_blank" rel="noopener noreferrer">
  External Site <span aria-label="opens in new tab">↗</span>
</a>
```

---

## Link States (CSS)

Links have four states you can style with CSS:

```css
a:link    { color: blue; }           /* Unvisited link */
a:visited { color: purple; }         /* Visited link */
a:hover   { color: red; }            /* Mouse over */
a:active  { color: orange; }         /* Being clicked */
```

Order matters: **L**o**V**e **HA**te (link, visited, hover, active).
