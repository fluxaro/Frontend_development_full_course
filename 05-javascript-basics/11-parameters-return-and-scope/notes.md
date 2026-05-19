# Notes — Parameters, Return, and Scope

## Parameters

```javascript
// Basic parameters
function add(a, b) { return a + b; }

// Default parameters
function greet(name = 'World', greeting = 'Hello') {
  return `${greeting}, ${name}!`;
}
greet();              // 'Hello, World!'
greet('Alex');        // 'Hello, Alex!'
greet('Alex', 'Hi'); // 'Hi, Alex!'

// Rest parameters — collect remaining args into array
function sum(first, ...rest) {
  return rest.reduce((total, n) => total + n, first);
}
sum(1, 2, 3, 4); // 10

// Options object pattern (better than many parameters)
function createUser({ name, age = 0, role = 'user' } = {}) {
  return { name, age, role };
}
createUser({ name: 'Alex', age: 25 });
```

## Return

```javascript
// Single return value
function square(n) { return n * n; }

// Early return (guard clause)
function divide(a, b) {
  if (b === 0) return null; // exit early
  return a / b;
}

// Return multiple values via object
function minMax(arr) {
  return {
    min: Math.min(...arr),
    max: Math.max(...arr),
  };
}
const { min, max } = minMax([3, 1, 4, 1, 5, 9]);

// No return = undefined
function logHello() { console.log('Hello'); }
const result = logHello(); // result is undefined
```

## Scope

```javascript
// Global scope
const globalVar = 'accessible everywhere';

function outer() {
  const outerVar = 'accessible in outer and inner';

  function inner() {
    const innerVar = 'only accessible in inner';
    console.log(globalVar); // ✅
    console.log(outerVar);  // ✅ (closure)
    console.log(innerVar);  // ✅
  }

  inner();
  // console.log(innerVar); // ❌ ReferenceError
}

// Block scope (let/const)
{
  let blockVar = 'only in this block';
  const blockConst = 'also only in this block';
}
// blockVar and blockConst not accessible here
```

## Scope Chain

When a variable is not found in the current scope, JavaScript looks up the chain:

```
inner scope → outer scope → global scope → ReferenceError
```

## Common Mistakes

```javascript
// ❌ Forgetting return
function double(n) {
  n * 2; // returns undefined!
}

// ✅ Correct
function double(n) {
  return n * 2;
}

// ❌ Mutating object parameters (affects original)
function addAge(user) {
  user.age = 25; // modifies the original object!
}

// ✅ Return a new object instead
function addAge(user) {
  return { ...user, age: 25 };
}
```
