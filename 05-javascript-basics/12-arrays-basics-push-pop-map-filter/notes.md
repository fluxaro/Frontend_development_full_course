# Notes — Arrays: Basics, push, pop, map, filter

## Creating Arrays

```javascript
const empty = [];
const numbers = [1, 2, 3, 4, 5];
const mixed = [1, 'hello', true, null, { name: 'Alex' }];

// Array.from
const fromLength = Array.from({ length: 5 }, (_, i) => i + 1); // [1,2,3,4,5]
const fromString = Array.from('hello'); // ['h','e','l','l','o']

// Array.of
const arr = Array.of(1, 2, 3); // [1, 2, 3]
```

## Accessing Elements

```javascript
const arr = ['a', 'b', 'c', 'd'];
arr[0];           // 'a' (first)
arr[arr.length - 1]; // 'd' (last)
arr.at(-1);       // 'd' (modern — negative index)
arr.at(-2);       // 'c'
```

## Adding and Removing

```javascript
const arr = [1, 2, 3];

// End
arr.push(4, 5);   // add to end → [1,2,3,4,5], returns new length
arr.pop();        // remove from end → returns 5, arr is [1,2,3,4]

// Start
arr.unshift(0);   // add to start → [0,1,2,3,4], returns new length
arr.shift();      // remove from start → returns 0, arr is [1,2,3,4]

// Middle — splice(startIndex, deleteCount, ...itemsToInsert)
arr.splice(1, 1);         // remove 1 at index 1 → [1,3,4]
arr.splice(1, 0, 'a','b'); // insert at index 1 → [1,'a','b',3,4]
arr.splice(1, 2, 'x');    // replace 2 items with 'x'
```

## map — Transform Every Element

Returns a **new array**. Original is unchanged.

```javascript
const numbers = [1, 2, 3, 4, 5];

const doubled = numbers.map(n => n * 2);       // [2, 4, 6, 8, 10]
const strings = numbers.map(n => `Item ${n}`); // ['Item 1', ...]
const squared = numbers.map(n => n ** 2);       // [1, 4, 9, 16, 25]

// With objects
const users = [{ name: 'Alex', age: 25 }, { name: 'Sam', age: 30 }];
const names = users.map(u => u.name);           // ['Alex', 'Sam']
const older = users.map(u => ({ ...u, age: u.age + 1 })); // increment ages
```

## filter — Keep Matching Elements

Returns a **new array** with only elements that pass the test.

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const evens  = numbers.filter(n => n % 2 === 0);  // [2, 4, 6, 8, 10]
const odds   = numbers.filter(n => n % 2 !== 0);  // [1, 3, 5, 7, 9]
const big    = numbers.filter(n => n > 5);         // [6, 7, 8, 9, 10]

// With objects
const users = [
  { name: 'Alex', active: true },
  { name: 'Sam', active: false },
  { name: 'Jordan', active: true },
];
const active = users.filter(u => u.active); // [Alex, Jordan]
```

## Other Essential Methods

```javascript
arr.includes(value)       // true/false — is value in array?
arr.indexOf(value)        // index of first match, or -1
arr.lastIndexOf(value)    // index of last match, or -1
arr.find(fn)              // first element that passes test
arr.findIndex(fn)         // index of first match
arr.slice(start, end)     // copy portion (non-destructive)
arr.concat(arr2)          // merge arrays (non-destructive)
arr.join(separator)       // array to string
arr.reverse()             // reverse in place (mutates!)
arr.sort()                // sort in place (mutates!)
arr.flat(depth)           // flatten nested arrays
arr.flatMap(fn)           // map then flatten one level
arr.fill(value, start, end) // fill with value
arr.length                // number of elements
```

## Chaining

```javascript
const result = users
  .filter(u => u.active)
  .map(u => u.name.toUpperCase())
  .sort();
```

## Common Mistakes

- `map` and `filter` return **new arrays** — the original is unchanged
- `sort()` sorts as strings by default: `[10, 9, 2].sort()` → `[10, 2, 9]`
- Use `sort((a, b) => a - b)` for numeric sort
- `splice` mutates the original; `slice` does not
- `push` returns the new length, not the array
