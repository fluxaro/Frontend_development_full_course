# Class Work — Parameters, Return, and Scope

## What You Will Build

A set of utility functions demonstrating default parameters, rest parameters, early returns, and scope — with an interactive demo page.

**Time:** 30 minutes  
**Output:** `params-scope-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Parameters and Scope</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; }
    pre { background: #1e293b; color: #e2e8f0; padding: 0.75rem; border-radius: 6px; font-size: 0.82rem; overflow-x: auto; line-height: 1.6; }
    .result { font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
    .good { color: #27ae60; } .bad { color: #e74c3c; }
    .form-row { display: flex; gap: 0.75rem; align-items: center; margin-bottom: 0.75rem; flex-wrap: wrap; }
    input { padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; }
    input:focus { border-color: #3498db; }
    button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; }
    button:hover { background: #2980b9; }
    .output { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1rem; font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
  </style>
</head>
<body>
  <h1>Parameters, Return, and Scope</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Default Parameters

Add this HTML before `<script>`:

```html
<h2>Default Parameters</h2>
<div class="card" id="defaults-output"></div>
```

Add this JavaScript:

```javascript
// Default parameters
function createProfile(name, role = 'Student', level = 1) {
  return { name, role, level };
}

function formatPrice(amount, currency = 'USD', decimals = 2) {
  const symbols = { USD: '$', EUR: '€', GBP: '£', NGN: '₦' };
  const symbol = symbols[currency] || currency;
  return `${symbol}${amount.toFixed(decimals)}`;
}

const examples = [
  createProfile('Alex'),
  createProfile('Sam', 'Instructor'),
  createProfile('Jordan', 'Admin', 5),
];

document.getElementById('defaults-output').innerHTML = `
  <div class="result">
    ${examples.map(p => `createProfile → ${JSON.stringify(p)}`).join('<br>')}
    <br>
    formatPrice(29.99) → ${formatPrice(29.99)}<br>
    formatPrice(29.99, 'EUR') → ${formatPrice(29.99, 'EUR')}<br>
    formatPrice(5000, 'NGN', 0) → ${formatPrice(5000, 'NGN', 0)}
  </div>
`;
```

---

## Step 3 — Rest Parameters

Add this HTML:

```html
<h2>Rest Parameters</h2>
<div class="card" id="rest-output"></div>
```

Add this JavaScript:

```javascript
// Rest parameters collect remaining args into an array
function sum(...numbers) {
  return numbers.reduce((total, n) => total + n, 0);
}

function log(level, ...messages) {
  const timestamp = new Date().toLocaleTimeString();
  return `[${timestamp}] [${level.toUpperCase()}] ${messages.join(' ')}`;
}

function buildTag(tagName, className, ...children) {
  const childContent = children.join('');
  return `<${tagName} class="${className}">${childContent}</${tagName}>`;
}

document.getElementById('rest-output').innerHTML = `
  <div class="result">
    sum(1, 2, 3) → ${sum(1, 2, 3)}<br>
    sum(1, 2, 3, 4, 5, 6, 7, 8, 9, 10) → ${sum(1,2,3,4,5,6,7,8,9,10)}<br>
    log('info', 'Server started', 'Port 3000') → ${log('info', 'Server started', 'Port 3000')}<br>
    buildTag('div', 'card', '&lt;h2&gt;Title&lt;/h2&gt;', '&lt;p&gt;Body&lt;/p&gt;') → ${buildTag('div', 'card', '<h2>Title</h2>', '<p>Body</p>')}
  </div>
`;
```

---

## Step 4 — Early Return (Guard Clauses)

Add this HTML:

```html
<h2>Early Return — Guard Clauses</h2>
<div class="form-row">
  <input type="number" id="divide-a" placeholder="Dividend" value="10">
  <input type="number" id="divide-b" placeholder="Divisor" value="0">
  <button onclick="testDivide()">Divide</button>
</div>
<div class="output" id="divide-output"></div>
```

Add this JavaScript:

```javascript
// Guard clauses — return early for invalid cases
function safeDivide(a, b) {
  if (typeof a !== 'number' || typeof b !== 'number') return 'Error: both arguments must be numbers';
  if (b === 0) return 'Error: cannot divide by zero';
  if (!isFinite(a) || !isFinite(b)) return 'Error: infinite values not allowed';
  return a / b;
}

function getLetterGrade(score) {
  if (typeof score !== 'number') return 'Error: score must be a number';
  if (score < 0 || score > 100) return 'Error: score must be between 0 and 100';
  if (score >= 90) return 'A';
  if (score >= 80) return 'B';
  if (score >= 70) return 'C';
  if (score >= 60) return 'D';
  return 'F';
}

function testDivide() {
  const a = Number(document.getElementById('divide-a').value);
  const b = Number(document.getElementById('divide-b').value);
  const result = safeDivide(a, b);
  document.getElementById('divide-output').textContent =
    `safeDivide(${a}, ${b}) = ${result}`;
}

// Show grade examples
console.log('Grade examples:');
[105, -5, 95, 82, 71, 65, 45, 'hello'].forEach(s => {
  console.log(`getLetterGrade(${JSON.stringify(s)}) = ${getLetterGrade(s)}`);
});
```

---

## Step 5 — Scope Demonstration

Add this JavaScript:

```javascript
// Scope demonstration
const globalMessage = 'I am global — accessible everywhere';

function outerFunction() {
  const outerMessage = 'I am in outer — accessible in outer and inner';

  function innerFunction() {
    const innerMessage = 'I am in inner — only accessible here';
    console.log('From inner:', globalMessage);  // ✅
    console.log('From inner:', outerMessage);   // ✅ (closure)
    console.log('From inner:', innerMessage);   // ✅
  }

  innerFunction();
  console.log('From outer:', globalMessage);    // ✅
  console.log('From outer:', outerMessage);     // ✅
  // console.log(innerMessage); // ❌ ReferenceError
}

outerFunction();
// console.log(outerMessage); // ❌ ReferenceError

console.log('Scope chain test complete — check for errors above');
```

---

## Checklist

- [ ] Default parameters work when arguments are omitted
- [ ] Rest parameters collect all extra arguments into an array
- [ ] `sum()` with no arguments returns `0` (empty array reduce)
- [ ] Guard clauses return early for invalid input
- [ ] `safeDivide(10, 0)` returns an error message, not `Infinity`
- [ ] Scope chain is demonstrated — inner can access outer, but not vice versa

---

## Bonus Challenges

1. Write a `createCounter(start = 0, step = 1)` function that returns an object with `increment()`, `decrement()`, and `reset()` methods — demonstrating closure over `start` and `step`
2. Write a `pipe(...fns)` function that applies functions left to right: `pipe(double, addOne)(5)` → `11`
3. Write a `partial(fn, ...args)` function that partially applies arguments to a function
