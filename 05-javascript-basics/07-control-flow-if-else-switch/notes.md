# Notes — Control Flow: if, else, switch

## if / else if / else

```javascript
if (condition) {
  // runs if condition is true
} else if (anotherCondition) {
  // runs if first is false and this is true
} else {
  // runs if all above are false
}
```

## Ternary Operator

```javascript
const result = condition ? valueIfTrue : valueIfFalse;

// Example
const label = age >= 18 ? 'Adult' : 'Minor';

// Nested (use sparingly)
const grade = score >= 90 ? 'A' : score >= 80 ? 'B' : 'C';
```

## switch

```javascript
switch (value) {
  case 'a':
    // runs if value === 'a'
    break;
  case 'b':
  case 'c':
    // runs if value === 'b' OR 'c' (fall-through)
    break;
  default:
    // runs if no case matches
}
```

## When to Use Each

| Situation | Use |
|---|---|
| One condition | `if` |
| 2–4 conditions with ranges | `if / else if / else` |
| Many specific values | `switch` |
| Simple inline | ternary `?:` |

## Grade Example

```javascript
function getGrade(score) {
  if (score >= 90) return 'A';
  if (score >= 80) return 'B';
  if (score >= 70) return 'C';
  if (score >= 60) return 'D';
  return 'F';
}
```

## Day Type Example

```javascript
function getDayType(day) {
  switch (day.toLowerCase()) {
    case 'monday':
    case 'tuesday':
    case 'wednesday':
    case 'thursday':
    case 'friday':
      return 'Weekday';
    case 'saturday':
    case 'sunday':
      return 'Weekend';
    default:
      return 'Invalid';
  }
}
```

## Common Mistakes

- Forgetting `break` in switch — execution falls through to the next case
- Using `switch` for ranges (use `if/else` instead — switch uses `===`)
- Using `=` (assignment) instead of `===` (comparison) in conditions
- Deeply nested ternaries — use `if/else` when it gets complex
