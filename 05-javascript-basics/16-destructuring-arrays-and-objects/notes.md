# Notes — Destructuring Arrays and Objects

## Object Destructuring

```javascript
const user = { name: 'Alex', age: 25, city: 'Lagos', role: 'admin' };

// Basic — extract into variables with same names
const { name, age } = user;
console.log(name, age); // 'Alex' 25

// Rename — extract and give a different variable name
const { name: userName, age: userAge } = user;
console.log(userName); // 'Alex'

// Default values — used when property is undefined
const { name, role = 'user', country = 'Unknown' } = user;
console.log(role);    // 'admin' (exists in object)
console.log(country); // 'Unknown' (not in object, uses default)

// Nested destructuring
const { address: { city, zip } } = { address: { city: 'Lagos', zip: '100001' } };
console.log(city); // 'Lagos'

// Rest — collect remaining properties
const { name, ...rest } = user;
console.log(rest); // { age: 25, city: 'Lagos', role: 'admin' }

// In function parameters
function displayUser({ name, age, role = 'user' }) {
  return `${name} (${age}) — ${role}`;
}
displayUser(user);
```

## Array Destructuring

```javascript
const [first, second, third] = [1, 2, 3];
console.log(first, second, third); // 1 2 3

// Skip elements with commas
const [, second, , fourth] = [1, 2, 3, 4];
console.log(second, fourth); // 2 4

// Rest — collect remaining elements
const [head, ...tail] = [1, 2, 3, 4, 5];
console.log(head); // 1
console.log(tail); // [2, 3, 4, 5]

// Default values
const [a = 0, b = 0, c = 0] = [1, 2];
console.log(a, b, c); // 1 2 0

// Swap variables (no temp variable needed!)
let x = 1, y = 2;
[x, y] = [y, x];
console.log(x, y); // 2 1

// From function return
function getCoords() { return [40.7128, -74.0060]; }
const [lat, lng] = getCoords();
```

## Destructuring in Loops

```javascript
const users = [
  { name: 'Alex', age: 25 },
  { name: 'Sam', age: 30 },
];

// Destructure in for-of
for (const { name, age } of users) {
  console.log(`${name} is ${age}`);
}

// Destructure Object.entries
const scores = { math: 90, english: 85 };
for (const [subject, score] of Object.entries(scores)) {
  console.log(`${subject}: ${score}`);
}
```

## Practical Patterns

```javascript
// API response destructuring
const { data: { users, total }, status } = await fetchUsers();

// React useState
const [count, setCount] = useState(0);

// React useReducer
const [state, dispatch] = useReducer(reducer, initialState);

// Promise.all
const [user, posts, comments] = await Promise.all([
  fetchUser(id),
  fetchPosts(id),
  fetchComments(id),
]);
```

## Common Mistakes

- Destructuring a property that doesn't exist gives `undefined` (not an error)
- Forgetting `{}` around object destructuring in function parameters
- Nested destructuring can get hard to read — use intermediate variables
- Array destructuring order matters — object destructuring uses names
