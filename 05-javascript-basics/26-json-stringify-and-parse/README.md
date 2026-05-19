# 26 — JSON: stringify and parse

## What Is This Lesson About?

JSON (JavaScript Object Notation) is the standard format for exchanging data between a browser and a server. `JSON.stringify` converts JS to JSON, and `JSON.parse` converts JSON back to JS.

---

## JSON.stringify

Converts a JavaScript value to a JSON string:

```javascript
const user = { name: 'Alex', age: 25, active: true };
JSON.stringify(user);
// '{"name":"Alex","age":25,"active":true}'

// Pretty print (indent with 2 spaces)
JSON.stringify(user, null, 2);
// {
//   "name": "Alex",
//   "age": 25,
//   "active": true
// }

// Replacer — include only certain keys
JSON.stringify(user, ['name', 'age']);
// '{"name":"Alex","age":25}'
```

---

## JSON.parse

Converts a JSON string back to a JavaScript value:

```javascript
const json = '{"name":"Alex","age":25}';
const user = JSON.parse(json);
user.name; // 'Alex'

// Always wrap in try/catch
try {
  const data = JSON.parse(rawString);
} catch (e) {
  console.error('Invalid JSON:', e.message);
}
```

---

## What JSON Supports

| JS Type | JSON |
|---|---|
| `string` | ✅ `"hello"` |
| `number` | ✅ `42` |
| `boolean` | ✅ `true` |
| `null` | ✅ `null` |
| `object` | ✅ `{}` |
| `array` | ✅ `[]` |
| `undefined` | ❌ (omitted) |
| `function` | ❌ (omitted) |
| `Date` | ❌ (becomes string) |
| `Symbol` | ❌ (omitted) |

---

## Deep Clone with JSON

```javascript
// Quick deep clone (loses functions, dates, undefined)
const clone = JSON.parse(JSON.stringify(original));
```

---

## Common Mistakes

- Not wrapping `JSON.parse` in try/catch (invalid JSON throws)
- Expecting `undefined` values to survive stringify (they're omitted)
- Using JSON to clone objects with functions or Dates (they're lost)
- Forgetting that JSON keys must be double-quoted strings
