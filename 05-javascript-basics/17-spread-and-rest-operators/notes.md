# Notes — Spread and Rest Operators

## Spread Operator (...)

Expands an iterable into individual elements.

### Spread Arrays

```javascript
const a = [1, 2, 3];
const b = [4, 5, 6];

// Merge arrays
const merged = [...a, ...b];          // [1, 2, 3, 4, 5, 6]

// Copy array (shallow)
const copy = [...a];                  // [1, 2, 3] — new array

// Add elements
const withExtra = [0, ...a, 4];       // [0, 1, 2, 3, 4]

// Pass array as function arguments
Math.max(...a);                       // 3
Math.min(...a);                       // 1
console.log(...a);                    // 1 2 3

// Convert string to array of characters
const chars = [..."hello"];           // ['h','e','l','l','o']

// Convert Set to array (removes duplicates)
const unique = [...new Set([1,2,2,3,3,4])]; // [1, 2, 3, 4]
```

### Spread Objects

```javascript
const defaults = { theme: 'light', lang: 'en', fontSize: 16 };
const overrides = { theme: 'dark', fontSize: 18 };

// Merge objects (later properties win)
const config = { ...defaults, ...overrides };
// { theme: 'dark', lang: 'en', fontSize: 18 }

// Copy object (shallow)
const copy = { ...user };

// Add/override properties
const updated = { ...user, age: 26, updatedAt: Date.now() };

// Remove a property (spread + destructuring)
const { password, ...safeUser } = user;
// safeUser has everything except password
```

## Rest Parameters (...)

Collects remaining function arguments into an array.

```javascript
// Rest must be the LAST parameter
function sum(...numbers) {
  return numbers.reduce((total, n) => total + n, 0);
}
sum(1, 2, 3, 4, 5); // 15
sum();               // 0

// Mix with regular parameters
function log(level, ...messages) {
  console.log(`[${level.toUpperCase()}]`, ...messages);
}
log('info', 'Server started', 'Port 3000');
// [INFO] Server started Port 3000

// Rest in destructuring
const [first, second, ...rest] = [1, 2, 3, 4, 5];
// first=1, second=2, rest=[3,4,5]

const { name, ...others } = user;
// name='Alex', others={ age:25, city:'Lagos' }
```

## Spread vs Rest

| | Spread | Rest |
|---|---|---|
| Position | In a call or literal | In a definition |
| Direction | Expands | Collects |
| Example | `fn(...arr)` | `function fn(...args)` |

## Shallow Copy Warning

```javascript
// Spread creates a SHALLOW copy
const original = { name: 'Alex', address: { city: 'Lagos' } };
const copy = { ...original };

copy.name = 'Sam';           // ✅ doesn't affect original
copy.address.city = 'Abuja'; // ❌ DOES affect original (nested object is shared)

// Deep copy: use structuredClone() (modern) or JSON.parse(JSON.stringify())
const deepCopy = structuredClone(original);
```

## Common Mistakes

- Spread creates a **shallow** copy — nested objects are still references
- Rest must be the **last** parameter in a function
- `...` in a function definition = rest; `...` in a call/literal = spread
- Spreading a non-iterable throws a TypeError
