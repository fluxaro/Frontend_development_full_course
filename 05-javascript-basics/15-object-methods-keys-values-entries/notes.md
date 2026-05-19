# Notes — Object Methods: keys, values, entries

## Object.keys()

Returns an array of the object's own enumerable property names:

```javascript
const user = { name: 'Alex', age: 25, city: 'Lagos' };

Object.keys(user);          // ['name', 'age', 'city']
Object.keys(user).length;   // 3 — count properties
Object.keys({}).length === 0; // true — check if empty

// Iterate keys
Object.keys(user).forEach(key => {
  console.log(key, user[key]);
});

// Filter keys
const stringKeys = Object.keys(user).filter(k => typeof user[k] === 'string');
// ['name', 'city']
```

## Object.values()

Returns an array of the object's own enumerable property values:

```javascript
Object.values(user); // ['Alex', 25, 'Lagos']

// Sum all values
const scores = { math: 90, english: 85, science: 92 };
const total = Object.values(scores).reduce((sum, s) => sum + s, 0); // 267
const avg = total / Object.values(scores).length; // 89

// Check if any value matches
Object.values(user).includes('Alex'); // true
```

## Object.entries()

Returns an array of `[key, value]` pairs — the most versatile:

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
// { math: 180, english: 170, science: 184 }

// Filter object entries
const highScores = Object.fromEntries(
  Object.entries(scores).filter(([, val]) => val >= 90)
);
// { math: 90, science: 92 }
```

## Object.fromEntries()

Converts an array of `[key, value]` pairs back to an object:

```javascript
const entries = [['name', 'Alex'], ['age', 25]];
Object.fromEntries(entries); // { name: 'Alex', age: 25 }

// Convert Map to object
const map = new Map([['a', 1], ['b', 2]]);
Object.fromEntries(map); // { a: 1, b: 2 }
```

## Object.assign()

Copies properties from source objects into a target:

```javascript
const defaults = { theme: 'light', lang: 'en', fontSize: 16 };
const userPrefs = { theme: 'dark', fontSize: 18 };

// Merge (later sources override earlier)
const config = Object.assign({}, defaults, userPrefs);
// { theme: 'dark', lang: 'en', fontSize: 18 }

// Spread is cleaner for merging
const config2 = { ...defaults, ...userPrefs };
```

## Object.freeze() and Object.seal()

```javascript
// freeze — no changes at all (shallow)
const config = Object.freeze({ API_URL: 'https://api.example.com', version: 1 });
config.version = 2;    // silently fails (throws in strict mode)
config.newProp = 'x';  // silently fails

// seal — can modify existing, cannot add/delete
const obj = Object.seal({ name: 'Alex', age: 25 });
obj.name = 'Sam';  // ✅ can modify
obj.email = 'x';   // ❌ cannot add
delete obj.age;    // ❌ cannot delete
```

## Common Patterns

```javascript
// Check if object is empty
const isEmpty = obj => Object.keys(obj).length === 0;

// Pick specific keys
const pick = (obj, keys) =>
  Object.fromEntries(keys.map(k => [k, obj[k]]));

pick(user, ['name', 'email']); // { name: 'Alex', email: '...' }

// Omit specific keys
const omit = (obj, keys) =>
  Object.fromEntries(Object.entries(obj).filter(([k]) => !keys.includes(k)));

omit(user, ['password', 'token']); // user without sensitive fields
```

## Common Mistakes

- `Object.keys()` only returns own properties, not inherited ones
- `Object.assign()` does a shallow copy — nested objects are still references
- `Object.freeze()` is shallow — nested objects are not frozen
- `Object.entries()` order follows insertion order for string keys
