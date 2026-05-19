# 04 — Type Conversion and Coercion

## What Is This Lesson About?

JavaScript automatically converts values between types in certain situations (coercion), and you can also convert types explicitly. Understanding the difference prevents subtle bugs.

---

## Explicit Conversion

You control the conversion:

```javascript
// To Number
Number('42')        // 42
Number('3.14')      // 3.14
Number('')          // 0
Number('abc')       // NaN
Number(true)        // 1
Number(false)       // 0
Number(null)        // 0
Number(undefined)   // NaN
parseInt('42px')    // 42
parseFloat('3.14x') // 3.14

// To String
String(42)          // '42'
String(true)        // 'true'
String(null)        // 'null'
(42).toString()     // '42'
(255).toString(16)  // 'ff' (hex)

// To Boolean
Boolean(0)          // false
Boolean('')         // false
Boolean(null)       // false
Boolean(1)          // true
Boolean('hello')    // true
Boolean([])         // true
```

---

## Implicit Coercion

JavaScript converts automatically — often unexpectedly:

```javascript
// + with a string = string concatenation
'5' + 3         // '53' (not 8!)
'5' + true      // '5true'
'5' + null      // '5null'

// Other operators convert to number
'5' - 3         // 2
'5' * 2         // 10
'5' / 2         // 2.5
'5' - '3'       // 2

// Comparison coercion
'5' == 5        // true (loose — coerces)
'5' === 5       // false (strict — no coercion)
null == undefined // true
null === undefined // false
```

---

## Always Use Strict Equality

```javascript
// ❌ Loose equality — unpredictable
0 == false      // true
'' == false     // true
null == 0       // false (!)
null == ''      // false (!)

// ✅ Strict equality — predictable
0 === false     // false
'' === false    // false
```

---

## Common Mistakes

- Using `+` to add a number to a string (use `Number()` first)
- Using `==` instead of `===`
- Expecting `Number(null)` to be `NaN` (it's `0`)
- Expecting `Number(undefined)` to be `0` (it's `NaN`)
