# Notes — Nullish Coalescing and Optional Chaining

## ?? — Nullish Coalescing

```javascript
value ?? fallback
// Returns fallback ONLY if value is null or undefined
// 0, '', false are NOT null/undefined — they pass through

null ?? 'default'      // 'default'
undefined ?? 'default' // 'default'
0 ?? 'default'         // 0
'' ?? 'default'        // ''
false ?? 'default'     // false
```

## ?. — Optional Chaining

```javascript
obj?.prop           // undefined if obj is null/undefined
obj?.method()       // undefined if obj is null/undefined
arr?.[index]        // undefined if arr is null/undefined
obj?.a?.b?.c        // chain multiple
```

## ?? vs ||

| | `??` | `||` |
|---|---|---|
| Returns fallback for | `null`, `undefined` | Any falsy value |
| Keeps `0` | ✅ | ❌ |
| Keeps `''` | ✅ | ❌ |
| Keeps `false` | ✅ | ❌ |

## Common Pattern

```javascript
const city = user?.address?.city ?? 'Unknown';
const count = data?.items?.length ?? 0;
```

## Common Mistakes

- Using `||` when `0` or `''` are valid values
- `user?.getName()` not `user.getName?.()`
