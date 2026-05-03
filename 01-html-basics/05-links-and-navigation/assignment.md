# Assignment — Single-Page Website with Navigation

## What You Are Building

Create a single-page website with a navigation bar that links to 4 sections on the same page. The site should include external links and a contact section with email and phone links.

No CSS. No JavaScript. Pure HTML structure only.

---

## Requirements

### Navigation Bar

- Uses `<nav>` element
- Contains a `<ul>` with `<li>` items
- Has links to at least 4 sections on the same page using `href="#section-id"`
- At least one external link with `target="_blank"` and `rel="noopener noreferrer"`

### Page Sections (4 required)

Each section must:
- Have a unique `id` attribute that matches a nav link
- Have an `<h2>` heading
- Have at least one paragraph of real content

Suggested sections:
1. Home or Hero
2. About
3. Portfolio, Projects, or Skills
4. Contact

### Contact Section

Must include:
- Email link using `mailto:`
- Phone link using `tel:`
- At least one external social media link

### Additional Requirements

- Proper HTML document structure (DOCTYPE, html, head, body)
- `<main>` wrapping the main content
- `<header>` wrapping the navigation
- `<footer>` at the bottom
- At least one anchor link within the page content (not just in the nav)
- A "Back to top" link at the bottom of the last section

---

## What Good Looks Like

- Every nav link jumps to the correct section when clicked
- The `id` attributes on sections exactly match the `href` values in the nav
- External links open in a new tab
- Email link opens the email client
- Phone link works on mobile
- The page is well-structured with semantic HTML
- The page passes W3C validation at `https://validator.w3.org/`

---

## Topic Ideas

Make it personal. The site could be:
- Your personal portfolio
- A page about your favorite hobby
- A fan page for a band, game, or show
- A small business landing page
- A page about your hometown

---

## Bonus Challenges

- Add `aria-label="Main navigation"` to the `<nav>` element
- Add a `title` attribute to external links explaining they open in a new tab
- Add a download link for a resume or file
- Add `aria-current="page"` to the active nav item
- Add a "skip to main content" link at the very top for accessibility: `<a href="#main">Skip to main content</a>`

---

## Submission

Save as `portfolio-nav.html` and submit via GitHub or file upload.
