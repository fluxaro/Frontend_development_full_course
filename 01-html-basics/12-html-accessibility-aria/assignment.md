# Assignment — Accessible Contact Page

## What You Are Building

Create an HTML page called `accessible-contact.html` — a fully accessible contact page that passes WCAG 2.1 AA requirements.

No CSS. No JavaScript. Pure HTML structure only.

---

## Requirements

### Accessibility Requirements

Every single one of these must be present:

- `lang="en"` on the `<html>` element
- A skip link as the very first element: `<a href="#main-content">Skip to main content</a>`
- `<main id="main-content">` wrapping the main content
- Proper heading hierarchy (h1 → h2 → h3, no skipping)
- All images have descriptive `alt` text (or `alt=""` if decorative)
- All form inputs have `<label>` elements with matching `for` and `id`
- All required fields have both `required` and `aria-required="true"`
- `aria-describedby` on inputs that have hint text
- `<button>` used for all interactive actions (not `<div>` or `<span>`)
- `type="email"` for email inputs
- `type="tel"` for phone inputs

### Page Content

Your page must include:

1. **Header** with site name and navigation
2. **Contact Form** with:
   - Full name (text)
   - Email address (email)
   - Phone number (tel) — optional
   - Subject (select with at least 4 options)
   - Message (textarea)
   - Submit and reset buttons
3. **Contact Information Section** with:
   - Physical address using `<address>`
   - Email link using `mailto:`
   - Phone link using `tel:`
   - Business hours
4. **FAQ Section** using `<details>` and `<summary>` for at least 3 questions

---

## What Good Looks Like

- The page is fully navigable using only the keyboard (Tab, Enter, Space, arrow keys)
- Every form field has a visible label
- The skip link works (jumps to main content)
- The page passes the WAVE accessibility checker at `https://wave.webaim.org/`
- The page passes W3C validation

---

## Bonus Challenges

- Add `aria-live="polite"` region for form submission status messages
- Add `aria-expanded` to the FAQ `<details>` elements
- Add `role="alert"` to an error message area
- Add `autocomplete` attributes to all relevant form fields

---

## Submission

Save as `accessible-contact.html` and submit via GitHub.
