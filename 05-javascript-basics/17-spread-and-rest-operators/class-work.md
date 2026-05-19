# Class Work — Spread and Rest in Practice

## What You Will Build

A page demonstrating spread for merging/copying arrays and objects, and rest for collecting function arguments — with a practical immutable update demo.

**Time:** 30 minutes  
**Output:** `spread-rest-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Spread and Rest Practice</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; }
    .result { font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
    .good { color: #27ae60; font-weight: bold; }
    .warn { color: #e74c3c; font-weight: bold; }
    .blue { color: #3498db; font-weight: bold; }
    .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
    .form-row { display: flex; gap: 0.75rem; align-items: center; margin-bottom: 0.75rem; flex-wrap: wrap; }
    input { padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; }
    input:focus { border-color: #3498db; }
    button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; }
    button:hover { background: #2980b9; }
  </style>
</head>
<body>
  <h1>Spread and Rest Operators</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Spread Arrays

Add this HTML before `<script>`:

```html
<h2>Spread Arrays</h2>
<div class="card" id="spread-arrays"></div>
```

Add this JavaScript:

```javascript
const frontend = ['HTML', 'CSS', 'JavaScript'];
const backend = ['Node.js', 'Python', 'SQL'];
const tools = ['Git', 'VS Code'];

// Merge
const allSkills = [...frontend, ...backend, ...tools];

// Copy (new array)
const frontendCopy = [...frontend];
frontendCopy.push('TypeScript');

// Add elements
const withReact = ['React', ...frontend, 'Vue'];

// Remove duplicates
const withDupes = [1, 2, 2, 3, 3, 3, 4];
const unique = [...new Set(withDupes)];

// Spread string
const chars = [..."hello"];

document.getElementById('spread-arrays').innerHTML = `
  <div class="result">
    frontend: [${frontend}]<br>
    backend: [${backend}]<br>
    <br>
    merged: <span class="good">[${allSkills}]</span><br>
    <br>
    frontendCopy (after push): <span class="good">[${frontendCopy}]</span><br>
    original frontend unchanged: <span class="good">[${frontend}]</span><br>
    <br>
    withReact: <span class="good">[${withReact}]</span><br>
    unique: <span class="good">[${unique}]</span><br>
    chars: <span class="good">[${chars}]</span>
  </div>
`;
```

---

## Step 3 — Spread Objects

Add this HTML:

```html
<h2>Spread Objects</h2>
<div class="card" id="spread-objects"></div>
```

Add this JavaScript:

```javascript
const defaults = { theme: 'light', lang: 'en', fontSize: 16, notifications: true };
const userPrefs = { theme: 'dark', fontSize: 18 };

// Merge (userPrefs overrides defaults)
const config = { ...defaults, ...userPrefs };

// Copy
const configCopy = { ...config };
configCopy.lang = 'fr';

// Add/override properties
const user = { name: 'Alex', age: 25, role: 'user' };
const promoted = { ...user, role: 'admin', promotedAt: '2026-01-01' };

// Remove property (spread + destructuring)
const { password, ...safeUser } = { ...user, password: 'secret123' };

document.getElementById('spread-objects').innerHTML = `
  <div class="result">
    defaults: ${JSON.stringify(defaults)}<br>
    userPrefs: ${JSON.stringify(userPrefs)}<br>
    merged config: <span class="good">${JSON.stringify(config)}</span><br>
    <br>
    configCopy.lang = 'fr': <span class="good">${JSON.stringify(configCopy)}</span><br>
    original config.lang unchanged: <span class="good">${config.lang}</span><br>
    <br>
    promoted: <span class="good">${JSON.stringify(promoted)}</span><br>
    safeUser (no password): <span class="good">${JSON.stringify(safeUser)}</span>
  </div>
`;
```

---

## Step 4 — Rest Parameters

Add this HTML:

```html
<h2>Rest Parameters</h2>
<div class="card" id="rest-demo"></div>
```

Add this JavaScript:

```javascript
// Collect all args
function sum(...numbers) {
  return numbers.reduce((total, n) => total + n, 0);
}

// Mix with regular params
function createTag(tagName, className, ...children) {
  return `<${tagName} class="${className}">${children.join('')}</${tagName}>`;
}

// Rest in destructuring
const [first, second, ...rest] = [10, 20, 30, 40, 50];
const { name, age, ...profile } = { name: 'Alex', age: 25, city: 'Lagos', role: 'admin' };

document.getElementById('rest-demo').innerHTML = `
  <div class="result">
    sum(1,2,3,4,5): <span class="good">${sum(1,2,3,4,5)}</span><br>
    sum(10,20,30): <span class="good">${sum(10,20,30)}</span><br>
    sum(): <span class="good">${sum()}</span><br>
    <br>
    createTag('div','card','&lt;h2&gt;Title&lt;/h2&gt;','&lt;p&gt;Body&lt;/p&gt;'):<br>
    <span class="good">${createTag('div','card','&lt;h2&gt;Title&lt;/h2&gt;','&lt;p&gt;Body&lt;/p&gt;')}</span><br>
    <br>
    [first, second, ...rest] = [10,20,30,40,50]:<br>
    first=<span class="good">${first}</span>, second=<span class="good">${second}</span>, rest=<span class="good">[${rest}]</span><br>
    <br>
    { name, age, ...profile } = user:<br>
    name=<span class="good">${name}</span>, age=<span class="good">${age}</span>, profile=<span class="good">${JSON.stringify(profile)}</span>
  </div>
`;
```

---

## Step 5 — Shallow Copy Warning

Add this HTML:

```html
<h2>Shallow Copy Warning</h2>
<div class="card" id="shallow-demo"></div>
```

Add this JavaScript:

```javascript
const original = { name: 'Alex', address: { city: 'Lagos' } };
const shallowCopy = { ...original };

// Modifying a primitive property — safe
shallowCopy.name = 'Sam';

// Modifying a nested object — AFFECTS ORIGINAL!
shallowCopy.address.city = 'Abuja';

document.getElementById('shallow-demo').innerHTML = `
  <div class="result">
    After shallowCopy.name = 'Sam':<br>
    original.name: <span class="good">${original.name}</span> (unchanged ✅)<br>
    shallowCopy.name: <span class="good">${shallowCopy.name}</span><br>
    <br>
    After shallowCopy.address.city = 'Abuja':<br>
    original.address.city: <span class="warn">${original.address.city}</span> (CHANGED ❌ — shared reference!)<br>
    shallowCopy.address.city: <span class="good">${shallowCopy.address.city}</span><br>
    <br>
    Fix: use structuredClone() for deep copy<br>
    const deepCopy = structuredClone(original);
  </div>
`;
```

---

## Checklist

- [ ] Array spread merges arrays correctly
- [ ] Array spread copy is independent (push doesn't affect original)
- [ ] `new Set` with spread removes duplicates
- [ ] Object spread merges with later properties winning
- [ ] Object spread copy is independent for primitive properties
- [ ] Rest parameters collect all extra arguments
- [ ] Rest in destructuring collects remaining elements/properties
- [ ] Shallow copy warning is demonstrated — nested object IS shared

---

## Bonus Challenges

1. Write a `deepMerge(obj1, obj2)` function that recursively merges nested objects
2. Use spread to implement `zip([1,2,3], ['a','b','c'])` → `[[1,'a'],[2,'b'],[3,'c']]`
3. Write a `pipe(...fns)` function using rest that applies functions left to right
