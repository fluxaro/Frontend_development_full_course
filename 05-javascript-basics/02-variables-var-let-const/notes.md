# Notes — Variables: var, let, const

## Quick Reference

| | `var` | `let` | `const` |
|---|---|---|---|
| Scope | Function | Block | Block |
| Reassign | ✅ | ✅ | ❌ |
| Redeclare | ✅ | ❌ | ❌ |
| Hoisted | ✅ (undefined) | ❌ (TDZ) | ❌ (TDZ) |
| Use today | ❌ Never | ✅ When reassigning | ✅ Default |

## Decision Rule

```
Always use const.
Switch to let only when you need to reassign.
Never use var.
```

## Naming Conventions

```javascript
const firstName = 'Alex';      // camelCase
const MAX_SIZE = 100;          // SCREAMING_SNAKE_CASE for true constants
class UserProfile {}           // PascalCase for classes
```

## const with Objects/Arrays

```javascript
const user = { name: 'Alex' };
user.name = 'Sam';  // ✅ mutation OK
user = {};          // ❌ reassignment not OK

const arr = [1, 2, 3];
arr.push(4);        // ✅ mutation OK
arr = [5, 6];       // ❌ reassignment not OK
```

## Scope

```javascript
// Block scope (let/const)
{
  let x = 10;
  const y = 20;
}
// x and y not accessible here

// Function scope (var)
function fn() {
  var z = 30;
}
// z not accessible here
```

## Common Mistakes

- Using `var` in new code
- Trying to reassign `const` — use `let` instead
- Vague names like `x`, `data`, `temp`
