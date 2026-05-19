# Class Work — Grade Calculator and Switch Practice

## What You Will Build

A grade calculator using `if/else` and a day classifier using `switch`. You will also practice the ternary operator for simple conditions.

**Time:** 35 minutes  
**Output:** `control-flow-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Control Flow Practice</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; }
    .form-row { display: flex; gap: 0.75rem; align-items: center; margin-bottom: 1rem; }
    input { padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; }
    input:focus { border-color: #3498db; }
    button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; }
    button:hover { background: #2980b9; }
    .result { padding: 1rem 1.25rem; border-radius: 8px; font-weight: bold; margin-top: 0.5rem; display: none; }
  </style>
</head>
<body>
  <h1>Control Flow Practice</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Grade Calculator with if/else

Add this HTML inside `<body>` before the `<script>` tag:

```html
<h2>Grade Calculator</h2>
<div class="form-row">
  <input type="number" id="score-input" placeholder="Enter score (0–100)" min="0" max="100">
  <button onclick="calculateGrade()">Calculate Grade</button>
</div>
<div class="result" id="grade-result"></div>
```

Now add the JavaScript inside `<script>`:

```javascript
function calculateGrade() {
  const score = Number(document.getElementById('score-input').value);
  const resultEl = document.getElementById('grade-result');

  // Validate input
  if (isNaN(score) || score < 0 || score > 100) {
    resultEl.style.display = 'block';
    resultEl.style.background = '#f8d7da';
    resultEl.style.color = '#721c24';
    resultEl.textContent = 'Please enter a valid score between 0 and 100.';
    return;
  }

  // Determine grade
  let grade, message, bgColor, textColor;

  if (score >= 90) {
    grade = 'A';
    message = 'Excellent! Outstanding work.';
    bgColor = '#d4edda';
    textColor = '#155724';
  } else if (score >= 80) {
    grade = 'B';
    message = 'Good job! Above average.';
    bgColor = '#cce5ff';
    textColor = '#004085';
  } else if (score >= 70) {
    grade = 'C';
    message = 'Satisfactory. Room for improvement.';
    bgColor = '#fff3cd';
    textColor = '#856404';
  } else if (score >= 60) {
    grade = 'D';
    message = 'Needs improvement. Study harder.';
    bgColor = '#ffe5d0';
    textColor = '#7d3c00';
  } else {
    grade = 'F';
    message = 'Failed. Please retake the exam.';
    bgColor = '#f8d7da';
    textColor = '#721c24';
  }

  resultEl.style.display = 'block';
  resultEl.style.background = bgColor;
  resultEl.style.color = textColor;
  resultEl.textContent = `Grade: ${grade} — ${message} (Score: ${score})`;
}
```

**Test it:** Try scores 95, 85, 72, 65, 45, and -5.

---

## Step 3 — Day Classifier with switch

Add this HTML after the grade section:

```html
<h2>Day Classifier</h2>
<div class="form-row">
  <input type="text" id="day-input" placeholder="Enter a day name">
  <button onclick="classifyDay()">Classify</button>
</div>
<div class="result" id="day-result"></div>
```

Add this JavaScript:

```javascript
function classifyDay() {
  const day = document.getElementById('day-input').value.trim();
  const resultEl = document.getElementById('day-result');

  if (!day) {
    resultEl.style.display = 'block';
    resultEl.style.background = '#f8d7da';
    resultEl.style.color = '#721c24';
    resultEl.textContent = 'Please enter a day name.';
    return;
  }

  let type, emoji, bgColor;

  switch (day.toLowerCase()) {
    case 'monday':
    case 'tuesday':
    case 'wednesday':
    case 'thursday':
    case 'friday':
      type = 'Weekday';
      emoji = '📅';
      bgColor = '#cce5ff';
      break;
    case 'saturday':
    case 'sunday':
      type = 'Weekend';
      emoji = '🎉';
      bgColor = '#d4edda';
      break;
    default:
      type = 'Invalid day';
      emoji = '❓';
      bgColor = '#f8d7da';
  }

  resultEl.style.display = 'block';
  resultEl.style.background = bgColor;
  resultEl.style.color = '#333';
  resultEl.textContent = `${emoji} "${day}" is a ${type}`;
}
```

**Test it:** Try "Monday", "saturday", "SUNDAY", "Holiday".

---

## Step 4 — Ternary Operator Practice

Add this to your JavaScript:

```javascript
// Ternary examples — log to console
const age = 20;
const status = age >= 18 ? 'Adult' : 'Minor';
console.log(`Age ${age}: ${status}`);

const score = 75;
const passed = score >= 60 ? 'Passed ✅' : 'Failed ❌';
console.log(`Score ${score}: ${passed}`);

// Nested ternary (use sparingly)
const grade = score >= 90 ? 'A' : score >= 80 ? 'B' : score >= 70 ? 'C' : 'F';
console.log(`Grade: ${grade}`);

// Ternary in JSX-style template literals
const items = 3;
console.log(`You have ${items} item${items !== 1 ? 's' : ''} in your cart.`);
```

Open the console to see the output.

---

## Checklist

- [ ] Grade calculator shows correct grade for scores 95, 85, 72, 65, 45
- [ ] Grade calculator shows error for invalid input (-5, 150, empty)
- [ ] Day classifier correctly identifies weekdays and weekends
- [ ] Day classifier is case-insensitive ("MONDAY" and "monday" both work)
- [ ] Day classifier shows "Invalid day" for unknown input
- [ ] Ternary examples log correctly to the console
- [ ] `break` is present in every switch case

---

## Bonus Challenges

1. Add a "Season Finder" — input a month number (1–12), output the season using `switch`
2. Add a "Number Sign" checker — input a number, output "Positive", "Negative", or "Zero" using a ternary
3. Add a "Ticket Price" calculator — input an age, output the ticket price: under 5 = free, 5–17 = $8, 18–64 = $15, 65+ = $10
