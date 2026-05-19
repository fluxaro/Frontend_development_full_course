# Class Work — reduce, find, some, every

## What You Will Build

A page that demonstrates `reduce` for aggregation, `find` for searching, and `some`/`every` for validation — using a dataset of students.

**Time:** 35 minutes  
**Output:** `advanced-arrays-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Advanced Array Methods</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; }
    .result { font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
    .stat { display: flex; align-items: center; gap: 1rem; margin-bottom: 0.5rem; }
    .stat-label { min-width: 120px; font-size: 0.85rem; color: #555; }
    .bar-track { flex: 1; height: 20px; background: #f0f0f0; border-radius: 999px; overflow: hidden; }
    .bar-fill { height: 100%; background: #3498db; border-radius: 999px; transition: width 0.5s ease; }
    .stat-val { min-width: 60px; text-align: right; font-size: 0.85rem; font-weight: bold; }
    .form-row { display: flex; gap: 0.75rem; align-items: center; margin-bottom: 0.75rem; }
    input { padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; }
    input:focus { border-color: #3498db; }
    button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; }
    button:hover { background: #2980b9; }
    .check { color: #27ae60; font-weight: bold; }
    .cross { color: #e74c3c; font-weight: bold; }
  </style>
</head>
<body>
  <h1>Advanced Array Methods</h1>
  <script>
    const students = [
      { id: 1, name: 'Alex Rivera', grade: 92, subject: 'JavaScript', passed: true },
      { id: 2, name: 'Sam Okafor', grade: 78, subject: 'CSS', passed: true },
      { id: 3, name: 'Jordan Lee', grade: 85, subject: 'React', passed: true },
      { id: 4, name: 'Morgan Kim', grade: 55, subject: 'HTML', passed: false },
      { id: 5, name: 'Taylor Chen', grade: 95, subject: 'JavaScript', passed: true },
      { id: 6, name: 'Casey Brown', grade: 68, subject: 'CSS', passed: true },
      { id: 7, name: 'Riley Davis', grade: 42, subject: 'React', passed: false },
      { id: 8, name: 'Quinn Wilson', grade: 88, subject: 'HTML', passed: true },
    ];
  </script>
</body>
</html>
```

---

## Step 2 — reduce: Statistics

Add this HTML before `<script>`:

```html
<h2>Statistics with reduce</h2>
<div class="card" id="stats-output"></div>
```

Add this JavaScript:

```javascript
// Total grade points
const totalGrades = students.reduce((sum, s) => sum + s.grade, 0);
const avgGrade = (totalGrades / students.length).toFixed(1);

// Highest and lowest
const highest = students.reduce((best, s) => s.grade > best.grade ? s : best);
const lowest = students.reduce((worst, s) => s.grade < worst.grade ? s : worst);

// Count by subject
const bySubject = students.reduce((acc, s) => {
  acc[s.subject] = (acc[s.subject] || 0) + 1;
  return acc;
}, {});

// Average grade by subject
const gradeBySubject = students.reduce((acc, s) => {
  if (!acc[s.subject]) acc[s.subject] = { total: 0, count: 0 };
  acc[s.subject].total += s.grade;
  acc[s.subject].count++;
  return acc;
}, {});

const avgBySubject = Object.entries(gradeBySubject).map(([subject, data]) => ({
  subject,
  avg: (data.total / data.count).toFixed(1),
}));

document.getElementById('stats-output').innerHTML = `
  <div class="result">
    Total students: ${students.length}<br>
    Average grade: ${avgGrade}<br>
    Highest: ${highest.name} (${highest.grade})<br>
    Lowest: ${lowest.name} (${lowest.grade})<br>
    <br>
    <strong>Students per subject:</strong><br>
    ${Object.entries(bySubject).map(([s, c]) => `  ${s}: ${c}`).join('<br>')}<br>
    <br>
    <strong>Average grade by subject:</strong><br>
    ${avgBySubject.map(({subject, avg}) => `  ${subject}: ${avg}`).join('<br>')}
  </div>
`;
```

---

## Step 3 — find: Search by ID

Add this HTML:

```html
<h2>Find Student by ID</h2>
<div class="form-row">
  <input type="number" id="search-id" placeholder="Enter student ID (1-8)" min="1" max="8">
  <button onclick="searchStudent()">Find</button>
</div>
<div class="card" id="search-result" style="display:none"></div>
```

Add this JavaScript:

```javascript
function searchStudent() {
  const id = Number(document.getElementById('search-id').value);
  const resultEl = document.getElementById('search-result');

  const student = students.find(s => s.id === id);

  resultEl.style.display = 'block';

  if (!student) {
    resultEl.innerHTML = `<span style="color:#e74c3c">No student found with ID ${id}</span>`;
    return;
  }

  const gradeColor = student.grade >= 80 ? '#27ae60' : student.grade >= 60 ? '#f39c12' : '#e74c3c';

  resultEl.innerHTML = `
    <strong>${student.name}</strong><br>
    ID: ${student.id} | Subject: ${student.subject}<br>
    Grade: <span style="color:${gradeColor};font-weight:bold">${student.grade}</span><br>
    Status: ${student.passed ? '<span style="color:#27ae60">✅ Passed</span>' : '<span style="color:#e74c3c">❌ Failed</span>'}
  `;
}
```

---

## Step 4 — some and every: Validation

Add this HTML:

```html
<h2>Validation with some and every</h2>
<div class="card" id="validation-output"></div>
```

Add this JavaScript:

```javascript
const checks = [
  {
    question: 'Does any student have a grade above 90?',
    result: students.some(s => s.grade > 90),
    detail: `${students.filter(s => s.grade > 90).map(s => s.name).join(', ')}`,
  },
  {
    question: 'Did every student pass?',
    result: students.every(s => s.passed),
    detail: `${students.filter(s => !s.passed).map(s => s.name).join(', ')} failed`,
  },
  {
    question: 'Does any student have a grade below 50?',
    result: students.some(s => s.grade < 50),
    detail: `${students.filter(s => s.grade < 50).map(s => s.name).join(', ')}`,
  },
  {
    question: 'Does every student have a name?',
    result: students.every(s => s.name && s.name.trim() !== ''),
    detail: 'All students have names',
  },
];

document.getElementById('validation-output').innerHTML = checks.map(c => `
  <div style="margin-bottom:0.75rem">
    <span class="${c.result ? 'check' : 'cross'}">${c.result ? '✅' : '❌'}</span>
    <strong>${c.question}</strong><br>
    <span style="font-size:0.85rem;color:#666;margin-left:1.5rem">${c.detail}</span>
  </div>
`).join('');
```

---

## Checklist

- [ ] `reduce` correctly calculates total, average, highest, lowest
- [ ] `reduce` correctly groups students by subject
- [ ] `find` returns the correct student for valid IDs
- [ ] `find` returns `undefined` for invalid IDs (handled gracefully)
- [ ] `some` returns `true` when at least one student matches
- [ ] `every` returns `false` because not all students passed
- [ ] All results are accurate

---

## Bonus Challenges

1. Use `reduce` to build a grade distribution: `{ A: 2, B: 3, C: 1, D: 1, F: 1 }`
2. Use `findIndex` to locate a student, then use `splice` to remove them
3. Chain `filter`, `map`, and `reduce` to get the average grade of only passing students
