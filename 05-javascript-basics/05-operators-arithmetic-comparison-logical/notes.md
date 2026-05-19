# Notes — Operators

## Arithmetic

```javascript
+  -  *  /  %  **
x++  x--  ++x  --x
x += 5  x -= 3  x *= 2  x /= 4  x %= 3
```

## Comparison (always use ===)

```javascript
===  !==   // strict (use these)
==   !=    // loose (avoid)
>  <  >=  <=
```

## Logical

```javascript
&&   // AND — both true
||   // OR — at least one true
!    // NOT — invert
!!   // double NOT — convert to boolean
```

## Short-Circuit Patterns

```javascript
// Fallback value
const name = input || 'Anonymous';

// Safe property access
const city = user && user.address && user.address.city;

// Default with ??
const count = value ?? 0; // only if null/undefined
```

## Precedence (high to low)

```
()  →  **  →  !  →  * / %  →  + -  →  > < >= <=  →  === !==  →  &&  →  ||
```

## Common Mistakes

- `=` vs `===` in conditions
- `||` returns the first truthy value, not `true`/`false`
- `&&` returns the first falsy value, not `true`/`false`
