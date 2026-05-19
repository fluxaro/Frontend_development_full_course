# Class Work — Objects in Practice

## What You Will Build

A user profile builder that demonstrates creating, accessing, modifying, and iterating over objects.

**Time:** 30 minutes  
**Output:** `objects-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Objects Practice</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; }
    .profile-card { display: flex; gap: 1.5rem; align-items: flex-start; }
    .avatar { width: 80px; height: 80px; border-radius: 50%; background: linear-gradient(135deg, #3498db, #9b59b6); display: flex; align-items: center; justify-content: center; color: white; font-size: 1.5rem; font-weight: bold; flex-shrink: 0; }
    .profile-info h3 { margin-bottom: 0.25rem; }
    .profile-info p { color: #666; font-size: 0.9rem; margin-bottom: 0.25rem; }
    table { border-collapse: collapse; width: 100%; }
    th, td { padding: 0.5rem 0.75rem; text-align: left; border-bottom: 1px solid #dee2e6; font-size: 0.88rem; }
    th { background: #f0f0f0; font-weight: 600; }
    .form-row { display: flex; gap: 0.75rem; align-items: center; margin-bottom: 0.75rem; flex-wrap: wrap; }
    input, select { padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; }
    input:focus, select:focus { border-color: #3498db; }
    button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; }
    button:hover { background: #2980b9; }
    .result { font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
  </style>
</head>
<body>
  <h1>Objects Practice</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Create and Display a User Object

Add this HTML before `<script>`:

```html
<h2>User Profile Object</h2>
<div class="card" id="profile-display"></div>
```

Add this JavaScript:

```javascript
// Create a user object
const user = {
  firstName: 'Alex',
  lastName: 'Rivera',
  age: 25,
  email: 'alex@example.com',
  role: 'Frontend Developer',
  location: {
    city: 'Lagos',
    country: 'Nigeria',
  },
  skills: ['HTML', 'CSS', 'JavaScript', 'React'],
  isActive: true,
};

// Access properties
const fullName = `${user.firstName} ${user.lastName}`;
const initials = `${user.firstName[0]}${user.lastName[0]}`;
const city = user.location.city; // nested access
const topSkill = user.skills[0]; // array inside object

document.getElementById('profile-display').innerHTML = `
  <div class="profile-card">
    <div class="avatar">${initials}</div>
    <div class="profile-info">
      <h3>${fullName}</h3>
      <p>${user.role}</p>
      <p>📍 ${city}, ${user.location.country}</p>
      <p>✉️ ${user.email}</p>
      <p>Skills: ${user.skills.join(', ')}</p>
      <p>Status: ${user.isActive ? '🟢 Active' : '🔴 Inactive'}</p>
    </div>
  </div>
`;
```

---

## Step 3 — Inspect Object with Object.entries()

Add this HTML:

```html
<h2>Object Inspector (Object.entries)</h2>
<table>
  <thead><tr><th>Property</th><th>Value</th><th>Type</th></tr></thead>
  <tbody id="inspector-body"></tbody>
</table>
```

Add this JavaScript:

```javascript
const tbody = document.getElementById('inspector-body');

for (const [key, value] of Object.entries(user)) {
  const displayValue = Array.isArray(value)
    ? `[${value.join(', ')}]`
    : typeof value === 'object' && value !== null
    ? JSON.stringify(value)
    : String(value);

  tbody.innerHTML += `
    <tr>
      <td><strong>${key}</strong></td>
      <td>${displayValue}</td>
      <td><code>${Array.isArray(value) ? 'array' : typeof value}</code></td>
    </tr>
  `;
}
```

---

## Step 4 — Modify Object Properties

Add this HTML:

```html
<h2>Modify User Properties</h2>
<div class="form-row">
  <select id="prop-key">
    <option value="age">age</option>
    <option value="role">role</option>
    <option value="email">email</option>
  </select>
  <input type="text" id="prop-value" placeholder="New value">
  <button onclick="updateProp()">Update</button>
</div>
<div class="card result" id="update-result"></div>
```

Add this JavaScript:

```javascript
function updateProp() {
  const key = document.getElementById('prop-key').value;
  const value = document.getElementById('prop-value').value;

  const oldValue = user[key];
  user[key] = isNaN(value) ? value : Number(value); // convert to number if numeric

  document.getElementById('update-result').textContent =
    `Updated user.${key}: "${oldValue}" → "${user[key]}"`;
}
```

---

## Step 5 — Reference vs Copy

Add this JavaScript:

```javascript
console.log('--- Reference vs Copy ---');

const original = { name: 'Alex', score: 100 };

// Reference — same object
const ref = original;
ref.score = 999;
console.log('original.score after ref.score = 999:', original.score); // 999 — changed!

// Shallow copy — different object
const copy = { ...original };
copy.score = 50;
console.log('original.score after copy.score = 50:', original.score); // 999 — unchanged

console.log('original === ref:', original === ref);   // true (same object)
console.log('original === copy:', original === copy); // false (different object)
```

---

## Checklist

- [ ] User object is created with nested objects and arrays
- [ ] Dot notation accesses simple properties
- [ ] Bracket notation accesses nested properties
- [ ] `Object.entries()` iterates all key-value pairs
- [ ] Modifying a property via bracket notation works
- [ ] Reference vs copy is demonstrated — modifying a reference changes the original

---

## Bonus Challenges

1. Add a `getFullAddress()` method to the user object that returns a formatted address string
2. Use `Object.keys()` to count how many properties the user object has
3. Use `Object.freeze()` on a copy of the user and try to modify it — observe what happens
