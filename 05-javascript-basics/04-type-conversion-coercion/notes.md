# Notes — Type Conversion and Coercion

## Explicit Conversion

```javascript
Number('42')      // 42
Number('')        // 0
Number('abc')     // NaN
Number(true)      // 1
Number(null)      // 0
Number(undefined) // NaN

String(42)        // '42'
String(null)      // 'null'

Boolean(0)        // false
Boolean('')       // false
Boolean([])       // true (!)
```

## Implicit Coercion Traps

```javascript
'5' + 3    // '53' (string concat)
'5' - 3    // 2 (numeric)
'5' == 5   // true (loose)
'5' === 5  // false (strict)
null == undefined  // true
null === undefined // false
```

## Rule: Always Use ===

```javascript
// ❌ Avoid
if (x == null) {}

// ✅ Use
if (x === null || x === undefined) {}
// or
if (x == null) {} // only acceptable null/undefined check
```

## Common Mistakes

- `'5' + 3` gives `'53'` not `8`
- `Number(null)` is `0`, not `NaN`
- `Number(undefined)` is `NaN`, not `0`
- Using `==` instead of `===`
