# Class Work — Decorate a Page with ::before and ::after

## What You Will Build

A styled article page using `::before` and `::after` for decorative elements — no extra HTML needed.

**Time:** 35 minutes

---

## Step 1 — Create the HTML

Create `pseudo-elements-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pseudo-elements Demo</title>
  <link rel="stylesheet" href="pseudo-elements.css">
</head>
<body>

  <header>
    <h1>CSS Pseudo-elements</h1>
    <nav>
      <a href="#section1">Section 1</a>
      <a href="https://example.com" target="_blank">External Link</a>
      <a href="https://docs.example.com" target="_blank">Docs</a>
    </nav>
  </header>

  <main>

    <section id="section1">
      <h2>Decorated Headings</h2>
      <p>This heading has a colored underline added with <code>::after</code>.</p>
    </section>

    <section>
      <h2>Custom List Bullets</h2>
      <ul class="custom-list">
        <li>First item with custom bullet</li>
        <li>Second item with custom bullet</li>
        <li>Third item with custom bullet</li>
      </ul>
    </section>

    <section>
      <h2>Blockquote with Quote Marks</h2>
      <blockquote>
        <p>The best way to learn CSS is to build things and break things.</p>
        <footer>— A wise developer</footer>
      </blockquote>
    </section>

    <section>
      <h2>Required Form Fields</h2>
      <form>
        <div>
          <label class="required" for="name">Full Name</label>
          <input type="text" id="name" placeholder="Enter your name">
        </div>
        <div>
          <label class="required" for="email">Email</label>
          <input type="email" id="email" placeholder="Enter your email">
        </div>
        <div>
          <label for="website">Website</label>
          <input type="url" id="website" placeholder="Optional">
        </div>
      </form>
    </section>

    <section>
      <h2>Tooltip Demo</h2>
      <p>Hover over these elements to see tooltips:</p>
      <button data-tooltip="Click to save your work">Save</button>
      <button data-tooltip="This will delete permanently">Delete</button>
    </section>

    <section>
      <h2>Card with Overlay</h2>
      <div class="card">
        <h3>Hover Over Me</h3>
        <p>The card gets a dark overlay on hover using ::after.</p>
      </div>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `pseudo-elements.css`:

```css
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: sans-serif;
  color: #333;
  line-height: 1.6;
  background: #f8f9fa;
}

header {
  background: #2c3e50;
  padding: 20px 40px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

header h1 { color: white; }

nav a {
  color: #bdc3c7;
  text-decoration: none;
  margin-left: 20px;
}

/* External link arrow using ::after */
nav a[target="_blank"]::after {
  content: ' ↗';
  font-size: 0.8em;
  color: #3498db;
}

main {
  max-width: 800px;
  margin: 40px auto;
  padding: 0 20px;
}

section {
  margin-bottom: 50px;
}

/* Heading with underline using ::after */
h2 {
  position: relative;
  padding-bottom: 12px;
  margin-bottom: 20px;
  color: #2c3e50;
}

h2::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 50px;
  height: 3px;
  background-color: #3498db;
  border-radius: 2px;
}

/* Custom list bullets using ::before */
.custom-list {
  list-style: none;
  padding: 0;
}

.custom-list li {
  position: relative;
  padding-left: 28px;
  margin-bottom: 10px;
}

.custom-list li::before {
  content: '→';
  position: absolute;
  left: 0;
  color: #3498db;
  font-weight: bold;
}

/* Blockquote with large quote mark using ::before */
blockquote {
  position: relative;
  padding: 20px 20px 20px 70px;
  background: white;
  border-radius: 8px;
  border-left: 4px solid #3498db;
  font-style: italic;
}

blockquote::before {
  content: '"';
  position: absolute;
  left: 15px;
  top: -5px;
  font-size: 5rem;
  color: #3498db;
  line-height: 1;
  font-family: Georgia, serif;
}

blockquote footer {
  margin-top: 10px;
  font-style: normal;
  font-size: 0.9rem;
  color: #666;
}

/* Required field asterisk using ::after */
label.required::after {
  content: ' *';
  color: #e74c3c;
  font-weight: bold;
}

form div {
  margin-bottom: 16px;
}

label {
  display: block;
  font-weight: 600;
  margin-bottom: 4px;
  font-size: 0.9rem;
}

input {
  width: 100%;
  padding: 10px 14px;
  border: 2px solid #ddd;
  border-radius: 6px;
  font-size: 1rem;
}

/* Tooltip using ::after */
[data-tooltip] {
  position: relative;
  padding: 10px 20px;
  background: #3498db;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  margin-right: 10px;
}

[data-tooltip]::after {
  content: attr(data-tooltip);
  position: absolute;
  bottom: calc(100% + 8px);
  left: 50%;
  transform: translateX(-50%);
  background: #2c3e50;
  color: white;
  padding: 6px 12px;
  border-radius: 4px;
  font-size: 0.8rem;
  white-space: nowrap;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.2s;
}

[data-tooltip]:hover::after {
  opacity: 1;
}

/* Card with overlay using ::after */
.card {
  position: relative;
  background: white;
  padding: 30px;
  border-radius: 8px;
  border: 1px solid #ddd;
  overflow: hidden;
  cursor: pointer;
}

.card::after {
  content: '';
  position: absolute;
  inset: 0;
  background: rgba(52, 152, 219, 0);
  transition: background 0.3s;
}

.card:hover::after {
  background: rgba(52, 152, 219, 0.15);
}
```

---

## Checklist

- [ ] `::after` adds underline to h2 headings
- [ ] `::after` adds arrow to external links
- [ ] `::before` adds custom bullets to list
- [ ] `::before` adds large quote mark to blockquote
- [ ] `::after` adds asterisk to required labels
- [ ] `::after` creates tooltip on hover
- [ ] `::after` creates overlay on card hover
