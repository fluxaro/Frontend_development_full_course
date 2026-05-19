# 10 — Functions: Declaration, Expression, Arrow

## What Is This Lesson About?

Functions are reusable blocks of code. JavaScript has three ways to define them, each with different behaviour around hoisting and `this`.

---

## Function Declaration

```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet('Alex')); // Hello, Alex!
```

Function declarations are **hoisted** — you can call them before they are defined in the file.

---

## Function Expression

```javascript
const greet = function(name) {
  return `Hello, ${name}!`;
};

// Named function expression
const greet = function greetFn(name) {
  return `Hello, ${name}!`;
};
```

Function expressions are **not hoisted** — they must be defined before use.

---

## Arrow Functions

Shorter syntax, and they do **not** have their own `this`:

```javascript
// Full arrow function
const greet = (name) => {
  return `Hello, ${name}!`;
};

// Implicit return (single expression)
const greet = (name) => `Hello, ${name}!`;

// Single parameter — parentheses optional
const double = n => n * 2;

// No parameters — parentheses required
const getRandom = () => Math.random();

// Returning an object — wrap in parentheses
const getUser = () => ({ name: 'Alex', age: 25 });
```

---

## Key Differences

| | Declaration | Expression | Arrow |
|---|---|---|---|
| Hoisted | ✅ | ❌ | ❌ |
| Own `this` | ✅ | ✅ | ❌ |
| `arguments` object | ✅ | ✅ | ❌ |
| Can be constructor | ✅ | ✅ | ❌ |

---

## When to Use Each

- **Arrow functions** — callbacks, array methods, short utilities
- **Function declarations** — main named functions, when hoisting is useful
- **Function expressions** — when you need a named function stored in a variable

---

## Common Mistakes

- Forgetting `return` in a multi-line arrow function
- Returning an object literal without wrapping in `()`
- Using arrow functions as methods (they don't have their own `this`)
