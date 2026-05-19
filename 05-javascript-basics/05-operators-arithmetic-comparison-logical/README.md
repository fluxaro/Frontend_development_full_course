# 05 — Operators: Arithmetic, Comparison, Logical

## What Is This Lesson About?

Operators are symbols that perform operations on values. JavaScript has arithmetic operators for math, comparison operators for testing values, and logical operators for combining conditions.

---

## Arithmetic Operators

```javascript
5 + 3    // 8  — addition
5 - 3    // 2  — subtraction
5 * 3    // 15 — multiplication
5 / 3    // 1.666... — division
5 % 3    // 2  — modulo (remainder)
5 ** 3   // 125 — exponentiation
-5       // -5 — unary negation

// Increment / Decrement
let x = 5;
x++;     // post-increment: returns 5, then x becomes 6
++x;     // pre-increment: x becomes 7, returns 7
x--;     // post-decrement
--x;     // pre-decrement

// Assignment operators
x += 5;  // x = x + 5
x -= 3;  // x = x - 3
x *= 2;  // x = x * 2
x /= 4;  // x = x / 4
x %= 3;  // x = x % 3
x **= 2; // x = x ** 2
```

---

## Comparison Operators

```javascript
5 > 3    // true  — greater than
5 < 3    // false — less than
5 >= 5   // true  — greater than or equal
5 <= 4   // false — less than or equal
5 === 5  // true  — strict equality (same value AND type)
5 !== 3  // true  — strict inequality
5 == '5' // true  — loose equality (avoid)
5 != '3' // true  — loose inequality (avoid)
```

---

## Logical Operators

```javascript
// AND — both must be true
true && true   // true
true && false  // false

// OR — at least one must be true
true || false  // true
false || false // false

// NOT — inverts
!true   // false
!false  // true
!!value // converts to boolean

// Short-circuit evaluation
false && expensiveFunction() // expensiveFunction never called
true  || expensiveFunction() // expensiveFunction never called

// Practical patterns
const name = user.name || 'Anonymous'; // fallback
const isAdmin = user && user.isAdmin;  // safe access
```

---

## Operator Precedence

Higher precedence runs first (like PEMDAS in math):

```javascript
2 + 3 * 4    // 14 (not 20) — * before +
(2 + 3) * 4  // 20 — parentheses first
!true || false // false — ! before ||
```

---

## Common Mistakes

- Using `=` (assignment) instead of `===` (comparison) in conditions
- Forgetting operator precedence — use parentheses when unsure
- Using `==` instead of `===`
- Post vs pre increment: `x++` vs `++x` in expressions
