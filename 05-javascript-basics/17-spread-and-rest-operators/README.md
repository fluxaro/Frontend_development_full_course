# 17 — Spread and Rest Operators

## What Is This Lesson About?

The `...` operator does two different things depending on context: **spread** expands an iterable into individual elements, and **rest** collects multiple elements into an array.

---

## Spread Operator

### Spread Arrays

```javascript
const a = [1, 2, 3];
const b = [4, 5, 6];

// Merge arrays
const merged = [...a, ...b]; // [1, 2, 3, 4, 5, 6]

// Copy array (shallow)
const copy = [...a]; // [1, 2, 3]

// Add elements
const withExtra = [0, ...a, 4]; // [0, 1, 2, 3, 4]

// Pass array as arguments
Math.max(...a); // 3
```

### Spread Objects

```javascript
const defaults = { theme: 'light', lang: 'en' };
const overrides = { theme: 'dark' };

// Merge objects (later properties win)
const config = { ...defaults, ...overrides };
// { theme: 'dark', lang: 'en' }

// Copy object (shallow)
const copy = { ...user };

// Add/override properties
const updated = { ...user, age: 26 };
```

---

## Rest Parameters

Collects remaining function arguments into an array:

```javascript
function sum(...numbers) {
  return numbers.reduce((total, n) => total + n, 0);
}
sum(1, 2, 3, 4, 5); // 15

// Rest must be last parameter
function log(level, ...messages) {
  console.log(`[${level}]`, ...messages);
}
log('INFO', 'Server started', 'Port 3000');
```

---

## Rest in Destructuring

```javascript
// Array rest
const [first, second, ...rest] = [1, 2, 3, 4, 5];
// first=1, second=2, rest=[3,4,5]

// Object rest
const { name, age, ...others } = user;
// name='Alex', age=25, others={ city:'Lagos' }
```

---

## Common Mistakes

- Spread creates a **shallow** copy — nested objects are still references
- Rest must be the **last** parameter in a function
- `...` in a function definition = rest; `...` in a call = spread
