# Class Work — Style Links and Forms with Attribute Selectors

## What You Will Build

Style links and form inputs using only attribute selectors.

**Time:** 25 minutes

---

## Step 1 — Create the HTML

Create `attribute-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Attribute Selectors Demo</title>
  <link rel="stylesheet" href="attribute-selectors.css">
</head>
<body>

  <main>
    <h1>Attribute Selectors Demo</h1>

    <section>
      <h2>Link Types</h2>
      <ul>
        <li><a href="/about">Internal link</a></li>
        <li><a href="https://github.com" target="_blank">External link (GitHub)</a></li>
        <li><a href="https://google.com" target="_blank">External link (Google)</a></li>
        <li><a href="mailto:hello@example.com">Email link</a></li>
        <li><a href="tel:+15551234567">Phone link</a></li>
        <li><a href="document.pdf">PDF download</a></li>
        <li><a href="archive.zip">ZIP download</a></li>
        <li><a href="photo.jpg">Image link</a></li>
      </ul>
    </section>

    <section>
      <h2>Form Inputs</h2>
      <form>
        <input type="text" placeholder="Text input" required>
        <input type="email" placeholder="Email input" required>
        <input type="password" placeholder="Password">
        <input type="number" placeholder="Number" min="0" max="100">
        <input type="text" placeholder="Disabled input" disabled>
        <input type="text" placeholder="Readonly input" readonly>
        <button type="submit">Submit</button>
      </form>
    </section>

    <section>
      <h2>Data Attribute Cards</h2>
      <div class="cards">
        <div data-variant="default">Default Card</div>
        <div data-variant="primary">Primary Card</div>
        <div data-variant="success">Success Card</div>
        <div data-variant="danger">Danger Card</div>
      </div>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `attribute-selectors.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 16px; color: #2c3e50; }
section { margin-bottom: 50px; }
ul { list-style: none; padding: 0; }
li { margin-bottom: 8px; }

/* All links */
a { text-decoration: none; color: #333; }

/* Internal links */
a[href^="/"] { color: #2c3e50; }
a[href^="/"]:hover { text-decoration: underline; }

/* External links */
a[href^="http"] { color: #3498db; }
a[href^="http"]::after { content: ' ↗'; font-size: 0.8em; }

/* Email links */
a[href^="mailto"] { color: #27ae60; }
a[href^="mailto"]::before { content: '✉ '; }

/* Phone links */
a[href^="tel"] { color: #9b59b6; }
a[href^="tel"]::before { content: '📞 '; }

/* PDF links */
a[href$=".pdf"] { color: #e74c3c; }
a[href$=".pdf"]::before { content: '📄 '; }

/* ZIP links */
a[href$=".zip"] { color: #f39c12; }
a[href$=".zip"]::before { content: '📦 '; }

/* Image links */
a[href$=".jpg"], a[href$=".png"], a[href$=".webp"] { color: #1abc9c; }
a[href$=".jpg"]::before, a[href$=".png"]::before { content: '🖼 '; }

/* Form inputs */
form { display: flex; flex-direction: column; gap: 12px; max-width: 400px; }

input {
  padding: 10px 14px;
  border: 2px solid #ddd;
  border-radius: 6px;
  font-size: 1rem;
  outline: none;
}

/* Required inputs */
input[required] { border-left: 4px solid #f39c12; }

/* Email inputs */
input[type="email"] { border-left: 4px solid #3498db; }

/* Disabled inputs */
input[disabled] { opacity: 0.5; cursor: not-allowed; background: #f0f0f0; }

/* Readonly inputs */
input[readonly] { background: #f8f9fa; cursor: default; }

/* Number inputs */
input[type="number"] { border-left: 4px solid #9b59b6; }

/* Data attribute cards */
.cards { display: flex; gap: 1rem; flex-wrap: wrap; }

[data-variant] {
  padding: 1.5rem;
  border-radius: 8px;
  font-weight: bold;
  color: white;
  min-width: 150px;
  text-align: center;
}

[data-variant="default"] { background: #95a5a6; }
[data-variant="primary"]  { background: #3498db; }
[data-variant="success"]  { background: #27ae60; }
[data-variant="danger"]   { background: #e74c3c; }
```

---

## Checklist

- [ ] External links have `↗` arrow
- [ ] Email links have `✉` icon
- [ ] PDF links have `📄` icon
- [ ] Required inputs have orange left border
- [ ] Disabled inputs are grayed out
- [ ] Data attribute cards have different colors
