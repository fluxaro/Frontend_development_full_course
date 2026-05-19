# 35 — Map, Set, WeakMap, WeakSet

## What Is This Lesson About?

Map and Set are modern data structures that solve specific problems better than plain objects and arrays.

---

## Map

A Map stores key-value pairs where keys can be any type (not just strings):

```javascript
const map = new Map();

map.set('name', 'Alex');
map.set(42, 'the answer');
map.set(true, 'boolean key');
map.set({ id: 1 }, 'object key');

map.get('name');    // 'Alex'
map.has('name');    // true
map.delete('name'); // true
map.size;           // 3

// Iterate
for (const [key, value] of map) {
  console.log(key, value);
}

map.keys();   // iterator of keys
map.values(); // iterator of values
map.entries(); // iterator of [key, value] pairs
```

### Map vs Object

| | Map | Object |
|---|---|---|
| Key types | Any | String/Symbol |
| Order | Insertion order | Not guaranteed |
| Size | `.size` | `Object.keys().length` |
| Iteration | Built-in | Need Object.entries() |

---

## Set

A Set stores unique values — duplicates are automatically removed:

```javascript
const set = new Set([1, 2, 3, 2, 1]); // {1, 2, 3}

set.add(4);
set.has(3);    // true
set.delete(2);
set.size;      // 3

// Remove duplicates from array
const unique = [...new Set([1, 2, 2, 3, 3, 4])]; // [1, 2, 3, 4]

// Set operations
const a = new Set([1, 2, 3]);
const b = new Set([2, 3, 4]);
const union = new Set([...a, ...b]);        // {1,2,3,4}
const intersection = new Set([...a].filter(x => b.has(x))); // {2,3}
```

---

## WeakMap and WeakSet

Like Map/Set but keys must be objects and are held weakly (garbage collected when no other references exist):

```javascript
const cache = new WeakMap();
const user = { id: 1 };
cache.set(user, { data: 'cached' });
// When user is garbage collected, cache entry is too
```

Use WeakMap for caching data associated with objects without preventing garbage collection.

---

## Common Mistakes

- Using an object as a Map key and expecting it to match another object with the same content (Map uses reference equality)
- Forgetting that Set doesn't have index access — convert to array first
- Using WeakMap/WeakSet when you need to iterate (they're not iterable)
