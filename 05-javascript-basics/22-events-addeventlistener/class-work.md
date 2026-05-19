# Class Work — Events in Practice

## What You Will Build

A page that demonstrates click, keyboard, and form events with visual feedback — including a colour picker, a keyboard shortcut handler, and a form with live validation.

**Time:** 35 minutes  
**Output:** `events-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Events Practice</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; }
    .click-area {
      height: 120px; border-radius: 8px; background: #3498db;
      display: flex; align-items: center; justify-content: center;
      color: white; font-size: 1.1rem; font-weight: bold;
      cursor: pointer; user-select: none; transition: background 0.2s;
    }
    .click-area:hover { background: #2980b9; }
    .click-area:active { background: #1a6fa8; transform: scale(0.98); }
    .log { background: #1e293b; color: #e2e8f0; border-radius: 6px; padding: 0.75rem; font-family: monospace; font-size: 0.82rem; line-height: 1.8; max-height: 150px; overflow-y: auto; margin-top: 0.75rem; }
    .log-entry { border-bottom: 1px solid #334155; padding: 0.2rem 0; }
    .log-entry:last-child { border-bottom: none; }
    input, textarea { width: 100%; padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; font-family: inherit; }
    input:focus, textarea:focus { border-color: #3498db; }
    input.valid { border-color: #27ae60; }
    input.invalid { border-color: #e74c3c; }
    .field-hint { font-size: 0.8rem; margin-top: 0.25rem; }
    .field-hint.valid { color: #27ae60; }
    .field-hint.invalid { color: #e74c3c; }
    .form-group { margin-bottom: 1rem; }
    label { display: block; font-size: 0.85rem; font-weight: 600; margin-bottom: 0.3rem; }
    button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; font-family: inherit; }
    button:hover { background: #2980b9; }
    .key-display { background: #1e293b; color: #e2e8f0; border-radius: 8px; padding: 1rem; font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
    .key-badge { display: inline-block; background: #334155; border: 1px solid #475569; border-radius: 4px; padding: 0.1rem 0.4rem; font-size: 0.8rem; margin: 0.1rem; }
    .key-badge.active { background: #3498db; border-color: #3498db; }
  </style>
</head>
<body>
  <h1>Events Practice</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Click Events

Add this HTML before `<script>`:

```html
<h2>Click Events</h2>
<div class="card">
  <div class="click-area" id="click-area">Click me!</div>
  <div class="log" id="click-log">
    <div class="log-entry">Waiting for clicks...</div>
  </div>
</div>
```

Add this JavaScript:

```javascript
let clickCount = 0;
const clickArea = document.getElementById('click-area');
const clickLog = document.getElementById('click-log');

function addLog(message, container) {
  const entry = document.createElement('div');
  entry.className = 'log-entry';
  entry.textContent = message;
  container.insertBefore(entry, container.firstChild);
  // Keep only last 10 entries
  while (container.children.length > 10) {
    container.removeChild(container.lastChild);
  }
}

clickArea.addEventListener('click', (e) => {
  clickCount++;
  clickArea.textContent = `Clicked ${clickCount} time${clickCount !== 1 ? 's' : ''}!`;
  addLog(`Click #${clickCount} at (${e.clientX}, ${e.clientY})`, clickLog);
});

clickArea.addEventListener('dblclick', (e) => {
  clickArea.style.background = `hsl(${Math.random() * 360}, 70%, 50%)`;
  addLog('Double-click! Colour changed.', clickLog);
});

clickArea.addEventListener('contextmenu', (e) => {
  e.preventDefault(); // prevent browser context menu
  addLog('Right-click! (context menu prevented)', clickLog);
});
```

---

## Step 3 — Keyboard Events

Add this HTML:

```html
<h2>Keyboard Events</h2>
<div class="card">
  <input type="text" id="key-input" placeholder="Type here — press Escape to clear, Ctrl+Enter to submit">
  <div class="key-display" id="key-display" style="margin-top:0.75rem">
    Press any key...
  </div>
</div>
```

Add this JavaScript:

```javascript
const keyInput = document.getElementById('key-input');
const keyDisplay = document.getElementById('key-display');

