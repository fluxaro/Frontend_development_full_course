# Notes — Objects: Basics and Properties

## Creating Objects

```javascript
// Object literal (most common)
const user = {
  name: 'Alex',
  age: 25,
  isActive: true,
  address: {
    city: 'Lagos',
    country: 'Nigeria',
  },
};

// Shorthand properties (when variable name matches key)
const name = 'Alex';
const age = 25;
const user = { name, age }; // same as { name: name, age: age }

// Computed property names
const key = 'email';
const obj = { [key]: 'alex@example.com' }; // { email: 'alex@example.com' }

// Method shorthand
const calculator = {
  value: 0,
  add(n) { this.value += n; return this; },
  subtract(n) { this.value -= n; return this; },
  result() { return this.value; },
};
```

## Accessing Properties

```javascript
const user = { name: 'Alex', age: 25, 'full-name': 'Alex Rivera' };

// Dot notation (preferred for known keys)
user.name;    // 'Alex'
user.age;     // 25

// Bracket notation (for dynamic keys or keys with special chars)
user['age'];          // 25
user['full-name'];    // 'Alex Rivera' (can't use dot for hyphenated keys)

const key = 'name';
user[key];            // 'Alex' (dynamic key)
```

## Modifying Objects

```javascript
const user = { name: 'Alex', age: 25 };

user.age = 26;          // modify existing property
user.email = 'a@b.com'; // add new property
delete user.age;        // remove property

// Check if property exists
'name' in user;                  // true
Object.hasOwn(user, 'name');     // true (modern)
user.hasOwnProperty('name');     // true (older)
user.name !== undefined;         // true (but fragile — undefined could be a value)
```

## Nested Objects

```javascript
const user = {
  name: 'Alex',
  address: {
    city: 'Lagos',
    country: 'Nigeria',
    zip: '100001',
  },
  scores: [95, 87, 92],
};

user.address.city;      // 'Lagos'
user.address['city'];   // 'Lagos'
user.scores[0];         // 95

// Safe access with optional chaining
user?.address?.city;    // 'Lagos' (no error if address is null)
user?.phone?.number;    // undefined (no error)
```

## Iterating Over Objects

```javascript
const user = { name: 'Alex', age: 25, city: 'Lagos' };

// for-in
for (const key in user) {
  console.log(key, user[key]);
}

// Object.keys / values / entries
Object.keys(user);    // ['name', 'age', 'city']
Object.values(user);  // ['Alex', 25, 'Lagos']
Object.entries(user); // [['name','Alex'], ['age',25], ['city','Lagos']]

// Iterate entries
for (const [key, value] of Object.entries(user)) {
  console.log(`${key}: ${value}`);
}
```

## Objects Are Reference Types

```javascript
const a = { x: 1 };
const b = a;        // b points to the SAME object
b.x = 99;
console.log(a.x);   // 99 — a was also changed!

// To copy: use spread or Object.assign
const copy = { ...a };
const copy2 = Object.assign({}, a);
copy.x = 0;
console.log(a.x);   // 99 — original unchanged
```

## Common Mistakes

- Accessing a missing property returns `undefined`, not an error
- Accessing a property on `undefined` throws `TypeError`
- Objects are passed by reference — modifying a "copy" modifies the original
- `for-in` iterates inherited properties too — use `Object.hasOwn()` to filter
