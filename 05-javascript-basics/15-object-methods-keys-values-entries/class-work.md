# Class Work — Object Methods in Practice

## What You Will Build

A page that demonstrates `Object.keys()`, `Object.values()`, `Object.entries()`, and `Object.fromEntries()` through practical data transformation examples.

**Time:** 30 minutes  
**Output:** `object-methods-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Object Methods Practice</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; }
    .result { font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
    table { border-collapse: collapse; width: 100%; }
    th, td { padding: 0.5rem 0.75rem; text-align: left; border-bottom: 1px solid #dee2e6; font-size: 0.88rem; }
    th { background: #2c3e50; color: white; }
    .type-string { color: #3498db; font-weight: bold; }
    .type-number { color: #27ae60; font-weight: bold; }
    .type-boolean { color: #e67e22; font-weight: bold; }
    .bar-row { display: flex; align-items: center; gap: 1rem; margin-bottom: 0.5rem; }
    .bar-label { min-width: 100px; font-size: 0.85rem; }
    .bar-track { flex: 1; height: 18px; background: #f0f0f0; border-radius: 999px; overflow: hidden; }
    .bar-fill { height: 100%; border-radius: 999px; }
    .bar-val { min-width: 50px; text-align: right; font-size: 0.85rem; font-weight: bold; }
  </style>
</head>
<body>
  <h1>Object Methods Practice</h1>
  <script>
    const scores = {
      mathematics: 88,
      english: 92,
      science: 79,
      history: 85,
      geography: 91,
      art: 76,
    };

    const student = {
      name: 'Alex Rivera',
      age: 20,
      email: 'alex@example.com',
      grade: 'A',
      gpa: 3.8,
      enrolled: true,
      scholarship: false,
      city: 'Lagos',
    };
  </script>
</body>
</html>
```

---

## Step 2 — Object.keys() Demo

Add this HTML before `<script>`:

```html
<h2>Object.keys() — Property Names</h2>
<div class="card" id="keys-demo"></div>
```

Add this JavaScript:

```javascript
const subjectNames = Object.keys(scores);
const studentProps = Object.keys(student);

document.getElementById('keys-demo').innerHTML = `
  <div class="result">
    Object.keys(scores): [${subjectNames.join(', ')}]<br>
    Count: ${subjectNames.length} subjects<br>
    <br>
    Object.keys(student): [${studentProps.join(', ')}]<br>
    Count: ${studentProps.length} properties<br>
    <br>
    String properties: [${studentProps.filter(k => typeof student[k] === 'string').join(', ')}]<br>
    Boolean properties: [${studentProps.filter(k => typeof student[k] === 'boolean').join(', ')}]
  </div>
`;
```

---

## Step 3 — Object.values() Demo

Add this HTML:

```html
<h2>Object.values() — Property Values</h2>
<div class="card" id="values-demo"></div>
```

Add this JavaScript:

```javascript
const scoreValues = Object.values(scores);
const total = scoreValues.reduce((sum, s) => sum + s, 0);
const avg = (total / scoreValues.length).toFixed(1);
const highest = Math.max(...scoreValues);
const lowest = Math.min(...scoreValues);

document.getElementById('values-demo').innerHTML = `
  <div class="result">
    Object.values(scores): [${scoreValues.join(', ')}]<br>
    Total: ${total}<br>
    Average: ${avg}<br>
    Highest: ${highest}<br>
    Lowest: ${lowest}
  </div>
`;
```

---

## Step 4 — Object.entries() with Bar Chart

Add this HTML:

```html
<h2>Object.entries() — Score Bar Chart</h2>
<div class="card" id="entries-demo"></div>
```

Add this JavaScript:

```javascript
const maxScore = Math.max(...Object.values(scores));
const entriesEl = document.getElementById('entries-demo');

entriesEl.innerHTML = Object.entries(scores).map(([subject, score]) => {
  const pct = (score / maxScore * 100).toFixed(0);
  const color = score >= 90 ? '#27ae60' : score >= 80 ? '#3498db' : '#f39c12';
  return `
    <div class="bar-row">
      <span class="bar-label">${subject}</span>
      <div class="bar-track">
        <div class="bar-fill" style="width:${pct}%;background:${color}"></div>
      </div>
      <span class="bar-val" style="color:${color}">${score}</span>
    </div>
  `;
}).join('');
```

---

## Step 5 — Object.fromEntries() Transformations

Add this HTML:

```html
<h2>Object.fromEntries() — Transformations</h2>
<div class="card" id="transform-demo"></div>
```

Add this JavaScript:

```javascript
// Double all scores
const doubled = Object.fromEntries(
  Object.entries(scores).map(([k, v]) => [k, v * 2])
);

// Filter only high scores (>= 85)
const highScores = Object.fromEntries(
  Object.entries(scores).filter(([, v]) => v >= 85)
);

// Normalise to 0-1 range
const normalised = Object.fromEntries(
  Object.entries(scores).map(([k, v]) => [k, (v / 100).toFixed(2)])
);

document.getElementById('transform-demo').innerHTML = `
  <div class="result">
    <strong>Original:</strong> ${JSON.stringify(scores)}<br><br>
    <strong>Doubled:</strong> ${JSON.stringify(doubled)}<br><br>
    <strong>High scores (≥85):</strong> ${JSON.stringify(highScores)}<br><br>
    <strong>Normalised (0-1):</strong> ${JSON.stringify(normalised)}
  </div>
`;
```

---

## Step 6 — Student Object Inspector

Add this HTML:

```html
<h2>Student Object Inspector</h2>
<table>
  <thead><tr><th>Property</th><th>Value</th><th>Type</th></tr></thead>
  <tbody id="student-table"></tbody>
</table>
```

Add this JavaScript:

```javascript
const tbody = document.getElementById('student-table');
tbody.innerHTML = Object.entries(student).map(([key, value]) => {
  const type = typeof value;
  const typeClass = `type-${type}`;
  return `
    <tr>
      <td><strong>${key}</strong></td>
      <td>${String(value)}</td>
      <td><span class="${typeClass}">${type}</span></td>
    </tr>
  `;
}).join('');
```

---

## Checklist

- [ ] `Object.keys()` returns an array of property names
- [ ] `Object.values()` returns an array of values
- [ ] Statistics (total, avg, max, min) are calculated correctly
- [ ] `Object.entries()` bar chart shows proportional bars
- [ ] `Object.fromEntries()` correctly transforms the scores object
- [ ] Student inspector shows all properties with correct types

---

## Bonus Challenges

1. Use `Object.assign()` to merge two objects and show the result
2. Use `Object.freeze()` on the scores object and try to modify a score — observe what happens
3. Write a `pick(obj, keys)` function using `Object.fromEntries()` that returns only the specified keys
