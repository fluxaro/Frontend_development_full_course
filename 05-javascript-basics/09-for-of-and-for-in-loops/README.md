# 09 — for-of and for-in Loops

## What Is This Lesson About?

`for-of` and `for-in` are modern loop syntax that are cleaner than traditional `for` loops for iterating over arrays and objects.

---

## for-of — Iterate Over Values

Use `for-of` to loop over any iterable (arrays, strings, Maps, Sets):

```javascript
const fruits = ['apple', 'banana', 'cherry'];

for (const fruit of fruits) {
  console.log(fruit); // apple, banana, cherry
}

// Works on strings too
for (const char of 'hello') {
  console.log(char); // h, e, l, l, o
}

// With index using entries()
for (const [index, fruit] of fruits.entries()) {
  console.log(index, fruit); // 0 apple, 1 banana, 2 cherry
}
```

---

## for-in — Iterate Over Object Keys

Use `for-in` to loop over the enumerable properties of an object:

```javascript
const user = { name: 'Alex', age: 25, city: 'Lagos' };

for (const key in user) {
  console.log(key, ':', user[key]);
  // name : Alex
  // age : 25
  // city : Lagos
}
```

**Warning:** `for-in` also iterates over inherited properties. Use `hasOwnProperty` or prefer `Object.keys()`:

```javascript
for (const key in user) {
  if (user.hasOwnProperty(key)) {
    console.log(key, user[key]);
  }
}
```

---

## for-of vs for-in vs forEach

| | `for-of` | `for-in` | `forEach` |
|---|---|---|---|
| Works on | Iterables (arrays, strings) | Objects | Arrays only |
| Gets | Values | Keys | Values + index |
| Can `break` | ✅ | ✅ | ❌ |
| Can `continue` | ✅ | ✅ | ❌ |

---

## Common Mistakes

- Using `for-in` on arrays (gets string indices, not numbers)
- Using `for-of` on plain objects (not iterable — use `for-in` or `Object.entries()`)
- Forgetting that `for-in` includes inherited properties
