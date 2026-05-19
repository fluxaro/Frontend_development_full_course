# 07 — Control Flow: if, else, switch

## What Is This Lesson About?

Control flow lets your program make decisions. `if/else` runs code conditionally based on any expression, and `switch` handles multiple specific values cleanly.

---

## if / else if / else

```javascript
const score = 75;

if (score >= 90) {
  console.log('A');
} else if (score >= 80) {
  console.log('B');
} else if (score >= 70) {
  console.log('C');
} else {
  console.log('F');
}
```

---

## Ternary Operator

A compact one-line if/else:

```javascript
const age = 20;
const status = age >= 18 ? 'Adult' : 'Minor';

// Nested ternary (use sparingly — prefer if/else for readability)
const grade = score >= 90 ? 'A' : score >= 80 ? 'B' : 'C';
```

---

## switch

Best for checking one value against many specific cases:

```javascript
const day = 'Monday';

switch (day) {
  case 'Monday':
  case 'Tuesday':
  case 'Wednesday':
  case 'Thursday':
  case 'Friday':
    console.log('Weekday');
    break;
  case 'Saturday':
  case 'Sunday':
    console.log('Weekend');
    break;
  default:
    console.log('Unknown day');
}
```

**Always include `break`** — without it, execution falls through to the next case.

---

## When to Use Each

| Situation | Use |
|---|---|
| One condition | `if` |
| 2–4 conditions with ranges | `if/else if/else` |
| Many specific values | `switch` |
| Simple inline | ternary `?:` |

---

## Common Mistakes

- Forgetting `break` in switch (causes fall-through bugs)
- Using `switch` with ranges (use `if/else` instead)
- Deeply nested ternaries — use `if/else` for readability
- Using `=` (assignment) instead of `===` (comparison) in conditions
