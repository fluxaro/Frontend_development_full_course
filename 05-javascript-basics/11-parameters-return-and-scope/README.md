# 11 — Parameters, Return, and Scope

## What Is This Lesson About?

Functions receive data through parameters and send data back with `return`. Scope determines where variables are accessible.

---

## Parameters and Arguments

```javascript
// Parameters are the names in the definition
function add(a, b) {
  return a + b;
}

// Arguments are the values passed in
add(3, 5); // 8

// Default parameters
function greet(name = 'World') {
  return `Hello, ${name}!`;
}
greet();        // 'Hello, World!'
greet('Alex');  // 'Hello, Alex!'

// Rest parameters — collect remaining args into array
function sum(...numbers) {
  return numbers.reduce((total, n) => total + n, 0);
}
sum(1, 2, 3, 4); // 10
```

---

## Return

```javascript
function divide(a, b) {
  if (b === 0) return null; // early return
  return a / b;
}

// Functions without return return undefined
function logHello() {
  console.log('Hello');
}
const result = logHello(); // result is undefined
```

---

## Scope

```javascript
// Global scope — accessible everywhere
const globalVar = 'I am global';

function outer() {
  // Function scope
  const outerVar = 'I am in outer';

  function inner() {
    // Block scope
    const innerVar = 'I am in inner';
    console.log(globalVar); // ✅ accessible
    console.log(outerVar);  // ✅ accessible (closure)
    console.log(innerVar);  // ✅ accessible
  }

  inner();
  console.log(innerVar); // ❌ ReferenceError
}
```

---

## Scope Chain

When a variable is not found in the current scope, JavaScript looks up the scope chain to the parent scope, then grandparent, until it reaches global scope.

---

## Common Mistakes

- Forgetting `return` (function returns `undefined`)
- Accessing variables outside their scope
- Mutating parameters that are objects (affects the original)
- Using too many parameters — consider an options object instead
