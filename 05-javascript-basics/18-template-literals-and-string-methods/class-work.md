# Class Work — Template Literals and String Methods

## What You Will Build

An interactive string playground that demonstrates template literals and the most important string methods with live examples.

**Time:** 30 minutes  
**Output:** `strings-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Strings Practice</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; }
    .result { font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
    .good { color: #27ae60; font-weight: bold; }
    .blue { color: #3498db; font-weight: bold; }
    .form-row { display: flex; gap: 0.75rem; align-items: center; margin-bottom: 0.75rem; flex-wrap: wrap; }
    input, textarea { padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; font-family: inherit; }
    input:focus, textarea:focus { border-color: #3498db; }
    textarea { width: 100%; resize: vertical; }
    button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; }
    button:hover { background: #2980b9; }
    .output { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1rem; font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
    .stat-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); gap: 0.75rem; }
    .stat { background: #f0f0f0; border-radius: 6px; padding: 0.75rem; text-align: center; }
    .stat-val { font-size: 1.5rem; font-weight: bold; color: #3498db; }
    .stat-label { font-size: 0.75rem; color: #888; margin-top: 0.25rem; }
  </style>
</head>
<body>
  <h1>Template Literals and String Methods</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Template Literals

Add this HTML before `<script>`:

```html
<h2>Template Literals</h2>
<div class="card" id="template-demo"></div>
```

Add this JavaScript:

```javascript
const name = 'Alex Rivera';
const role = 'Frontend Developer';
const years = 3;
const skills = ['HTML', 'CSS', 'JavaScript', 'React'];
const score = 92;

// Basic interpolation
const greeting = `Hello, ${name}!`;

// Expression
const experience = `${years} year${years !== 1 ? 's' : ''} of experience`;

// Conditional
const level = `${score >= 90 ? '🏆 Expert' : score >= 70 ? '⭐ Intermediate' : '📚 Beginner'}`;

// Multi-line
const bio = `
Name: ${name}
Role: ${role}
Experience: ${experience}
Skills: ${skills.join(', ')}
Level: ${level}
`.trim();

// Nested template literal
const skillList = `<ul>${skills.map(s => `<li>${s}</li>`).join('')}</ul>`;

document.getElementById('template-demo').innerHTML = `
  <div class="result">
    greeting: <span class="good">"${greeting}"</span><br>
    experience: <span class="good">"${experience}"</span><br>
    level: <span class="good">"${level}"</span><br>
    <br>
    <strong>Multi-line bio:</strong><br>
    <pre style="background:#f0f0f0;padding:0.75rem;border-radius:6px;font-size:0.82rem">${bio}</pre>
    <br>
    <strong>Nested template (skill list):</strong><br>
    ${skillList}
  </div>
`;
```

---

## Step 3 — String Methods Demo

Add this HTML:

```html
<h2>String Methods</h2>
<div class="card" id="methods-demo"></div>
```

Add this JavaScript:

```javascript
const sample = '  Hello, World! This is JavaScript.  ';

const methods = [
  { name: 'trim()', result: sample.trim() },
  { name: 'toUpperCase()', result: sample.trim().toUpperCase() },
  { name: 'toLowerCase()', result: sample.trim().toLowerCase() },
  { name: "includes('World')", result: String(sample.includes('World')) },
  { name: "startsWith('  Hello')", result: String(sample.startsWith('  Hello')) },
  { name: 'slice(2, 7)', result: sample.slice(2, 7) },
  { name: "replace('World', 'JS')", result: sample.replace('World', 'JS') },
  { name: "split(' ')", result: JSON.stringify(sample.trim().split(' ')) },
  { name: "'5'.padStart(3, '0')", result: '5'.padStart(3, '0') },
  { name: "'ha'.repeat(3)", result: 'ha'.repeat(3) },
  { name: 'length', result: String(sample.length) },
];

document.getElementById('methods-demo').innerHTML = `
  <div class="result">
    Input: <span class="blue">"${sample}"</span><br><br>
    ${methods.map(m => `<strong>${m.name}</strong> → <span class="good">${m.result}</span>`).join('<br>')}
  </div>
`;
```

---

## Step 4 — Live String Inspector

Add this HTML:

```html
<h2>Live String Inspector</h2>
<textarea id="text-input" rows="4" placeholder="Type something here...">Hello, World! This is a test.</textarea>
<div class="stat-grid" id="stats-grid" style="margin-top:1rem"></div>
```

Add this JavaScript:

```javascript
function updateStats() {
  const text = document.getElementById('text-input').value;
  const words = text.trim() ? text.trim().split(/\s+/) : [];

  const stats = [
    { val: text.length, label: 'Characters' },
    { val: words.length, label: 'Words' },
    { val: text.split('\n').length, label: 'Lines' },
    { val: new Set(words.map(w => w.toLowerCase())).size, label: 'Unique Words' },
    { val: words.reduce((max, w) => w.length > max.length ? w : max, ''), label: 'Longest Word' },
  ];

  document.getElementById('stats-grid').innerHTML = stats.map(s => `
    <div class="stat">
      <div class="stat-val">${s.val}</div>
      <div class="stat-label">${s.label}</div>
    </div>
  `).join('');
}

document.getElementById('text-input').addEventListener('input', updateStats);
updateStats(); // run on load
```

---

## Checklist

- [ ] Template literals use backticks and `${}`
- [ ] Multi-line template literal preserves line breaks
- [ ] Nested template literals work (map inside template)
- [ ] `trim()` removes whitespace from both ends
- [ ] `includes()` returns boolean
- [ ] `slice()` extracts a portion of the string
- [ ] `replace()` replaces first match only
- [ ] Live inspector updates on every keystroke

---

## Bonus Challenges

1. Add a "Capitalise Words" button that capitalises the first letter of each word
2. Add a "Reverse Words" button that reverses the order of words (not characters)
3. Add a "Count Vowels" stat to the live inspector
