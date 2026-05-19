# 13 — Array Methods: reduce, find, some, every

## What Is This Lesson About?

Advanced array methods that let you aggregate data, search arrays, and test conditions across all elements.

---

## reduce — Accumulate to a Single Value

```javascript
const numbers = [1, 2, 3, 4, 5];

// Sum
const sum = numbers.reduce((acc, n) => acc + n, 0); // 15

// Product
const product = numbers.reduce((acc, n) => acc * n, 1); // 120

// Count occurrences
const words = ['cat', 'dog', 'cat', 'bird', 'dog', 'cat'];
const counts = words.reduce((acc, word) => {
  acc[word] = (acc[word] || 0) + 1;
  return acc;
}, {});
// { cat: 3, dog: 2, bird: 1 }

// Group by property
const users = [
  { name: 'Alex', role: 'admin' },
  { name: 'Sam', role: 'user' },
  { name: 'Jordan', role: 'admin' },
];
const byRole = users.reduce((acc, user) => {
  if (!acc[user.role]) acc[user.role] = [];
  acc[user.role].push(user);
  return acc;
}, {});
```

---

## find — First Matching Element

Returns the first element that passes the test, or `undefined`:

```javascript
const users = [
  { id: 1, name: 'Alex' },
  { id: 2, name: 'Sam' },
];

const user = users.find(u => u.id === 2); // { id: 2, name: 'Sam' }
const missing = users.find(u => u.id === 99); // undefined
```

---

## findIndex — Index of First Match

```javascript
const index = users.findIndex(u => u.id === 2); // 1
```

---

## some — At Least One Passes

Returns `true` if at least one element passes the test:

```javascript
const numbers = [1, 2, 3, 4, 5];
numbers.some(n => n > 4);  // true (5 > 4)
numbers.some(n => n > 10); // false
```

---

## every — All Must Pass

Returns `true` only if ALL elements pass the test:

```javascript
numbers.every(n => n > 0);  // true (all positive)
numbers.every(n => n > 3);  // false (1, 2, 3 fail)
```

---

## Chaining Methods

```javascript
const result = users
  .filter(u => u.active)
  .map(u => u.name)
  .sort();
```

---

## Common Mistakes

- Forgetting the initial value in `reduce` (causes bugs with empty arrays)
- Using `find` when you need all matches (use `filter`)
- `some` and `every` short-circuit — they stop as soon as the result is known
