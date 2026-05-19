# 15 — Object Methods: keys, values, entries

## What Is This Lesson About?

`Object.keys()`, `Object.values()`, and `Object.entries()` convert objects into arrays so you can use array methods on them. `Object.assign()` and the spread operator copy objects.

---

## Object.keys()

Returns an array of the object's own enumerable property names:

```javascript
const user = { name: 'Alex', age: 25, city: 'Lagos' };
Object.keys(user); // ['name', 'age', 'city']

// Count properties
Object.keys(user).length; // 3

// Check if empty
Object.keys(user).length === 0; // false
```

---

## Object.values()

Returns an array of the object's own enumerable property values:

```javascript
Object.values(user); // ['Alex', 25, 'Lagos']

// Sum all values
const scores = { math: 90, english: 85, science: 92 };
const total = Object.values(scores).reduce((sum, s) => sum + s, 0); // 267
```

---

## Object.entries()

Returns an array of `[key, value]` pairs — great for transforming objects:

```javascript
Object.entries(user);
// [['name','Alex'], ['age',25], ['city','Lagos']]

// Iterate with destructuring
for (const [key, value] of Object.entries(user)) {
  console.log(`${key}: ${value}`);
}

// Transform object values
const doubled = Object.fromEntries(
  Object.entries(scores).map(([key, val]) => [key, val * 2])
);
```

---

## Object.assign()

Copies properties from source objects into a target:

```javascript
const defaults = { theme: 'light', lang: 'en' };
const userPrefs = { theme: 'dark' };
const config = Object.assign({}, defaults, userPrefs);
// { theme: 'dark', lang: 'en' }
```

---

## Object.freeze() and Object.seal()

```javascript
const config = Object.freeze({ API_URL: 'https://api.example.com' });
config.API_URL = 'other'; // silently fails (or throws in strict mode)

const obj = Object.seal({ name: 'Alex' });
obj.name = 'Sam'; // ✅ can modify existing
obj.age = 25;     // ❌ cannot add new properties
```

---

## Common Mistakes

- `Object.keys()` only returns own properties, not inherited ones
- `Object.assign()` does a shallow copy — nested objects are still references
- `Object.freeze()` is shallow — nested objects are not frozen
