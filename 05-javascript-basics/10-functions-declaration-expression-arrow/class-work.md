# Class Work — Functions in Three Styles

## What You Will Build

A page that demonstrates function declarations, expressions, and arrow functions side by side, with an interactive calculator that uses all three styles.

**Time:** 35 minutes  
**Output:** `functions-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Functions Practice</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; }
    .card h3 { font-size: 0.9rem; color: #3498db; font-family: monospace; margin-bottom: 0.75rem; }
    pre { background: #1e293b; color: #e2e8f0; padding: 0.75rem; border-radius: 6px; font-size: 0.8rem; overflow-x: auto; line-height: 1.6; }
    .result { background: #d4edda; color: #155724; padding: 0.5rem 0.75rem; border-radius: 4px; font-family: monospace; font-size: 0.85rem; margin-top: 0.5rem; }
    .form-row { display: flex; gap: 0.75rem; align-items: center; margin-bottom: 0.75rem; flex-wrap: wrap; }
    input { padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; }
    input:focus { border-color: #3498db; }
    button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; }
    button:hover { background: #2980b9; }
    .output { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1rem; margin-top: 0.5rem; font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
  </style>
</head>
<body>
  <h1>Functions: Declaration, Expression, Arrow</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Three Ways to Write the Same Function

Add this HTML before `<script>`:

```html
<h2>Three Ways to Write the Same Function</h2>
<div class="grid" id="three-ways"></div>
```

Add this JavaScript:

```javascript
// 1. Function Declaration
function addDeclaration(a, b) {
  return a + b;
}

// 2. Function Expression
const addExpression = function(a, b) {
  return a + b;
};

// 3. Arrow Function
const addArrow = (a, b) => a + b;

// All produce the same result
const a = 7, b = 3;
document.getElementById('three-ways').innerHTML = `
  <div class="card">
    <h3>Function Declaration</h3>
    <pre>function add(a, b) {
  return a + b;
}</pre>
    <div class="result">add(${a}, ${b}) = ${addDeclaration(a, b)}</div>
    <p style="font-size:0.8rem;color:#666;margin-top:0.5rem">✅ Hoisted — can call before definition</p>
  </div>
  <div class="card">
    <h3>Function Expression</h3>
    <pre>const add = function(a, b) {
  return a + b;
};</pre>
    <div class="result">add(${a}, ${b}) = ${addExpression(a, b)}</div>
    <p style="font-size:0.8rem;color:#666;margin-top:0.5rem">❌ Not hoisted — define before use</p>
  </div>
  <div class="card">
    <h3>Arrow Function</h3>
    <pre>const add = (a, b) => a + b;</pre>
    <div class="result">add(${a}, ${b}) = ${addArrow(a, b)}</div>
    <p style="font-size:0.8rem;color:#666;margin-top:0.5rem">❌ No own <code>this</code> — use for callbacks</p>
  </div>
`;
```

---

## Step 3 — Arrow Function Variations

Add this HTML:

```html
<h2>Arrow Function Syntax Variations</h2>
<div class="grid" id="arrow-variations"></div>
```

Add this JavaScript:

```javascript
// No parameters
const getRandom = () => Math.random().toFixed(4);

// Single parameter (no parens needed)
const double = n => n * 2;

// Multiple parameters
const multiply = (a, b) => a * b;

// Multi-line (needs return)
const gradeMessage = score => {
  if (score >= 90) return 'Excellent!';
  if (score >= 70) return 'Good job!';
  return 'Keep practising!';
};

// Returning an object (wrap in parens!)
const createUser = (name, age) => ({ name, age, createdAt: new Date().toISOString() });

document.getElementById('arrow-variations').innerHTML = `
  <div class="card">
    <h3>() => value (no params)</h3>
    <pre>const getRandom = () => Math.random();</pre>
    <div class="result">getRandom() = ${getRandom()}</div>
  </div>
  <div class="card">
    <h3>n => value (single param)</h3>
    <pre>const double = n => n * 2;</pre>
    <div class="result">double(7) = ${double(7)}</div>
  </div>
  <div class="card">
    <h3>Multi-line arrow</h3>
    <pre>const grade = score => {
  if (score >= 90) return 'Excellent!';
  return 'Keep practising!';
};</pre>
    <div class="result">gradeMessage(85) = "${gradeMessage(85)}"</div>
  </div>
  <div class="card">
    <h3>Returning an object</h3>
    <pre>const user = (name, age) => ({ name, age });</pre>
    <div class="result">createUser('Alex', 25) = ${JSON.stringify(createUser('Alex', 25))}</div>
  </div>
`;
```

---

## Step 4 — Interactive Calculator

Add this HTML:

```html
<h2>Interactive Calculator</h2>
<div class="form-row">
  <input type="number" id="num1" placeholder="First number" value="10">
  <input type="number" id="num2" placeholder="Second number" value="3">
  <button onclick="calculate()">Calculate</button>
</div>
<div class="output" id="calc-output"></div>
```

Add this JavaScript:

```javascript
// Define operations as arrow functions
const operations = {
  add:      (a, b) => a + b,
  subtract: (a, b) => a - b,
  multiply: (a, b) => a * b,
  divide:   (a, b) => b !== 0 ? (a / b).toFixed(4) : 'Cannot divide by zero',
  modulo:   (a, b) => a % b,
  power:    (a, b) => Math.pow(a, b),
};

function calculate() {
  const a = Number(document.getElementById('num1').value);
  const b = Number(document.getElementById('num2').value);
  const output = document.getElementById('calc-output');

  let html = '';
  for (const [name, fn] of Object.entries(operations)) {
    html += `${a} ${name} ${b} = <strong>${fn(a, b)}</strong>\n`;
  }
  output.textContent = html;
}
```

---

## Checklist

- [ ] All three function styles produce the same result for `add(7, 3)`
- [ ] Arrow function variations all work correctly
- [ ] Returning an object with `=> ({ })` works (not `=> { }`)
- [ ] Calculator uses arrow functions stored in an object
- [ ] Division by zero is handled gracefully

---

## Bonus Challenges

1. Add a `compose(f, g)` function that returns a new function applying `g` then `f`
2. Write a `memoize(fn)` function that caches results of expensive function calls
3. Rewrite the calculator operations as a function declaration, expression, and arrow — compare the syntax
