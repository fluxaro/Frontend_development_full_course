# Assignment — Immutable State Manager

## What You Are Building

A state manager that uses spread and rest operators to update state immutably — the same pattern used in React and Redux.

---

## Requirements

Create `state-manager.html` with:

### Initial State

```javascript
let state = {
  user: {
    name: 'Alex Rivera',
    email: 'alex@example.com',
    preferences: {
      theme: 'light',
      language: 'en',
      notifications: true,
    },
  },
  cart: [
    { id: 1, name: 'Laptop', price: 1299, qty: 1 },
    { id: 2, name: 'Mouse', price: 29, qty: 2 },
  ],
  ui: {
    sidebarOpen: false,
    activeTab: 'home',
    loading: false,
  },
};
```

### Part 1 — State Updates (spread)

Write these update functions that return a **new state** (never mutate):

```javascript
function updateUserName(state, newName) { ... }
function updateTheme(state, theme) { ... }
function toggleSidebar(state) { ... }
function setActiveTab(state, tab) { ... }
```

Each function must use spread to create a new state object.

### Part 2 — Cart Operations (spread + rest)

Write these cart functions:

```javascript
function addToCart(state, item) { ... }      // add item to cart
function removeFromCart(state, id) { ... }   // remove by id
function updateQty(state, id, qty) { ... }   // update quantity
function clearCart(state) { ... }            // empty the cart
```

### Part 3 — History

Keep a history of all state changes:
- Each update pushes the new state to a `history` array
- A "Undo" button restores the previous state
- Show the history log with timestamps

### Part 4 — State Display

Show the current state in a formatted display that updates after every change.

### Part 5 — Spread Demos

Show these spread operations visually:
- Merging two arrays
- Removing duplicates with `Set`
- Merging two objects with conflict resolution
- Shallow vs deep copy comparison

---

## What Good Looks Like

- State is never mutated — every update returns a new object
- Cart operations work correctly (add, remove, update qty)
- Undo works correctly
- Spread demos are clearly labelled

---

## Submission

Submit `state-manager.html`.
