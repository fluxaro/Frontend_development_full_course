# Notes — for-of and for-in Loops

## for-of — Iterate Over Values

Works on any iterable: arrays, strings, Maps, Sets, NodeLists.

```javascript
// Arrays
const fruits = ['apple', 'banana', 'cherry'];
for (const fruit of fruits) {
  console.log(fruit); // apple, banana, cherry
}

// Strings
for (const char of 'hello') {
  console.log(char); // h, e, l, l, o
}

// With index using entries()
for (const [index, fruit] of fruits.entries()) {
  console.log(index, fruit); // 0 apple, 1 banana, 2 cherry
}

// NodeList (DOM elements)
for (const el of document.querySelectorAll('.card')) {
  el.classList.add('active');
}
```

## for-in — Iterate Over Object Keys

```javascript
const user = { name: 'Alex', age: 25, city: 'Lagos' };

for (const key in user) {
  console.log(`${key}: ${user[key]}`);
  // name: Alex
  // age: 25
  // city: Lagos
}

// Safe version — only own properties
for (const key in user) {
  if (Object.hasOwn(user, key)) {
    console.log(key, user[key]);
  }
}
```

## Comparison Table

| | `for` | `for-of` | `for-in` | `forEach` |
|---|---|---|---|---|
| Works on | Anything | Iterables | Objects | Arrays |
| Gets | Index | Values | Keys | Values + index |
| Can `break` | ✅ | ✅ | ✅ | ❌ |
| Can `continue` | ✅ | ✅ | ✅ | ❌ |
| `async/await` | ✅ | ✅ | ✅ | ❌ |

## Practical Patterns

```javascript
// Sum array values
let total = 0;
for (const price of prices) total += price;

// Find first match (with break)
for (const user of users) {
  if (user.id === targetId) {
    console.log('Found:', user);
    break;
  }
}

// Build HTML from object
let html = '';
for (const [key, value] of Object.entries(config)) {
  html += `<li>${key}: ${value}</li>`;
}
```

## Common Mistakes

- Using `for-in` on arrays — it iterates string indices ('0', '1', '2') and inherited properties
- Using `for-of` on plain objects — objects are not iterable (use `Object.entries()`)
- Forgetting that `forEach` cannot use `break` or `continue`
- Not using `for-of` with `await` inside async functions (forEach doesn't work with async)
