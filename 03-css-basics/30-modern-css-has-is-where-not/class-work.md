# Class Work — Modern CSS Selectors

## What You Will Build

A page demonstrating :has(), :is(), :where(), and :not() in real-world scenarios.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `modern-selectors.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modern CSS Selectors</title>
  <link rel="stylesheet" href="modern-selectors.css">
</head>
<body>

  <main>
    <h1>Modern CSS Selectors</h1>

    <section>
      <h2>:is() — Group Selectors</h2>
      <article>
        <h3>Article with h3</h3>
        <p>Paragraph inside article.</p>
      </article>
      <section>
        <h3>Section with h3</h3>
        <p>Paragraph inside section.</p>
      </section>
    </section>

    <section>
      <h2>:where() — Zero Specificity</h2>
      <nav class="main-nav">
        <a href="#">Nav link</a>
      </nav>
      <nav class="footer-nav">
        <a href="#">Footer nav link</a>
      </nav>
    </section>

    <section>
      <h2>:not() — Exclusion</h2>
      <ul>
        <li>Item 1</li>
        <li>Item 2</li>
        <li class="special">Special item (not styled)</li>
        <li>Item 4</li>
        <li>Item 5 (last)</li>
      </ul>
    </section>

    <section>
      <h2>:has() — Parent Selector</h2>
      <div class="card">
        <h3>Card without image</h3>
        <p>This card has no image.</p>
      </div>
      <div class="card">
        <img src="https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=300&h=150&fit=crop" alt="Mountain">
        <h3>Card with image</h3>
        <p>This card has an image — it gets different styling.</p>
      </div>
      <div class="card">
        <h3>Card without image</h3>
        <p>Another card without an image.</p>
      </div>
    </section>

    <section>
      <h2>:has() — Form Validation</h2>
      <form class="smart-form">
        <div class="field">
          <label for="name">Name</label>
          <input type="text" id="name" required placeholder="Enter name">
        </div>
        <div class="field">
          <label for="email">Email</label>
          <input type="email" id="email" required placeholder="Enter email">
        </div>
      </form>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `modern-selectors.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 16px; color: #2c3e50; }
section { margin-bottom: 50px; }

/* :is() — applies to h3 inside article OR section */
:is(article, section) h3 {
  color: #3498db;
  font-size: 1.2rem;
  margin-bottom: 8px;
}

:is(article, section) p {
  color: #666;
  margin-bottom: 16px;
}

/* :where() — zero specificity, easy to override */
:where(.main-nav, .footer-nav) a {
  color: #3498db;
  text-decoration: none;
  padding: 4px 8px;
}

/* This overrides :where() easily because it has higher specificity */
.footer-nav a {
  color: #666;
  font-size: 0.9rem;
}

/* :not() — style all li except .special and :last-child */
ul { list-style: none; padding: 0; }

li {
  padding: 10px 16px;
  border-bottom: 1px solid #eee;
}

li:not(.special):not(:last-child) {
  background: #ebf5fb;
}

li.special {
  background: #fef9e7;
  font-weight: bold;
}

li:last-child {
  border-bottom: none;
  background: #eafaf1;
}

/* :has() — card with image gets different layout */
.card {
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 1.5rem;
  margin-bottom: 1rem;
}

/* Card that HAS an image */
.card:has(img) {
  padding: 0;
  overflow: hidden;
}

.card:has(img) img {
  width: 100%;
  height: 150px;
  object-fit: cover;
  display: block;
}

.card:has(img) h3,
.card:has(img) p {
  padding: 0 1.5rem;
  margin-top: 1rem;
}

.card:has(img) p {
  margin-bottom: 1.5rem;
}

/* :has() — form field with invalid input */
.field {
  margin-bottom: 1rem;
}

label {
  display: block;
  font-weight: 600;
  margin-bottom: 4px;
  font-size: 0.9rem;
}

input {
  width: 100%;
  max-width: 400px;
  padding: 10px 14px;
  border: 2px solid #ddd;
  border-radius: 6px;
  font-size: 1rem;
  outline: none;
}

/* Field that HAS an invalid input */
.field:has(input:invalid:not(:placeholder-shown)) label {
  color: #e74c3c;
}

.field:has(input:invalid:not(:placeholder-shown)) input {
  border-color: #e74c3c;
}

/* Field that HAS a valid input */
.field:has(input:valid:not(:placeholder-shown)) input {
  border-color: #27ae60;
}
```

---

## Checklist

- [ ] `:is()` groups article and section selectors
- [ ] `:where()` has zero specificity (footer nav overrides it)
- [ ] `:not()` excludes `.special` and `:last-child`
- [ ] `:has(img)` changes card layout when image is present
- [ ] `:has(input:invalid)` styles the label red
- [ ] `:has(input:valid)` styles the input green
