# Class Work — Exploring Data Types

## What You Will Build

A JavaScript file that explores strings, numbers, and booleans through hands-on examples. You will use the console to see how each type behaves.

**Time:** 30 minutes  
**Output:** `data-types-practice.html`

---

## Step 1 — Setup

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Data Types Practice</title>
</head>
<body>
  <h1>Data Types Practice</h1>
  <p>Open the console to see output.</p>
  <script>
    // code goes here
  </script>
</body>
</html>
```

---

## Step 2 — Strings

```javascript
console.group('Strings');

const greeting = 'Hello, World!';
console.log('Length:', greeting.length);
console.log('Uppercase:', greeting.toUpperCase());
console.log('Includes "World":', greeting.includes('World'));
console.log('Slice 0-5:', greeting.slice(0, 5));
console.log('Replace:', greeting.replace('World', 'JavaScript'));

// Template literals
const name = 'Alex';
const age = 25;
console.log(`My name is ${name} and I am ${age} years old.`);
console.log(`Next year I will be ${age + 1}.`);
console.log(`2 + 2 = ${2 + 2}`);

// Split and join
const csv = 'HTML,CSS,JavaScript,React';
const skills = csv.split(',');
console.log('Skills array:', skills);
console.log('Joined:', skills.join(' | '));

console.groupEnd();
```

---

## Step 3 — Numbers

```javascript
console.group('Numbers');

console.log('Integer:', 42);
console.log('Decimal:', 3.14159);
console.log('Negative:', -273.15);
console.log('Scientific:', 1.5e6);

// Special values
console.log('Infinity:', 1/0);
console.log('-Infinity:', -1/0);
console.log('NaN:', 0/0);
console.log('NaN check:', Number.isNaN(NaN));

// Math
console.log('Round 4.6:', Math.round(4.6));
console.log('Floor 4.9:', Math.floor(4.9));
console.log('Ceil 4.1:', Math.ceil(4.1));
console.log('Max:', Math.max(1, 5, 3, 9, 2));
console.log('Random 1-10:', Math.floor(Math.random() * 10) + 1);

// Floating point
console.log('0.1 + 0.2:', 0.1 + 0.2);
console.log('0.1 + 0.2 === 0.3:', 0.1 + 0.2 === 0.3);
console.log('Fixed:', (0.1 + 0.2).toFixed(2));

console.groupEnd();
```

---

## Step 4 — Booleans and Truthy/Falsy

```javascript
console.group('Booleans');

// Falsy values
const falsyValues = [false, 0, '', null, undefined, NaN];
console.log('Falsy values:');
falsyValues.forEach(v => console.log(`  ${String(v)} → ${Boolean(v)}`));

// Truthy surprises
const truthyValues = ['0', [], {}, -1, Infinity, 'false'];
console.log('Truthy surprises:');
truthyValues.forEach(v => console.log(`  ${JSON.stringify(v)} → ${Boolean(v)}`));

// Practical use
const username = '';
if (username) {
  console.log('Welcome,', username);
} else {
  console.log('No username provided (empty string is falsy)');
}

console.groupEnd();
```

---

## Checklist

- [ ] String methods all produce correct output
- [ ] Template literals work with expressions
- [ ] `NaN` check uses `Number.isNaN()` not `=== NaN`
- [ ] `0.1 + 0.2 !== 0.3` is demonstrated
- [ ] All 6 falsy values are shown
- [ ] Truthy surprises (`'0'`, `[]`, `{}`) are shown

---

## Bonus Challenges

1. Write a function `isValidAge(age)` that returns `true` if age is a number between 0 and 120
2. Write a function `capitalize(str)` that capitalises the first letter of a string
3. Generate a random integer between 1 and 100 using `Math.random()`
