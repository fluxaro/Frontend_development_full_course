# Class Work — Coercion Traps

## What You Will Build

A JavaScript file that demonstrates type coercion traps and how to avoid them.

**Time:** 25 minutes  
**Output:** `coercion-traps.html`

---

## Step 1 — Setup

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Coercion Traps</title>
</head>
<body>
  <h1>Type Coercion Traps</h1>
  <p>Open the console.</p>
  <script>
    // code here
  </script>
</body>
</html>
```

---

## Step 2 — The + Trap

```javascript
console.group('+ Operator Trap');
console.log('5' + 3);       // '53' — string concat!
console.log('5' + true);    // '5true'
console.log(5 + '3');       // '53'
console.log(5 + 3 + '1');   // '81' (left to right)
console.log('5' + 3 + 1);   // '531'

// Fix: convert first
console.log(Number('5') + 3); // 8
console.log(+'5' + 3);        // 8 (unary +)
console.groupEnd();
```

---

## Step 3 — == vs ===

```javascript
console.group('== vs ===');
console.log(0 == false);    // true
console.log(0 === false);   // false
console.log('' == false);   // true
console.log('' === false);  // false
console.log(null == undefined);  // true
console.log(null === undefined); // false
console.log('1' == 1);     // true
console.log('1' === 1);    // false
console.groupEnd();
```

---

## Step 4 — Explicit Conversion

```javascript
console.group('Explicit Conversion');
const inputs = ['42', '3.14', '', 'abc', null, undefined, true, false, []];
inputs.forEach(v => {
  console.log(`Number(${JSON.stringify(v)}) = ${Number(v)}`);
});
console.groupEnd();
```

---

## Checklist

- [ ] `'5' + 3` shows `'53'` (string)
- [ ] `Number('5') + 3` shows `8` (number)
- [ ] `0 == false` is `true`, `0 === false` is `false`
- [ ] `null == undefined` is `true`, `null === undefined` is `false`
- [ ] `Number(null)` is `0`, `Number(undefined)` is `NaN`
