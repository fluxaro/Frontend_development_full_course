# Notes — Array Methods: reduce, find, some, every

## reduce — Accumulate to a Single Value

```javascript
// Syntax: array.reduce(callback, initialValue)
// callback receives: (accumulator, currentValue, index, array)

const numbers = [1, 2, 3, 4, 5];

// Sum
const sum = numbers.reduce((acc, n) => acc + n, 0); // 15

// Product
const product = numbers.reduce((acc, n) => acc * n, 1); // 120

// Max value
const max = numbers.reduce((acc, n) => n > acc ? n : acc, -Infinity);

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
// { admin: [Alex, Jordan], user: [Sam] }

// Flatten array
const nested = [[1,2], [3,4], [5,6]];
const flat = nested.reduce((acc, arr) => [...acc, ...arr], []);
// [1, 2, 3, 4, 5, 6]
```

## find — First Matching Element

Returns the element itself (or `undefined` if not found):

```javascript
const users = [
  { id: 1, name: 'Alex' },
  { id: 2, name: 'Sam' },
  { id: 3, name: 'Jordan' },
];

const user = users.find(u => u.id === 2);    // { id: 2, name: 'Sam' }
const missing = users.find(u => u.id === 99); // undefined

// findIndex — returns index instead of element
const index = users.findIndex(u => u.id === 2); // 1
```

## some — At Least One Passes

Returns `true` if at least one element passes the test. Short-circuits on first match:

```javascript
const numbers = [1, 2, 3, 4, 5];
numbers.some(n => n > 4);   // true (5 passes)
numbers.some(n => n > 10);  // false (none pass)
numbers.some(n => n === 3); // true

// Practical use
const hasAdmin = users.some(u => u.role === 'admin');
const hasErrors = errors.some(e => e.severity === 'critical');
```

## every — All Must Pass

Returns `true` only if ALL elements pass. Short-circuits on first failure:

```javascript
numbers.every(n => n > 0);  // true (all positive)
numbers.every(n => n > 3);  // false (1, 2, 3 fail)
numbers.every(n => n < 10); // true

// Practical use
const allActive = users.every(u => u.active);
const allValid = inputs.every(input => input.value.trim() !== '');
```

## Chaining Methods

```javascript
const result = products
  .filter(p => p.inStock)           // keep in-stock only
  .map(p => ({ ...p, price: p.price * 0.9 })) // apply 10% discount
  .sort((a, b) => a.price - b.price) // sort by price
  .slice(0, 5);                      // take first 5
```

## Common Mistakes

- Forgetting the initial value in `reduce` — causes bugs with empty arrays
- Using `find` when you need all matches (use `filter`)
- Using `filter` when you only need the first match (use `find` — it's faster)
- `some` and `every` short-circuit — they stop as soon as the result is known
- `reduce` without an initial value uses the first element as the accumulator
