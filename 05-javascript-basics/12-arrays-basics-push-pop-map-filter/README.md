# 12 — Arrays: Basics, push, pop, map, filter

## What Is This Lesson About?

Arrays store ordered lists of values. JavaScript arrays are dynamic and have powerful built-in methods for adding, removing, and transforming data.

---

## Creating Arrays

```javascript
const empty = [];
const numbers = [1, 2, 3, 4, 5];
const mixed = [1, 'hello', true, null, { name: 'Alex' }];
const fromRange = Array.from({ length: 5 }, (_, i) => i + 1); // [1,2,3,4,5]
```

---

## Accessing and Modifying

```javascript
const arr = ['a', 'b', 'c'];
arr[0];        // 'a'
arr[arr.length - 1]; // 'c' (last element)
arr.at(-1);    // 'c' (modern — negative index)
arr[1] = 'B';  // modify: ['a', 'B', 'c']
```

---

## Adding and Removing

```javascript
const arr = [1, 2, 3];

arr.push(4);      // add to end → [1,2,3,4]
arr.pop();        // remove from end → [1,2,3]
arr.unshift(0);   // add to start → [0,1,2,3]
arr.shift();      // remove from start → [1,2,3]
arr.splice(1, 1); // remove 1 element at index 1 → [1,3]
arr.splice(1, 0, 'a', 'b'); // insert at index 1
```

---

## map — Transform Every Element

Returns a **new array** with each element transformed:

```javascript
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(n => n * 2); // [2, 4, 6, 8, 10]
const strings = numbers.map(n => `Item ${n}`); // ['Item 1', ...]

const users = [{ name: 'Alex' }, { name: 'Sam' }];
const names = users.map(u => u.name); // ['Alex', 'Sam']
```

---

## filter — Keep Matching Elements

Returns a **new array** with only elements that pass the test:

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evens = numbers.filter(n => n % 2 === 0); // [2, 4, 6]
const odds  = numbers.filter(n => n % 2 !== 0); // [1, 3, 5]

const users = [
  { name: 'Alex', active: true },
  { name: 'Sam', active: false },
];
const activeUsers = users.filter(u => u.active); // [{ name: 'Alex', ... }]
```

---

## Other Essential Methods

```javascript
arr.includes(value)    // true/false
arr.indexOf(value)     // index or -1
arr.find(fn)           // first matching element
arr.findIndex(fn)      // index of first match
arr.slice(start, end)  // copy portion (non-destructive)
arr.concat(arr2)       // merge arrays
arr.join(separator)    // array to string
arr.reverse()          // reverse in place
arr.sort()             // sort in place
arr.flat()             // flatten nested arrays
arr.length             // number of elements
```

---

## Common Mistakes

- `map` and `filter` return new arrays — the original is unchanged
- `sort()` sorts as strings by default: `[10, 9, 2].sort()` → `[10, 2, 9]`
- `splice` modifies the original array; `slice` does not
- Forgetting that array indices start at 0
