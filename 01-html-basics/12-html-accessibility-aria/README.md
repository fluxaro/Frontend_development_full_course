# 12 — HTML Accessibility and ARIA

## What Is This Lesson About?

Accessibility means building websites that everyone can use — including people who use screen readers, keyboard navigation, or other assistive technologies. About 15% of the world's population has some form of disability. Accessibility is not optional — it is a legal requirement in many countries and the right thing to do.

---

## Why Accessibility Matters

- **Legal:** The ADA (US), WCAG (international), and EN 301 549 (EU) require accessible websites
- **Ethical:** Everyone deserves equal access to information
- **Business:** Accessible sites reach more users and rank better in search engines
- **Quality:** Accessible code is cleaner, more maintainable code

---

## WCAG — The Standard

WCAG (Web Content Accessibility Guidelines) is the international standard for web accessibility. The four principles are:

| Principle | Meaning |
|---|---|
| **Perceivable** | Users can perceive all content (text alternatives for images, captions for video) |
| **Operable** | Users can operate the interface (keyboard navigation, no seizure-inducing content) |
| **Understandable** | Content is understandable (clear language, predictable behavior) |
| **Robust** | Content works with assistive technologies |

---

## HTML Accessibility Basics

### 1. Use Semantic HTML

Semantic elements have built-in accessibility. A `<button>` is keyboard-focusable and announced as "button" by screen readers. A `<div>` with `onclick` is not.

```html
<!-- Bad -->
<div onclick="submit()">Submit</div>

<!-- Good -->
<button type="submit">Submit</button>
```

### 2. Alt Text on Images

```html
<!-- Meaningful image -->
<img src="chart.png" alt="Bar chart showing 40% increase in sales from 2023 to 2024">

<!-- Decorative image -->
<img src="divider.png" alt="">
```

### 3. Labels on Form Inputs

```html
<!-- Bad — no label -->
<input type="email" placeholder="Email">

<!-- Good — explicit label -->
<label for="email">Email Address</label>
<input type="email" id="email" name="email">
```

### 4. Heading Hierarchy

```html
<!-- Bad — skips levels -->
<h1>Page Title</h1>
<h3>Section</h3>  <!-- skipped h2! -->

<!-- Good — sequential -->
<h1>Page Title</h1>
<h2>Section</h2>
<h3>Subsection</h3>
```

### 5. Keyboard Navigation

All interactive elements must be reachable and usable with a keyboard:
- Tab to move between focusable elements
- Enter/Space to activate buttons and links
- Arrow keys for radio buttons and select menus
- Escape to close modals

### 6. Color Contrast

Text must have sufficient contrast against its background. WCAG AA requires:
- 4.5:1 ratio for normal text
- 3:1 ratio for large text (18px+ or 14px+ bold)

---

## ARIA — Accessible Rich Internet Applications

ARIA attributes add semantic meaning to elements that HTML alone cannot describe.

### ARIA Roles

```html
<div role="button" tabindex="0">Click me</div>
<div role="navigation">...</div>
<div role="alert">Error: Invalid email</div>
<div role="dialog" aria-modal="true">...</div>
```

### ARIA Labels

```html
<!-- aria-label: provides a text label -->
<button aria-label="Close dialog">X</button>

<!-- aria-labelledby: points to another element as the label -->
<section aria-labelledby="section-title">
  <h2 id="section-title">Latest News</h2>
</section>

<!-- aria-describedby: points to a description -->
<input type="password" aria-describedby="password-hint">
<p id="password-hint">Must be at least 8 characters</p>
```

### ARIA States

```html
<!-- aria-expanded: for accordions, dropdowns -->
<button aria-expanded="false">Show more</button>

<!-- aria-hidden: hide from screen readers -->
<span aria-hidden="true">★★★★☆</span>
<span class="sr-only">4 out of 5 stars</span>

<!-- aria-live: announce dynamic content changes -->
<div aria-live="polite" id="status"></div>

<!-- aria-required: mark required fields -->
<input type="email" aria-required="true">

<!-- aria-invalid: mark invalid fields -->
<input type="email" aria-invalid="true">
```

---

## Skip Links

A skip link lets keyboard users jump past the navigation directly to the main content:

```html
<a href="#main-content" class="skip-link">Skip to main content</a>

<nav>...</nav>

<main id="main-content">
  <!-- main content -->
</main>
```

---

## Focus Management

Visible focus indicators are required. Never do this:

```css
/* NEVER do this */
:focus { outline: none; }
```

Instead, style the focus indicator to be visible and attractive.

---

## Testing Accessibility

1. **Keyboard test:** Navigate your entire page using only Tab, Enter, Space, and arrow keys
2. **Screen reader test:** Use VoiceOver (Mac), NVDA (Windows), or TalkBack (Android)
3. **Automated tools:** axe DevTools, Lighthouse, WAVE
4. **Color contrast:** WebAIM Contrast Checker
