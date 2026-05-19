# Class Work — Destructuring in Practice

## What You Will Build

A page that demonstrates object and array destructuring through practical examples including variable swapping, function parameters, and nested data extraction.

**Time:** 30 minutes  
**Output:** `destructuring-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Destructuring Practice</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; }
    pre { background: #1e293b; color: #e2e8f0; padding: 0.75rem; border-radius: 6px; font-size: 0.82rem; overflow-x: auto; line-height: 1.6; }
    .result { font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
    .good { color: #27ae60; font-weight: bold; }
    .blue { color: #3498db; font-weight: bold; }
    .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  </style>
</head>
<body>
  <h1>Destructuring Practice</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Object Destructuring

Add this HTML before `<script>`:

```html
<h2>Object Destructuring</h2>
<div class="grid">
  <div class="card">
    <h3 style="font-size:0.9rem;margin-bottom:0.75rem">Basic</h3>
    <div class="result" id="obj-basic"></div>
  </div>
  <div class="card">
    <h3 style="font-size:0.9rem;margin-bottom:0.75rem">Rename + Defaults</h3>
    <div class="result" id="obj-rename"></div>
  </div>
  <div class="card">
    <h3 style="font-size:0.9rem;margin-bottom:0.75rem">Nested</h3>
    <div class="result" id="obj-nested"></div>
  </div>
  <div class="card">
    <h3 style="font-size:0.9rem;margin-bottom:0.75rem">Rest</h3>
    <div class="result" id="obj-rest"></div>
  </div>
</div>
```

Add this JavaScript:

```javascript
const user = {
  name: 'Alex Rivera',
  age: 25,
  email: 'alex@example.com',
  role: 'admin',
  address: { city: 'Lagos', country: 'Nigeria' },
};

// Basic
const { name, age, email } = user;
document.getElementById('obj-basic').innerHTML =
  `name: <span class="good">${name}</span><br>age: <span class="good">${age}</span><br>email: <span class="good">${email}</span>`;

// Rename + defaults
const { name: fullName, role: userRole = 'user', phone = 'Not provided' } = user;
document.getElementById('obj-rename').innerHTML =
  `fullName: <span class="good">${fullName}</span><br>userRole: <span class="good">${userRole}</span><br>phone: <span class="blue">${phone}</span> (default)`;

// Nested
const { address: { city, country } } = user;
document.getElementById('obj-nested').innerHTML =
  `city: <span class="good">${city}</span><br>country: <span class="good">${country}</span>`;

// Rest
const { name: n, ...rest } = user;
document.getElementById('obj-rest').innerHTML =
  `name: <span class="good">${n}</span><br>rest: <span class="blue">${JSON.stringify(rest)}</span>`;
```

---

## Step 3 — Array Destructuring

Add this HTML:

```html
<h2>Array Destructuring</h2>
<div class="grid">
  <div class="card">
    <h3 style="font-size:0.9rem;margin-bottom:0.75rem">Basic + Skip</h3>
    <div class="result" id="arr-basic"></div>
  </div>
  <div class="card">
    <h3 style="font-size:0.9rem;margin-bottom:0.75rem">Rest + Defaults</h3>
    <div class="result" id="arr-rest"></div>
  </div>
</div>
```

Add this JavaScript:

```javascript
const coords = [40.7128, -74.0060, 10]; // lat, lng, altitude
const [lat, lng, altitude = 0] = coords;

const rgb = [255, 128, 0];
const [red, , blue] = rgb; // skip green

document.getElementById('arr-basic').innerHTML =
  `lat: <span class="good">${lat}</span><br>lng: <span class="good">${lng}</span><br>altitude: <span class="good">${altitude}</span><br>red: <span class="good">${red}</span>, blue: <span class="good">${blue}</span> (skipped green)`;

const [first, second, ...remaining] = [1, 2, 3, 4, 5];
const [a = 10, b = 20, c = 30] = [1, 2]; // c uses default

document.getElementById('arr-rest').innerHTML =
  `first: <span class="good">${first}</span><br>second: <span class="good">${second}</span><br>remaining: <span class="good">[${remaining}]</span><br>a=${a}, b=${b}, c=<span class="blue">${c}</span> (default)`;
```

---

## Step 4 — Variable Swap

Add this HTML:

```html
<h2>Variable Swap with Destructuring</h2>
<div class="card" id="swap-demo"></div>
```

Add this JavaScript:

```javascript
let playerA = 'Alex (Score: 100)';
let playerB = 'Sam (Score: 85)';

const before = `Before: playerA = "${playerA}", playerB = "${playerB}"`;

// Swap without a temp variable!
[playerA, playerB] = [playerB, playerA];

const after = `After:  playerA = "${playerA}", playerB = "${playerB}"`;

document.getElementById('swap-demo').innerHTML = `
  <div class="result">
    ${before}<br>
    <span class="good">${after}</span>
  </div>
`;
```

---

## Step 5 — Destructuring in Function Parameters

Add this HTML:

```html
<h2>Destructuring in Function Parameters</h2>
<div class="card" id="params-demo"></div>
```

Add this JavaScript:

```javascript
// Without destructuring — verbose
function displayUserOld(user) {
  return `${user.name} (${user.age}) from ${user.address.city}`;
}

// With destructuring — clean
function displayUser({ name, age, address: { city } = {}, role = 'user' }) {
  return `${name} (${age}) from ${city || 'Unknown'} — ${role}`;
}

// Array parameter destructuring
function getDistance([x1, y1], [x2, y2]) {
  return Math.sqrt((x2 - x1) ** 2 + (y2 - y1) ** 2).toFixed(2);
}

const users = [
  { name: 'Alex', age: 25, address: { city: 'Lagos' }, role: 'admin' },
  { name: 'Sam', age: 30, address: { city: 'Abuja' } },
  { name: 'Jordan', age: 22 }, // no address
];

document.getElementById('params-demo').innerHTML = `
  <div class="result">
    ${users.map(u => displayUser(u)).join('<br>')}
    <br>
    Distance from [0,0] to [3,4]: <span class="good">${getDistance([0,0], [3,4])}</span>
  </div>
`;
```

---

## Checklist

- [ ] Basic object destructuring extracts `name`, `age`, `email`
- [ ] Rename destructuring creates `fullName` from `name`
- [ ] Default values work for missing properties (`phone`, `c`)
- [ ] Nested destructuring extracts `city` and `country`
- [ ] Rest destructuring collects remaining properties
- [ ] Array destructuring skips elements with commas
- [ ] Variable swap works without a temp variable
- [ ] Function parameter destructuring cleans up the function body

---

## Bonus Challenges

1. Destructure a deeply nested API response (3+ levels deep)
2. Use destructuring in a `for-of` loop over an array of objects
3. Write a function that accepts an options object with 5 properties, all with defaults
