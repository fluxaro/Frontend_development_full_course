# 03 — Data Types: String, Number, Boolean

## What Is This Lesson About?

JavaScript has 8 data types. The three most common primitive types are **String**, **Number**, and **Boolean**. Understanding how they work — and how to check them — is essential for writing correct JavaScript.

---

## The 8 JavaScript Data Types

| Type | Example | Category |
|---|---|---|
| `string` | `'hello'` | Primitive |
| `number` | `42`, `3.14` | Primitive |
| `boolean` | `true`, `false` | Primitive |
| `undefined` | `let x;` | Primitive |
| `null` | `null` | Primitive |
| `symbol` | `Symbol('id')` | Primitive |
| `bigint` | `9007199254740991n` | Primitive |
| `object` | `{}`, `[]`, `null` | Object |

---

## String

A string is a sequence of characters wrapped in quotes:

```javascript
const single = 'Hello';
const double = "World";
const template = `Hello, ${name}!`; // template literal

// String properties and methods
'hello'.length;           // 5
'hello'.toUpperCase();    // 'HELLO'
'hello'.includes('ell');  // true
'hello'.slice(1, 3);      // 'el'
'  hello  '.trim();       // 'hello'
'a,b,c'.split(',');       // ['a', 'b', 'c']
'hello'.replace('l', 'r'); // 'herlo'
```

---

## Number

JavaScript has only one number type — it handles both integers and decimals:

```javascript
const integer = 42;
const decimal = 3.14;
const negative = -10;
const scientific = 1.5e6; // 1,500,000

// Special values
Infinity;   // 1/0
-Infinity;  // -1/0
NaN;        // Not a Number (0/0, parseInt('abc'))

// Number methods
(3.14159).toFixed(2);    // '3.14'
(1234567).toLocaleString(); // '1,234,567'
Number.isInteger(42);    // true
Number.isNaN(NaN);       // true
Math.round(4.6);         // 5
Math.floor(4.9);         // 4
Math.ceil(4.1);          // 5
Math.max(1, 5, 3);       // 5
Math.random();           // 0 to 0.999...
```

---

## Boolean

A boolean is either `true` or `false`:

```javascript
const isLoggedIn = true;
const hasError = false;

// Comparison operators return booleans
5 > 3;      // true
5 === 5;    // true
5 !== 3;    // true
```

### Truthy and Falsy

Every value in JavaScript is either truthy or falsy when used in a boolean context:

**Falsy values (only 6):**
```javascript
false, 0, '', null, undefined, NaN
```

**Everything else is truthy**, including:
```javascript
'0', [], {}, -1, Infinity
```

---

## typeof Operator

```javascript
typeof 'hello';     // 'string'
typeof 42;          // 'number'
typeof true;        // 'boolean'
typeof undefined;   // 'undefined'
typeof null;        // 'object' ← famous bug in JS
typeof {};          // 'object'
typeof [];          // 'object'
typeof function(){}; // 'function'
```

---

## Common Mistakes

- `typeof null === 'object'` — this is a known JS bug, not a feature
- `NaN !== NaN` — use `Number.isNaN()` to check for NaN
- Floating point precision: `0.1 + 0.2 !== 0.3` (use `.toFixed()` for display)
- Empty string `''` is falsy, but `'0'` is truthy
