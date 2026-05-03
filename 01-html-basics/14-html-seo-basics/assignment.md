# Assignment — SEO-Optimized Product Landing Page

## What You Are Building

Create an HTML page called `product-landing-seo.html` — a fully SEO-optimized landing page for a fictional product.

---

## Requirements

### Head Section (SEO)

- `<title>` — 50–60 characters, includes product name and brand
- `<meta name="description">` — 150–160 characters, compelling and keyword-rich
- `<meta name="author">`
- `<link rel="canonical">` — the preferred URL
- Open Graph tags: `og:title`, `og:description`, `og:image`, `og:url`, `og:type`
- Twitter card: `twitter:card`, `twitter:title`, `twitter:description`

### Body Structure (SEO)

- One `<h1>` — the product name (most important keyword)
- `<h2>` headings for each major section (features, pricing, testimonials, FAQ)
- `<h3>` for subsections
- All images have descriptive `alt` text
- Internal anchor links in a `<nav>`
- At least one external link with `rel="noopener noreferrer"`
- `<time>` with `datetime` for any dates
- `<address>` for contact information

### Content Sections

1. **Hero** — Product name (h1), tagline, and call-to-action link
2. **Features** — At least 4 features, each with h3 and description
3. **Pricing** — A table with at least 3 pricing tiers
4. **Testimonials** — At least 2 customer quotes using `<blockquote>`
5. **FAQ** — At least 4 questions using `<details>` and `<summary>`
6. **Contact** — Address, email, phone

---

## What Good Looks Like

- The title and description are compelling and the right length
- The heading hierarchy is correct throughout
- All images have meaningful alt text
- The page structure makes sense to a search engine
- The page passes W3C validation

---

## Bonus Challenges

- Add JSON-LD structured data in a `<script type="application/ld+json">` block
- Add `<meta name="robots" content="index, follow">`
- Add breadcrumb navigation
- Add `hreflang` for multiple language versions

---

## Submission

Save as `product-landing-seo.html` and submit via GitHub.
