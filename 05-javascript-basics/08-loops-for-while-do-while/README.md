# 08 — Loops: for, while, do-while

## What Is This Lesson About?

Loops repeat a block of code. JavaScript has three main loop types: `for` (when you know the count), `while` (when you don't), and `do-while` (runs at least once).

---

## for Loop

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i); // 0, 1, 2, 3, 4
}

// Count down
for (let i = 10; i >= 0; i--) {
  console.log(i);
}

// Step by 2
for (let i = 0; i <= 10; i += 2) {
  console.log(i); // 0, 2, 4, 6, 8, 10
}
```

---

## while Loop

```javascript
let count = 0;
while (count < 5) {
  console.log(count);
  count++;
}
```

---

## do-while Loop

Runs the body at least once before checking the condition:

```javascript
let attempts = 0;
do {
  attempts++;
  console.log('Attempt', attempts);
} while (attempts < 3);
```

---

## break and continue

```javascript
// break — exit the loop entirely
for (let i = 0; i < 10; i++) {
  if (i === 5) break;
  console.log(i); // 0, 1, 2, 3, 4
}

// continue — skip to next iteration
for (let i = 0; i < 10; i++) {
  if (i % 2 === 0) continue;
  console.log(i); // 1, 3, 5, 7, 9
}
```

---

## When to Use Each

| Loop | Use when |
|---|---|
| `for` | You know the number of iterations |
| `while` | You don't know when it will end |
| `do-while` | Must run at least once |

---

## Common Mistakes

- Infinite loops: forgetting to increment the counter
- Off-by-one errors: `< length` vs `<= length`
- Using `while` when `for` is clearer (and vice versa)
