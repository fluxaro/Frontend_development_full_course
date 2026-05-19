# 16 — Destructuring Arrays and Objects

## What Is This Lesson About?

Destructuring is a concise syntax for extracting values from arrays and properties from objects into variables.

---

## Object Destructuring

```javascript
const user = { name: 'Alex', age: 25, city: 'Lagos' };

// Basic
const { name, age } = user;
console.log(name, age); // 'Alex' 25

// Rename
const { name: userName, age: userAge } = user;

// Default values
const { name, role = 'user' } = user; // role is 'user' if not in object

// Nested
const { address: { city, country } } = user;

// In function parameters
function greet({ name, age = 0 }) {
  return `${name} is ${age}`;
}
greet(user);
```

---

## Array Destructuring

```javascript
const [first, second, third] = [1, 2, 3];

// Skip elements
const [, second, , fourth] = [1, 2, 3, 4];

// Rest
const [head, ...tail] = [1, 2, 3, 4, 5];
// head = 1, tail = [2, 3, 4, 5]

// Default values
const [a = 0, b = 0] = [1];
// a = 1, b = 0

// Swap variables
let x = 1, y = 2;
[x, y] = [y, x]; // x = 2, y = 1
```

---

## Destructuring in Loops

```javascript
const users = [
  { name: 'Alex', age: 25 },
  { name: 'Sam', age: 30 },
];

for (const { name, age } of users) {
  console.log(name, age);
}

// Object.entries
for (const [key, value] of Object.entries(config)) {
  console.log(key, value);
}
```

---

## Common Mistakes

- Destructuring a property that doesn't exist gives `undefined` (not an error)
- Forgetting `{}` around object destructuring in function parameters
- Nested destructuring can get hard to read — use intermediate variables
