# 32 — Closures and Lexical Scope

## What Is This Lesson About?

A closure is a function that remembers variables from its outer scope even after the outer function has returned. This is one of the most powerful and widely-used patterns in JavaScript.

---

## Lexical Scope

JavaScript uses lexical (static) scope — a function's scope is determined by where it is written, not where it is called:

```javascript
const x = 'global';

function outer() {
  const x = 'outer';

  function inner() {
    console.log(x); // 'outer' — uses the scope where inner was defined
  }

  inner();
}
```

---

## Closures

A closure is created when an inner function accesses variables from its outer function's scope:

```javascript
function makeCounter() {
  let count = 0; // this variable is "closed over"

  return {
    increment() { count++; },
    decrement() { count--; },
    getCount() { return count; },
  };
}

const counter = makeCounter();
counter.increment();
counter.increment();
counter.getCount(); // 2
// count is private — not accessible from outside
```

---

## Practical Uses

### Data Privacy

```javascript
function createBankAccount(initial) {
  let balance = initial; // private

  return {
    deposit(amount) { balance += amount; },
    withdraw(amount) {
      if (amount > balance) throw new Error('Insufficient funds');
      balance -= amount;
    },
    getBalance() { return balance; },
  };
}
```

### Factory Functions

```javascript
function createMultiplier(factor) {
  return (n) => n * factor;
}

const double = createMultiplier(2);
const triple = createMultiplier(3);
double(5); // 10
triple(5); // 15
```

---

## The Loop Closure Bug

```javascript
// Bug: all buttons alert "3"
for (var i = 0; i < 3; i++) {
  buttons[i].onclick = function() { alert(i); };
}

// Fix 1: use let (block-scoped)
for (let i = 0; i < 3; i++) {
  buttons[i].onclick = function() { alert(i); };
}

// Fix 2: IIFE
for (var i = 0; i < 3; i++) {
  (function(j) {
    buttons[j].onclick = function() { alert(j); };
  })(i);
}
```

---

## Common Mistakes

- The loop closure bug (use `let` instead of `var`)
- Closures holding references to large objects (memory leaks)
- Confusing closures with copies — closures hold references, not values
