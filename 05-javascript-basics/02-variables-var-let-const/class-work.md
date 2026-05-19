# Class Work — Variables in Practice

## What You Will Build

A JavaScript file that explores `var`, `let`, and `const` through hands-on examples. You will see scope differences, hoisting, and const mutation in action.

**Time:** 30 minutes  
**Output:** `variables-practice.html`

---

## Step 1 — Setup

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Variables Practice</title>
</head>
<body>
  <h1>Variables: var, let, const</h1>
  <p>Open the console to see the output.</p>
  <script>
    // code goes here
  </script>
</body>
</html>
```

---

## Step 2 — var vs let Scope

```javascript
// ── var: function-scoped (leaks out of blocks) ──
console.log('--- var scope ---');
if (true) {
  var leaky = 'I leak out of the block';
}
console.log(leaky); // 'I leak out of the block' — var leaks!

// ── let: block-scoped ──
console.log('--- let scope ---');
if (true) {
  let contained = 'I stay inside the block';
  console.log(contained); // works inside
}
try {
  console.log(contained); // ReferenceError outside
} catch (e) {
  console.log('Error:', e.message); // contained is not defined
}
```

---

## Step 3 — const Basics

```javascript
// ── const: cannot be reassigned ──
console.log('--- const ---');
const MAX_SCORE = 100;
console.log('Max score:', MAX_SCORE);

try {
  MAX_SCORE = 200; // TypeError
} catch (e) {
  console.log('Error:', e.message); // Assignment to constant variable
}

// ── const with objects: mutation is allowed ──
const player = {
  name: 'Alex',
  score: 0,
  level: 1,
};

console.log('Before:', player);
player.score = 50;  // ✅ mutation OK
player.level = 2;   // ✅ mutation OK
console.log('After mutation:', player);

try {
  player = { name: 'Sam' }; // ❌ reassignment not OK
} catch (e) {
  console.log('Cannot reassign const:', e.message);
}
```

---

## Step 4 — Hoisting

```javascript
// ── var hoisting ──
console.log('--- hoisting ---');
console.log('var before declaration:', hoistedVar); // undefined (not an error)
var hoistedVar = 'I was hoisted';
console.log('var after declaration:', hoistedVar);

// ── let is NOT hoisted (Temporal Dead Zone) ──
try {
  console.log(notHoisted); // ReferenceError
  let notHoisted = 'I am not hoisted';
} catch (e) {
  console.log('let TDZ error:', e.message);
}
```

---

## Step 5 — Real-World Example

```javascript
// ── Build a shopping cart ──
console.log('--- Shopping Cart ---');

const DISCOUNT_RATE = 0.1; // 10% — never changes
const TAX_RATE = 0.075;    // 7.5% — never changes

let cartTotal = 0;         // changes as items are added
let itemCount = 0;         // changes as items are added

// Add items
cartTotal += 29.99;
itemCount++;
cartTotal += 14.99;
itemCount++;
cartTotal += 49.99;
itemCount++;

const discount = cartTotal * DISCOUNT_RATE;
const tax = (cartTotal - discount) * TAX_RATE;
const finalTotal = cartTotal - discount + tax;

console.log(`Items: ${itemCount}`);
console.log(`Subtotal: $${cartTotal.toFixed(2)}`);
console.log(`Discount (10%): -$${discount.toFixed(2)}`);
console.log(`Tax (7.5%): $${tax.toFixed(2)}`);
console.log(`Total: $${finalTotal.toFixed(2)}`);
```

---

## Checklist

- [ ] `var` leaks out of the `if` block
- [ ] `let` throws ReferenceError outside its block
- [ ] `const` throws TypeError on reassignment
- [ ] `const` object properties can be mutated
- [ ] `var` hoisting shows `undefined` before declaration
- [ ] `let` TDZ throws ReferenceError before declaration
- [ ] Shopping cart uses `const` for rates and `let` for totals

---

## Bonus Challenges

1. Create a `const` array of 5 favourite movies, then `push` a 6th — confirm it works
2. Try to reassign the array itself — confirm it throws
3. Rewrite the shopping cart using only `var` — what breaks?
