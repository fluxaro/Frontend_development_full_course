# 33 — ES6 Modules: import and export

## What Is This Lesson About?

ES6 modules let you split your code into separate files and share functionality between them using `export` and `import`.

---

## Named Exports

```javascript
// utils.js
export function add(a, b) { return a + b; }
export function subtract(a, b) { return a - b; }
export const PI = 3.14159;

// Or export at the bottom
function multiply(a, b) { return a * b; }
export { multiply };
```

```javascript
// main.js
import { add, subtract, PI } from './utils.js';
import { multiply as mult } from './utils.js'; // rename
import * as utils from './utils.js'; // import all
```

---

## Default Export

Each module can have one default export:

```javascript
// user.js
export default class User {
  constructor(name) { this.name = name; }
}

// Or
export default function greet(name) {
  return `Hello, ${name}!`;
}
```

```javascript
// main.js
import User from './user.js';       // any name works
import greet from './user.js';      // any name works
```

---

## Named + Default

```javascript
// api.js
export default async function fetchUser(id) { ... }
export const BASE_URL = 'https://api.example.com';
export function handleError(err) { ... }
```

```javascript
import fetchUser, { BASE_URL, handleError } from './api.js';
```

---

## Using Modules in HTML

```html
<script type="module" src="main.js"></script>
```

Modules are automatically deferred and use strict mode.

---

## Re-exporting

```javascript
// index.js — barrel file
export { add, subtract } from './math.js';
export { User } from './user.js';
export { default as fetchUser } from './api.js';
```

---

## Common Mistakes

- Forgetting `type="module"` on the script tag
- Using `./` prefix for relative imports (required in browsers)
- Mixing default and named imports incorrectly
- Circular imports (A imports B, B imports A) — can cause issues