keyInput.addEventListener('keydown', (e) => {
  // Keyboard shortcut: Escape to clear
  if (e.key === 'Escape') {
    keyInput.value = '';
    keyDisplay.textContent = 'Cleared with Escape!';
    return;
  }

  // Keyboard shortcut: Ctrl+Enter to submit
  if (e.key === 'Enter' && e.ctrlKey) {
    e.preventDefault();
    keyDisplay.innerHTML = `<strong>Submitted!</strong> Value: "${keyInput.value}"`;
    return;
  }

  // Show key info
  const modifiers = [
    e.ctrlKey && 'Ctrl',
    e.shiftKey && 'Shift',
    e.altKey && 'Alt',
    e.metaKey && 'Meta',
  ].filter(Boolean);

  keyDisplay.innerHTML = `
    Key: <span class="key-badge active">${e.key}</span>
    Code: <span class="key-badge">${e.code}</span>
    ${modifiers.length ? `Modifiers: ${modifiers.map(m => `<span class="key-badge active">${m}</span>`).join(' ')}` : ''}
    <br>Length: ${keyInput.value.length + (e.key.length === 1 ? 1 : 0)} chars
  `;
});
```

---

## Step 4 — Form Events with Validation

Add this HTML:

```html
<h2>Form Events</h2>
<div class="card">
  <form id="signup-form">
    <div class="form-group">
      <label>Username (3–20 characters)</label>
      <input type="text" id="username" placeholder="Enter username">
      <div class="field-hint" id="username-hint"></div>
    </div>
    <div class="form-group">
      <label>Email</label>
      <input type="email" id="email" placeholder="your@email.com">
      <div class="field-hint" id="email-hint"></div>
    </div>
    <button type="submit">Sign Up</button>
    <div id="form-result" style="margin-top:0.75rem;font-size:0.9rem"></div>
  </form>
</div>
```

Add this JavaScript:

```javascript
// Live validation on input
document.getElementById('username').addEventListener('input', (e) => {
  const val = e.target.value;
  const hint = document.getElementById('username-hint');
  if (val.length === 0) {
    e.target.className = '';
    hint.textContent = '';
  } else if (val.length < 3) {
    e.target.className = 'invalid';
    hint.className = 'field-hint invalid';
    hint.textContent = `Too short — ${3 - val.length} more character${3 - val.length !== 1 ? 's' : ''} needed`;
  } else if (val.length > 20) {
    e.target.className = 'invalid';
    hint.className = 'field-hint invalid';
    hint.textContent = `Too long — ${val.length - 20} character${val.length - 20 !== 1 ? 's' : ''} over limit`;
  } else {
    e.target.className = 'valid';
    hint.className = 'field-hint valid';
    hint.textContent = '✓ Username looks good!';
  }
});

document.getElementById('email').addEventListener('input', (e) => {
  const val = e.target.value;
  const hint = document.getElementById('email-hint');
  const isValid = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(val);
  if (val.length === 0) {
    e.target.className = '';
    hint.textContent = '';
  } else if (isValid) {
    e.target.className = 'valid';
    hint.className = 'field-hint valid';
    hint.textContent = '✓ Valid email address';
  } else {
    e.target.className = 'invalid';
    hint.className = 'field-hint invalid';
    hint.textContent = 'Please enter a valid email address';
  }
});

// Form submit
document.getElementById('signup-form').addEventListener('submit', (e) => {
  e.preventDefault(); // prevent page reload!
  const username = document.getElementById('username').value;
  const email = document.getElementById('email').value;
  const result = document.getElementById('form-result');

  if (!username || !email) {
    result.style.color = '#e74c3c';
    result.textContent = 'Please fill in all fields.';
    return;
  }

  result.style.color = '#27ae60';
  result.textContent = `✅ Account created for ${username} (${email})!`;
});
```

---

## Checklist

- [ ] Click event shows position and increments counter
- [ ] Double-click changes the colour
- [ ] Right-click is prevented and logged
- [ ] Keyboard events show the key name and code
- [ ] Escape clears the input
- [ ] Ctrl+Enter submits
- [ ] Username validation shows real-time feedback
- [ ] Email validation uses regex
- [ ] Form submit uses `e.preventDefault()` — page does NOT reload

---

## Bonus Challenges

1. Add a `mousemove` listener that shows the cursor position in real time
2. Add a `{ once: true }` button that can only be clicked once
3. Add a `focus`/`blur` listener that highlights the active form field with a coloured border
