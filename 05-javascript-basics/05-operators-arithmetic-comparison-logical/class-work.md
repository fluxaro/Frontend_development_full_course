# Class Work — Operators in Practice

## What You Will Build

A JavaScript file exploring all operator types with practical examples.

**Time:** 25 minutes  
**Output:** `operators-practice.html`

---

## Step 1 — Arithmetic

```javascript
console.group('Arithmetic');
let score = 100;
score += 50;   console.log('After +50:', score);
score -= 30;   console.log('After -30:', score);
score *= 2;    console.log('After *2:', score);
score /= 4;    console.log('After /4:', score);
score %= 7;    console.log('After %7:', score);
console.log('2**10:', 2**10);
console.groupEnd();
```

---

## Step 2 — Comparison

```javascript
console.group('Comparison');
console.log(10 > 5, 10 < 5, 10 >= 10, 10 <= 9);
console.log(10 === 10, 10 === '10', 10 !== '10');
console.groupEnd();
```

---

## Step 3 — Logical

```javascript
console.group('Logical');
const age = 20;
const hasID = true;
console.log('Can enter:', age >= 18 && hasID);
console.log('Gets discount:', age < 18 || age >= 65);

// Short-circuit
const username = '' || 'Anonymous';
console.log('Username:', username);

const user = null;
const city = user && user.city;
console.log('City:', city); // null (safe)
console.groupEnd();
```

---

## Checklist

- [ ] All arithmetic operators demonstrated
- [ ] `===` vs `==` difference shown
- [ ] `&&` and `||` short-circuit patterns work
- [ ] Fallback with `||` works correctly
