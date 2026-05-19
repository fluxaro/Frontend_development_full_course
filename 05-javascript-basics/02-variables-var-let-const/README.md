# 02 — Variables: var, let, const

## What Is This Lesson About?

Variables are named containers for storing data. JavaScript has three ways to declare variables: `var`, `let`, and `const`. Understanding the differences — especially scope and reassignment — is fundamental to writing correct JavaScript.

---

## The Three Keywords

```javascript
var name = 'Alex';    // old way — avoid
let age = 25;         // block-scoped, can be reassigned
const PI = 3.14159;   // block-scoped, cannot be reassigned
```

---

## var — Function Scoped (Avoid)

`var` is function-scoped and hoisted. It has confusing behaviour that causes bugs:

```javascript
// var is function-scoped
function example() {
  var x = 10;
  if (true) {
    var x = 20; // same variable! overwrites the outer x
    console.log(x); // 20
  }
  console.log(x); // 20 — unexpected!
}

// var is hoisted
console.log(y); // undefined (not an error!)
var y = 5;
```

**Rule: Never use `var` in modern JavaScript.**

---

## let — Block Scoped, Reassignable

`let` is block-scoped (limited to `{}`) and can be reassigned:

```javascript
let score = 0;
score = 10;    // ✅ reassignment allowed
score += 5;    // ✅ score is now 15

// Block scope
if (true) {
  let blockVar = 'inside';
  console.log(blockVar); // 'inside'
}
console.log(blockVar); // ❌ ReferenceError — not accessible outside block
```

Use `let` when the value will change (counters, loop variables, state).

---

## const — Block Scoped, Not Reassignable

`const` cannot be reassigned after declaration:

```javascript
const MAX_SIZE = 100;
MAX_SIZE = 200; // ❌ TypeError: Assignment to constant variable

// Must be initialised at declaration
const name; // ❌ SyntaxError
const name = 'Alex'; // ✅
```

**Important:** `const` prevents reassignment, not mutation:

```javascript
const user = { name: 'Alex', age: 25 };
user.age = 26;        // ✅ mutation is allowed
user = { name: 'Sam' }; // ❌ reassignment is not allowed

const nums = [1, 2, 3];
nums.push(4);  // ✅ mutation allowed
nums = [5, 6]; // ❌ reassignment not allowed
```

---

## Naming Conventions

```javascript
// camelCase for variables and functions
let firstName = 'Alex';
let totalScore = 0;

// SCREAMING_SNAKE_CASE for constants
const MAX_RETRIES = 3;
const API_URL = 'https://api.example.com';

// PascalCase for classes
class UserProfile {}

// Descriptive names — not single letters (except loop counters)
let i = 0;          // ✅ loop counter
let x = 42;         // ❌ what is x?
let userAge = 42;   // ✅ clear
```

---

## Quick Decision Guide

| Situation | Use |
|---|---|
| Value never changes | `const` |
| Value will be reassigned | `let` |
| Loop counter | `let` |
| Object/array that gets mutated | `const` |
| Legacy code | `var` (read only, don't write) |

**Default rule: always use `const`. Switch to `let` only when you need to reassign.**

---

## Common Mistakes

- Using `var` in new code
- Using `let` when `const` would work (prefer `const` by default)
- Trying to reassign a `const` (use `let` instead)
- Declaring variables without initialising them when using `const`
- Using single-letter variable names outside of loop counters
