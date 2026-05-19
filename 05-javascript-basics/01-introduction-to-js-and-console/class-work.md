# Class Work — Your First JavaScript

## What You Will Build

A simple HTML page with JavaScript that outputs information to the browser console. You will practice every console method and write your first JavaScript expressions.

**Time:** 25 minutes  
**Output:** `first-js.html`

---

## Step 1 — Create the HTML File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First JavaScript</title>
</head>
<body>
  <h1>My First JavaScript</h1>
  <p>Open the browser console (Cmd+Option+J / Ctrl+Shift+J) to see the output.</p>

  <script src="first-js.js" defer></script>
</body>
</html>
```

---

## Step 2 — Create first-js.js

Create `first-js.js` in the same folder:

```javascript
// ── Step 2a: Basic console.log ──
console.log('Hello, JavaScript!');
console.log('My name is Alex Rivera');
console.log('I am learning JavaScript');
```

Open the file in your browser. Open DevTools (Cmd+Option+J). You should see the three messages.

---

## Step 3 — Add More Console Methods

```javascript
// ── Step 3: Different console methods ──
console.error('This is what an error looks like');
console.warn('This is what a warning looks like');

// Multiple values in one log
console.log('Name:', 'Alex', '| Age:', 25, '| Learning:', true);
```

---

## Step 4 — Math and Comparisons

```javascript
// ── Step 4: Math ──
console.log('--- Math ---');
console.log(10 + 5);    // 15
console.log(10 - 3);    // 7
console.log(4 * 6);     // 24
console.log(15 / 4);    // 3.75
console.log(15 % 4);    // 3 (remainder)
console.log(2 ** 10);   // 1024 (power)

// Comparisons
console.log('--- Comparisons ---');
console.log(10 > 5);    // true
console.log(10 < 5);    // false
console.log(10 === 10); // true (strict equality)
console.log(10 === '10'); // false (different types!)
console.log(10 == '10');  // true (loose equality — avoid this)
```

---

## Step 5 — console.table

```javascript
// ── Step 5: Table ──
const courses = [
  { name: 'HTML Basics', weeks: 2, done: true },
  { name: 'CSS Basics', weeks: 3, done: true },
  { name: 'JavaScript', weeks: 6, done: false },
];

console.table(courses);
```

---

## Step 6 — Groups and Timer

```javascript
// ── Step 6: Groups ──
console.group('Personal Info');
console.log('Name: Alex Rivera');
console.log('Role: Frontend Developer');
console.log('Location: Lagos');
console.groupEnd();

// ── Timer ──
console.time('loop timer');
let sum = 0;
for (let i = 0; i < 1000000; i++) {
  sum += i;
}
console.timeEnd('loop timer');
console.log('Sum:', sum);
```

---

## Checklist

- [ ] File opens in browser without errors
- [ ] Console shows `console.log` messages
- [ ] `console.error` shows in red
- [ ] `console.warn` shows in yellow
- [ ] `console.table` shows a formatted table
- [ ] `console.group` creates a collapsible group
- [ ] `console.time` / `console.timeEnd` shows a time measurement
- [ ] Math results are correct
- [ ] `10 === '10'` returns `false` (strict equality)

---

## Bonus Challenges

1. Use `console.log` with CSS styling: `console.log('%cStyled!', 'color: blue; font-size: 20px')`
2. Log `typeof 42`, `typeof 'hello'`, `typeof true`, `typeof null` — what do you notice about `null`?
3. Try `console.dir(document.body)` — what does it show?
