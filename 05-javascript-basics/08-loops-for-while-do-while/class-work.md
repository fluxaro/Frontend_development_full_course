# Class Work — FizzBuzz, Countdown, and Dice

## What You Will Build

A page that demonstrates all three loop types through practical examples: FizzBuzz with a `for` loop, a power-of-2 finder with `while`, and a dice roller with `do-while`.

**Time:** 35 minutes  
**Output:** `loops-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Loops Practice</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .form-row { display: flex; gap: 0.75rem; align-items: center; margin-bottom: 1rem; flex-wrap: wrap; }
    input[type="number"] { padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; width: 100px; outline: none; }
    input:focus { border-color: #3498db; }
    button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; }
    button:hover { background: #2980b9; }
    .output { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1rem; margin-top: 0.5rem; font-family: monospace; font-size: 0.85rem; line-height: 1.8; min-height: 60px; }
    .fizz-grid { display: flex; flex-wrap: wrap; gap: 0.4rem; }
    .pill { padding: 0.25rem 0.6rem; border-radius: 999px; font-size: 0.8rem; font-weight: bold; }
    .pill-fizzbuzz { background: #e8d5f5; color: #6c3483; }
    .pill-fizz { background: #d6eaf8; color: #1a5276; }
    .pill-buzz { background: #d5f5e3; color: #1e8449; }
    .pill-num { background: #f0f0f0; color: #555; }
  </style>
</head>
<body>
  <h1>Loops Practice</h1>
  <!-- sections go here -->
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — FizzBuzz (for loop)

Add this HTML inside `<body>` before `<script>`:

```html
<h2>FizzBuzz (for loop)</h2>
<div class="form-row">
  <input type="number" id="fizz-limit" value="30" min="1" max="100">
  <button onclick="runFizzBuzz()">Run FizzBuzz</button>
</div>
<div class="output">
  <div class="fizz-grid" id="fizz-output"></div>
</div>
```

Add this JavaScript:

```javascript
function runFizzBuzz() {
  const limit = Number(document.getElementById('fizz-limit').value);
  const output = document.getElementById('fizz-output');
  output.innerHTML = '';

  for (let i = 1; i <= limit; i++) {
    let text, cssClass;

    if (i % 15 === 0) {
      text = 'FizzBuzz';
      cssClass = 'pill-fizzbuzz';
    } else if (i % 3 === 0) {
      text = 'Fizz';
      cssClass = 'pill-fizz';
    } else if (i % 5 === 0) {
      text = 'Buzz';
      cssClass = 'pill-buzz';
    } else {
      text = i;
      cssClass = 'pill-num';
    }

    output.innerHTML += `<span class="pill ${cssClass}">${text}</span>`;
  }
}
```

**Test it:** Run with limit 30. Verify: 3→Fizz, 5→Buzz, 15→FizzBuzz.

---

## Step 3 — Power of 2 Finder (while loop)

```html
<h2>First Power of 2 Greater Than N (while loop)</h2>
<div class="form-row">
  <input type="number" id="power-input" value="1000" min="1">
  <button onclick="findPower()">Find Power</button>
</div>
<div class="output" id="power-output"></div>
```

```javascript
function findPower() {
  const target = Number(document.getElementById('power-input').value);
  const output = document.getElementById('power-output');

  let power = 1;
  let exponent = 0;

  while (power <= target) {
    power *= 2;
    exponent++;
  }

  output.textContent = `First power of 2 greater than ${target}: 2^${exponent} = ${power}`;
}
```

---

## Step 4 — Dice Roller (do-while)

```html
<h2>Roll Until 6 (do-while)</h2>
<button onclick="rollDice()">Roll Dice</button>
<div class="output" id="dice-output"></div>
```

```javascript
function rollDice() {
  const output = document.getElementById('dice-output');
  const faces = ['⚀','⚁','⚂','⚃','⚄','⚅'];
  let rolls = 0;
  let result;
  let log = '';

  do {
    result = Math.floor(Math.random() * 6) + 1;
    rolls++;
    log += `Roll ${rolls}: ${faces[result - 1]} (${result})\n`;
  } while (result !== 6);

  log += `\n🎉 Got 6 after ${rolls} roll${rolls > 1 ? 's' : ''}!`;
  output.textContent = log;
}
```

---

## Step 5 — break and continue

Add this to your JavaScript (logs to console):

```javascript
// break — find first number divisible by both 7 and 11
console.log('--- break ---');
for (let i = 1; i <= 1000; i++) {
  if (i % 7 === 0 && i % 11 === 0) {
    console.log(`First number divisible by 7 and 11: ${i}`);
    break; // stop searching
  }
}

// continue — sum only odd numbers 1–50
console.log('--- continue ---');
let sum = 0;
for (let i = 1; i <= 50; i++) {
  if (i % 2 === 0) continue; // skip even numbers
  sum += i;
}
console.log(`Sum of odd numbers 1–50: ${sum}`); // 625
```

---

## Checklist

- [ ] FizzBuzz shows correct labels for multiples of 3, 5, and 15
- [ ] FizzBuzz uses a `for` loop
- [ ] Power finder uses a `while` loop and terminates correctly
- [ ] Dice roller uses `do-while` and always rolls at least once
- [ ] `break` stops the loop when the target is found
- [ ] `continue` skips even numbers in the sum
- [ ] No infinite loops in any example

---

## Bonus Challenges

1. Add a "Nested Loop" section that prints a multiplication table (10×10 grid) using nested `for` loops
2. Modify the dice roller to count how many rolls it takes on average over 100 games
3. Add a "Countdown" that uses `setInterval` and a `while`-style condition to count from 10 to 0
