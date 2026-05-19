# Notes — Loops: for, while, do-while

## for Loop

```javascript
// Syntax
for (initialisation; condition; update) {
  // body
}

// Count up
for (let i = 0; i < 5; i++) {
  console.log(i); // 0, 1, 2, 3, 4
}

// Count down
for (let i = 10; i >= 0; i--) {
  console.log(i); // 10, 9, 8 ... 0
}

// Step by 2
for (let i = 0; i <= 10; i += 2) {
  console.log(i); // 0, 2, 4, 6, 8, 10
}

// Loop over array by index
for (let i = 0; i < arr.length; i++) {
  console.log(arr[i]);
}
```

## while Loop

```javascript
// Syntax
while (condition) {
  // body — must eventually make condition false
}

// Example
let count = 0;
while (count < 5) {
  console.log(count);
  count++; // ← must update or infinite loop!
}
```

## do-while Loop

```javascript
// Runs body FIRST, then checks condition
do {
  // body runs at least once
} while (condition);

// Example: roll dice until you get 6
let roll;
do {
  roll = Math.floor(Math.random() * 6) + 1;
  console.log('Rolled:', roll);
} while (roll !== 6);
```

## break and continue

```javascript
// break — exit the loop entirely
for (let i = 0; i < 10; i++) {
  if (i === 5) break;
  console.log(i); // 0, 1, 2, 3, 4
}

// continue — skip this iteration, go to next
for (let i = 0; i < 10; i++) {
  if (i % 2 === 0) continue; // skip even numbers
  console.log(i); // 1, 3, 5, 7, 9
}
```

## When to Use Each

| Loop | Use when |
|---|---|
| `for` | You know the number of iterations |
| `while` | You don't know when it will end |
| `do-while` | Must run at least once |

## FizzBuzz Pattern

```javascript
for (let i = 1; i <= 100; i++) {
  if (i % 15 === 0) console.log('FizzBuzz');
  else if (i % 3 === 0) console.log('Fizz');
  else if (i % 5 === 0) console.log('Buzz');
  else console.log(i);
}
```

## Common Mistakes

- Infinite loop: forgetting to increment the counter (`i++`)
- Off-by-one: `< length` vs `<= length` (use `<` for zero-indexed arrays)
- Using `while` when `for` is clearer
- Modifying the array you're looping over (use a copy)
