# Class Work — Nullish and Optional Chaining

## What You Will Build

Practice using `?.` and `??` to safely access nested data.

**Time:** 25 minutes  
**Output:** `nullish-practice.html`

---

## Step 1 — Setup

```html
<!DOCTYPE html>
<html lang="en">
<head><meta charset="UTF-8"><title>Nullish Practice</title></head>
<body>
  <h1>Nullish Coalescing & Optional Chaining</h1>
  <script>
    // code here
  </script>
</body>
</html>
```

---

## Step 2 — ?? vs ||

```javascript
console.group('?? vs ||');
const values = [0, '', false, null, undefined];
values.forEach(v => {
  console.log(`${JSON.stringify(v)} || 'default' =`, v || 'default');
  console.log(`${JSON.stringify(v)} ?? 'default' =`, v ?? 'default');
  console.log('---');
});
console.groupEnd();
```

---

## Step 3 — Optional Chaining

```javascript
const users = [
  { name: 'Alex', address: { city: 'Lagos' } },
  { name: 'Sam', address: null },
  null,
];

users.forEach((user, i) => {
  const city = user?.address?.city ?? 'Unknown';
  const name = user?.name ?? 'Anonymous';
  console.log(`User ${i}: ${name} from ${city}`);
});
```

---

## Checklist

- [ ] `0 ?? 'default'` returns `0`
- [ ] `0 || 'default'` returns `'default'`
- [ ] `null?.prop` returns `undefined` (no error)
- [ ] Chained `?.` works on deeply nested objects
