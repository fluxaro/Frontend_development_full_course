# Class Work — Selecting DOM Elements

## What You Will Build

A page that demonstrates all DOM selection methods with visual highlighting, showing the difference between `getElementById`, `querySelector`, and `querySelectorAll`.

**Time:** 30 minutes  
**Output:** `dom-selection-practice.html`

---

## Step 1 — Create the HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>DOM Selection Practice</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: sans-serif; background: #f8f9fa; color: #333; }

    /* Control panel */
    .controls {
      position: sticky; top: 0; z-index: 100;
      background: #2c3e50; padding: 1rem 2rem;
      display: flex; gap: 0.5rem; flex-wrap: wrap; align-items: center;
    }
    .controls span { color: white; font-size: 0.85rem; margin-right: 0.5rem; }
    .btn { padding: 0.4rem 0.9rem; border: none; border-radius: 4px; cursor: pointer; font-size: 0.8rem; font-family: inherit; }
    .btn-blue { background: #3498db; color: white; }
    .btn-green { background: #27ae60; color: white; }
    .btn-orange { background: #e67e22; color: white; }
    .btn-red { background: #e74c3c; color: white; }
    .btn-clear { background: #95a5a6; color: white; }

    /* Page content */
    main { max-width: 900px; margin: 0 auto; padding: 2rem; }
    h1 { font-size: 1.75rem; margin-bottom: 0.5rem; }
    h2 { font-size: 1.2rem; margin: 2rem 0 1rem; }
    p { color: #666; line-height: 1.6; margin-bottom: 1rem; }
    .card-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; margin-bottom: 2rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; }
    .card h3 { font-size: 0.95rem; margin-bottom: 0.5rem; }
    .card p { font-size: 0.85rem; }
    .card.featured { border-color: #3498db; }
    form { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.5rem; }
    .form-group { margin-bottom: 1rem; }
    label { display: block; font-size: 0.85rem; font-weight: 600; margin-bottom: 0.3rem; }
    input, select { width: 100%; padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; }

    /* Highlight styles */
    .highlight-blue { outline: 3px solid #3498db !important; outline-offset: 2px; }
    .highlight-green { outline: 3px solid #27ae60 !important; outline-offset: 2px; }
    .highlight-orange { outline: 3px solid #e67e22 !important; outline-offset: 2px; }

    /* Info panel */
    .info-panel { background: #1e293b; color: #e2e8f0; border-radius: 8px; padding: 1rem; margin-top: 1rem; font-family: monospace; font-size: 0.85rem; line-height: 1.8; min-height: 60px; }
  </style>
</head>
<body>

  <!-- Control Panel -->
  <div class="controls">
    <span>Select:</span>
    <button class="btn btn-blue" onclick="selectById()">getElementById('hero')</button>
    <button class="btn btn-blue" onclick="selectFirst()">querySelector('h1')</button>
    <button class="btn btn-green" onclick="selectAll()">querySelectorAll('.card')</button>
    <button class="btn btn-orange" onclick="selectInput()">querySelector('input[type=email]')</button>
    <button class="btn btn-orange" onclick="selectFeatured()">querySelector('.featured')</button>
    <button class="btn btn-red" onclick="selectLinks()">querySelectorAll('a')</button>
    <button class="btn btn-clear" onclick="clearHighlights()">Clear</button>
  </div>

  <!-- Page Content -->
  <main>
    <section id="hero">
      <h1>DOM Selection Practice</h1>
      <p>Click the buttons above to select elements using different methods. Selected elements will be highlighted.</p>
      <p>Visit our <a href="#">documentation</a> or <a href="#">GitHub</a> for more info.</p>
    </section>

    <h2>Product Cards</h2>
    <div class="card-grid">
      <div class="card" id="card-1">
        <h3>Card One</h3>
        <p>First card in the grid.</p>
      </div>
      <div class="card featured" id="card-2">
        <h3>Card Two (Featured)</h3>
        <p>This card has the .featured class.</p>
      </div>
      <div class="card" id="card-3">
        <h3>Card Three</h3>
        <p>Third card in the grid.</p>
      </div>
    </div>

    <h2>Contact Form</h2>
    <form id="contact-form">
      <div class="form-group">
        <label>Name</label>
        <input type="text" id="name-input" placeholder="Your name">
      </div>
      <div class="form-group">
        <label>Email</label>
        <input type="email" id="email-input" placeholder="your@email.com">
      </div>
      <div class="form-group">
        <label>Subject</label>
        <select id="subject-select">
          <option>General Enquiry</option>
          <option>Support</option>
          <option>Feedback</option>
        </select>
      </div>
    </form>

    <div class="info-panel" id="info-panel">
      Click a selection button above to see results here...
    </div>
  </main>

  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Add the JavaScript

Inside `<script>`:

```javascript
function clearHighlights() {
  document.querySelectorAll('.highlight-blue, .highlight-green, .highlight-orange').forEach(el => {
    el.classList.remove('highlight-blue', 'highlight-green', 'highlight-orange');
  });
  document.getElementById('info-panel').textContent = 'Highlights cleared.';
}

function showInfo(method, elements) {
  const count = elements.length !== undefined ? elements.length : 1;
  const list = elements.length !== undefined
    ? Array.from(elements).map(el => `<${el.tagName.toLowerCase()}${el.id ? '#'+el.id : ''}${el.className ? '.'+el.className.split(' ').join('.') : ''}>`)
    : [`<${elements.tagName.toLowerCase()}${elements.id ? '#'+elements.id : ''}>`];

  document.getElementById('info-panel').innerHTML =
    `Method: <strong>${method}</strong>\n` +
    `Matched: <strong>${count}</strong> element${count !== 1 ? 's' : ''}\n` +
    list.map(l => `  → ${l}`).join('\n');
}

function selectById() {
  clearHighlights();
  const el = document.getElementById('hero');
  if (el) {
    el.classList.add('highlight-blue');
    showInfo("getElementById('hero')", { length: 1, 0: el });
  }
}

function selectFirst() {
  clearHighlights();
  const el = document.querySelector('h1');
  if (el) {
    el.classList.add('highlight-blue');
    showInfo("querySelector('h1')", { length: 1, 0: el });
  }
}

function selectAll() {
  clearHighlights();
  const els = document.querySelectorAll('.card');
  els.forEach(el => el.classList.add('highlight-green'));
  showInfo("querySelectorAll('.card')", els);
}

function selectInput() {
  clearHighlights();
  const el = document.querySelector('input[type="email"]');
  if (el) {
    el.classList.add('highlight-orange');
    showInfo("querySelector('input[type=\"email\"]')", { length: 1, 0: el });
  }
}

function selectFeatured() {
  clearHighlights();
  const el = document.querySelector('.featured');
  if (el) {
    el.classList.add('highlight-orange');
    showInfo("querySelector('.featured')", { length: 1, 0: el });
  }
}

function selectLinks() {
  clearHighlights();
  const els = document.querySelectorAll('a');
  els.forEach(el => el.classList.add('highlight-orange'));
  showInfo("querySelectorAll('a')", els);
}
```

---

## Checklist

- [ ] `getElementById` selects the hero section by ID
- [ ] `querySelector('h1')` selects only the first h1
- [ ] `querySelectorAll('.card')` selects all 3 cards
- [ ] `querySelector('input[type="email"]')` selects the email input
- [ ] `querySelector('.featured')` selects only the featured card
- [ ] `querySelectorAll('a')` selects all links
- [ ] Clear button removes all highlights
- [ ] Info panel shows the method used and count of matched elements

---

## Bonus Challenges

1. Add a custom CSS selector input where the user types any selector and the matching elements are highlighted
2. Add a "Traverse" button that starts from a card and navigates to its parent, siblings, and children
3. Show the difference between `querySelector` (first match) and `querySelectorAll` (all matches) for the same selector
