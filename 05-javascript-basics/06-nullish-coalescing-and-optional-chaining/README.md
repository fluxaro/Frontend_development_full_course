# 06 — Nullish Coalescing and Optional Chaining

## What Is This Lesson About?

Two modern operators that make working with potentially null or undefined values much cleaner and safer.

---

## Nullish Coalescing (??)

Returns the right side only when the left side is `null` or `undefined` (not other falsy values):

```javascript
const name = null ?? 'Anonymous';     // 'Anonymous'
const age  = undefined ?? 18;         // 18
const score = 0 ?? 100;               // 0 (0 is not null/undefined!)
const text  = '' ?? 'default';        // '' (empty string is not null/undefined!)
```

### ?? vs ||

```javascript
// || returns right side for ANY falsy value
0 || 100        // 100 (0 is falsy)
'' || 'default' // 'default' ('' is falsy)

// ?? returns right side ONLY for null/undefined
0 ?? 100        // 0 (0 is not null/undefined)
'' ?? 'default' // '' ('' is not null/undefined)
```

Use `??` when `0` and `''` are valid values you want to keep.

---

## Optional Chaining (?.)

Safely access nested properties without throwing if an intermediate value is null/undefined:

```javascript
const user = null;

// Without optional chaining — throws TypeError
user.address.city; // TypeError: Cannot read properties of null

// With optional chaining — returns undefined
user?.address?.city; // undefined (no error)

// Works with methods
user?.getName?.();   // undefined (no error)

// Works with arrays
arr?.[0];            // undefined if arr is null/undefined

// Practical example
const city = user?.profile?.address?.city ?? 'Unknown';
```

---

## Combining ?? and ?.

```javascript
const user = {
  name: 'Alex',
  address: null,
};

const city = user?.address?.city ?? 'No city provided';
// user exists → address is null → city is undefined → ?? returns 'No city provided'
```

---

## Common Mistakes

- Using `||` when you want `??` (loses valid `0` and `''` values)
- Forgetting `?.` on method calls: `user?.getName()` not `user.getName?.()`
- Chaining too deeply — if something is always expected to exist, don't use `?.`
