# Notes — Functions: Declaration, Expression, Arrow

## Function Declaration

```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

// Hoisted — can call before definition
greet('Alex'); // works even if called above the function
```

## Function Expression

```javascript
const greet = function(name) {
  return `Hello, ${name}!`;
};

// Named function expression (useful for recursion and stack traces)
const factorial = function fact(n) {
  return n <= 1 ? 1 : n * fact(n - 1);
};
```

## Arrow Functions

```javascript
// Full syntax
const greet = (name) => {
  return `Hello, ${name}!`;
};

// Implicit return (single expression — no braces, no return)
const greet = (name) => `Hello, ${name}!`;

// Single parameter — parentheses optional
const double = n => n * 2;

// No parameters — parentheses required
const getRandom = () => Math.random();

// Returning an object — wrap in parentheses
const getUser = () => ({ name: 'Alex', age: 25 });
// Without parens: () => { name: 'Alex' } is a code block, not an object!
```

## Key Differences

| | Declaration | Expression | Arrow |
|---|---|---|---|
| Hoisted | ✅ | ❌ | ❌ |
| Own `this` | ✅ | ✅ | ❌ (inherits) |
| `arguments` object | ✅ | ✅ | ❌ |
| Can be constructor | ✅ | ✅ | ❌ |

## When to Use Each

```javascript
// Arrow: callbacks, array methods, short utilities
const doubled = numbers.map(n => n * 2);
setTimeout(() => console.log('done'), 1000);

// Declaration: main named functions
function calculateTotal(items) { ... }

// Expression: when you need a named function in a variable
const handleSubmit = function handleSubmit(e) { ... };
```

## Common Mistakes

```javascript
// ❌ Forgetting return in multi-line arrow
const add = (a, b) => {
  a + b; // returns undefined!
};

// ✅ Correct
const add = (a, b) => {
  return a + b;
};

// ❌ Returning object without parens
const getUser = () => { name: 'Alex' }; // code block, not object

// ✅ Correct
const getUser = () => ({ name: 'Alex' });

// ❌ Arrow function as object method (this is wrong)
const obj = {
  name: 'Alex',
  greet: () => `Hello, ${this.name}` // this is undefined!
};

// ✅ Use regular function for methods
const obj = {
  name: 'Alex',
  greet() { return `Hello, ${this.name}`; }
};
```
