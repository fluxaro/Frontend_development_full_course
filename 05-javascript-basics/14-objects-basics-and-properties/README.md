# 14 — Objects: Basics and Properties

## What Is This Lesson About?

Objects store key-value pairs and are the foundation of JavaScript. Almost everything in JS is an object.

---

## Creating Objects

```javascript
// Object literal (most common)
const user = {
  name: 'Alex',
  age: 25,
  isActive: true,
};

// Computed property names
const key = 'name';
const obj = { [key]: 'Alex' }; // { name: 'Alex' }

// Shorthand properties
const name = 'Alex';
const age = 25;
const user = { name, age }; // { name: 'Alex', age: 25 }
```

---

## Accessing Properties

```javascript
const user = { name: 'Alex', age: 25 };

// Dot notation (preferred)
user.name; // 'Alex'

// Bracket notation (for dynamic keys)
user['age']; // 25
const key = 'name';
user[key]; // 'Alex'
```

---

## Modifying Objects

```javascript
const user = { name: 'Alex' };

user.age = 25;        // add property
user.name = 'Sam';    // modify property
delete user.age;      // remove property
```

---

## Nested Objects

```javascript
const user = {
  name: 'Alex',
  address: {
    city: 'Lagos',
    country: 'Nigeria',
  },
  scores: [95, 87, 92],
};

user.address.city;    // 'Lagos'
user.scores[0];       // 95
```

---

## Checking Properties

```javascript
'name' in user;              // true
user.hasOwnProperty('name'); // true
user.name !== undefined;     // true (but fragile)
```

---

## Iterating

```javascript
// for-in
for (const key in user) {
  console.log(key, user[key]);
}

// Object.keys / values / entries
Object.keys(user);    // ['name', 'age']
Object.values(user);  // ['Alex', 25]
Object.entries(user); // [['name','Alex'], ['age',25]]
```

---

## Common Mistakes

- Accessing a property that doesn't exist returns `undefined`, not an error
- Accessing a property on `undefined` throws a TypeError
- Objects are passed by reference — modifying a copy modifies the original
