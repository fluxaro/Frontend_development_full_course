# Class Work — DOM Manipulation in Practice

## What You Will Build

A page with a live character counter, a dark mode toggle, and a card state manager — demonstrating `textContent`, `classList`, and `style` manipulation.

**Time:** 35 minutes  
**Output:** `dom-manipulation-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>DOM Manipulation Practice</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    /* Theme variables */
    [data-theme="light"] {
      --bg: #f8f9fa; --surface: #ffffff; --text: #333; --border: #dee2e6;
    }
    [data-theme="dark"] {
      --bg: #0f172a; --surface: #1e293b; --text: #e2e8f0; --border: #334155;
    }

    body { font-family: sans-serif; background: var(--bg); color: var(--text); padding: 2rem; transition: background 0.3s, color 0.3s; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid var(--border); padding-bottom: 0.5rem; }
    .card { background: var(--surface); border: 1px solid var(--border); border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; transition: background 0.3s, border-color 0.3s; }
    .card.active { border-color: #3498db; border-width: 2px; }
    .card.featured { background: #ebf5fb; }
    [data-theme="dark"] .card.featured { background: #1a3a5c; }
    textarea { width: 100%; padding: 0.75rem; border: 2px solid var(--border); border-radius: 6px; font-size: 0.9rem; font-family: inherit; resize: vertical; background: var(--surface); color: var(--text); outline: none; }
    textarea:focus { border-color: #3498db; }
    .counter { font-size: 0.85rem; color: #888; text-align: right; margin-top: 0.25rem; }
    .counter.warn { color: #f39c12; }
    .counter.danger { color: #e74c3c; font-weight: bold; }
    button { padding: 0.5rem 1rem; border: none; border-radius: 6px; cursor: pointer; font-size: 0.85rem; font-family: inherit; margin: 0.25rem; }
    .btn-blue { background: #3498db; color: white; }
    .btn-green { background: #27ae60; color: white; }
    .btn-orange { background: #e67e22; color: white; }
    .btn-dark { background: #2c3e50; color: white; }
    .btn-light { background: #ecf0f1; color: #333; }
    .card-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 1rem; }
    .badge { display: inline-block; padding: 0.2rem 0.6rem; border-radius: 999px; font-size: 0.75rem; font-weight: bold; }
    .badge-active { background: #d6eaf8; color: #1a5276; }
    .badge-featured { background: #d5f5e3; color: #1e8449; }
    .badge-default { background: #f0f0f0; color: #888; }
  </style>
</head>
<body>
  <h1>DOM Manipulation Practice</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Dark Mode Toggle (classList on body)

Add this HTML before `<script>`:

```html
<h2>Dark Mode Toggle (classList)</h2>
<div class="card">
  <p style="margin-bottom:1rem">Toggle the theme by adding/removing a class on the &lt;html&gt; element.</p>
  <button class="btn-dark" onclick="setTheme('dark')">🌙 Dark Mode</button>
  <button class="btn-light" onclick="setTheme('light')">☀️ Light Mode</button>
  <p id="theme-status" style="margin-top:0.75rem;font-size:0.85rem;color:#888"></p>
</div>
```

Add this JavaScript:

```javascript
function setTheme(theme) {
  document.documentElement.setAttribute('data-theme', theme);
  document.getElementById('theme-status').textContent =
    `Current theme: ${theme} (set via setAttribute on <html>)`;
}
setTheme('light'); // initialise
```

---

## Step 3 — Live Character Counter (textContent)

Add this HTML:

```html
<h2>Live Character Counter (textContent)</h2>
<div class="card">
  <textarea id="tweet-input" rows="4" maxlength="280" placeholder="What's happening? (max 280 characters)"></textarea>
  <div class="counter" id="char-counter">0 / 280</div>
</div>
```

Add this JavaScript:

```javascript
const tweetInput = document.getElementById('tweet-input');
const charCounter = document.getElementById('char-counter');

tweetInput.addEventListener('input', () => {
  const count = tweetInput.value.length;
  const max = 280;
  const remaining = max - count;

  // Update text using textContent
  charCounter.textContent = `${count} / ${max}`;

  // Update class based on remaining characters
  charCounter.classList.remove('warn', 'danger');
  if (remaining <= 20) charCounter.classList.add('danger');
  else if (remaining <= 50) charCounter.classList.add('warn');
});
```

---

## Step 4 — Card State Manager (classList)

Add this HTML:

```html
<h2>Card State Manager (classList)</h2>
<div class="card-grid" id="card-grid"></div>
```

Add this JavaScript:

```javascript
const cardData = [
  { id: 1, title: 'Project Alpha', desc: 'Frontend redesign' },
  { id: 2, title: 'Project Beta', desc: 'API integration' },
  { id: 3, title: 'Project Gamma', desc: 'Mobile app' },
  { id: 4, title: 'Project Delta', desc: 'Dashboard' },
];

function renderCards() {
  document.getElementById('card-grid').innerHTML = cardData.map(card => {
    const el = document.getElementById(`card-${card.id}`);
    const isActive = el ? el.classList.contains('active') : false;
    const isFeatured = el ? el.classList.contains('featured') : false;

    return `
      <div class="card" id="card-${card.id}">
        <div style="display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:0.5rem">
          <h3 style="font-size:0.95rem">${card.title}</h3>
          <span class="badge ${isActive ? 'badge-active' : isFeatured ? 'badge-featured' : 'badge-default'}">
            ${isActive ? 'Active' : isFeatured ? 'Featured' : 'Default'}
          </span>
        </div>
        <p style="font-size:0.85rem;color:#666;margin-bottom:0.75rem">${card.desc}</p>
        <button class="btn-blue" onclick="toggleClass(${card.id}, 'active')">Toggle Active</button>
        <button class="btn-green" onclick="toggleClass(${card.id}, 'featured')">Toggle Featured</button>
      </div>
    `;
  }).join('');
}

function toggleClass(id, className) {
  const card = document.getElementById(`card-${id}`);
  if (card) {
    card.classList.toggle(className);
    // Update badge text
    const badge = card.querySelector('.badge');
    const isActive = card.classList.contains('active');
    const isFeatured = card.classList.contains('featured');
    badge.className = `badge ${isActive ? 'badge-active' : isFeatured ? 'badge-featured' : 'badge-default'}`;
    badge.textContent = isActive ? 'Active' : isFeatured ? 'Featured' : 'Default';
  }
}

renderCards();
```

---

## Step 5 — Attribute Manipulation

Add this HTML:

```html
<h2>Attribute Manipulation</h2>
<div class="card">
  <div class="form-row" style="display:flex;gap:0.75rem;margin-bottom:0.75rem;flex-wrap:wrap">
    <input type="text" id="attr-input" placeholder="Type something..." style="flex:1;padding:0.5rem 0.75rem;border:2px solid #dee2e6;border-radius:6px;font-size:0.9rem;outline:none">
    <button class="btn-orange" onclick="toggleDisabled()">Toggle Disabled</button>
    <button class="btn-blue" onclick="toggleRequired()">Toggle Required</button>
  </div>
  <p id="attr-status" style="font-size:0.85rem;color:#888"></p>
</div>
```

Add this JavaScript:

```javascript
function toggleDisabled() {
  const input = document.getElementById('attr-input');
  input.toggleAttribute('disabled');
  updateAttrStatus();
}

function toggleRequired() {
  const input = document.getElementById('attr-input');
  input.toggleAttribute('required');
  updateAttrStatus();
}

function updateAttrStatus() {
  const input = document.getElementById('attr-input');
  const attrs = [];
  if (input.hasAttribute('disabled')) attrs.push('disabled');
  if (input.hasAttribute('required')) attrs.push('required');
  document.getElementById('attr-status').textContent =
    attrs.length ? `Active attributes: ${attrs.join(', ')}` : 'No special attributes';
}
```

---

## Checklist

- [ ] Dark mode toggle adds/removes `data-theme` attribute on `<html>`
- [ ] Character counter updates `textContent` on every keystroke
- [ ] Counter changes class to `warn` at 50 chars remaining, `danger` at 20
- [ ] Card "Toggle Active" adds/removes `.active` class
- [ ] Card "Toggle Featured" adds/removes `.featured` class
- [ ] Badge text updates to reflect current state
- [ ] `toggleAttribute` correctly enables/disables the input

---

## Bonus Challenges

1. Add a "Copy to Clipboard" button that reads `textContent` from a card and copies it
2. Add a live preview that shows the tweet formatted with hashtags highlighted in blue
3. Add a "Reset All Cards" button that removes all classes from all cards
