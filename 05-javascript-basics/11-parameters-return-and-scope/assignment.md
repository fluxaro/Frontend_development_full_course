# Assignment — Shopping Cart Functions

## What You Are Building

A shopping cart system built entirely with functions, demonstrating parameters, return values, default parameters, rest parameters, and scope.

---

## Requirements

Create `shopping-cart.html` with:

### Core Functions

Write these functions with proper parameters and return values:

```javascript
// Add item to cart — returns new cart (don't mutate original)
function addItem(cart, { name, price, quantity = 1 }) { ... }

// Remove item by name — returns new cart
function removeItem(cart, name) { ... }

// Update quantity — returns new cart
function updateQuantity(cart, name, quantity) { ... }

// Calculate subtotal — returns number
function getSubtotal(cart) { ... }

// Apply discount — returns discounted total
function applyDiscount(subtotal, { code, percent }) { ... }

// Calculate tax — returns tax amount
function calculateTax(subtotal, taxRate = 0.075) { ... }

// Get order summary — returns object with all totals
function getOrderSummary(cart, discountCode = null) { ... }
```

### Discount Codes

Define these discount codes:
- `SAVE10` → 10% off
- `SAVE20` → 20% off
- `HALFOFF` → 50% off

### UI

Build a page that:
- Shows a list of available products (at least 5)
- Has "Add to Cart" buttons for each product
- Shows the cart with quantities and a remove button
- Shows the order summary: subtotal, discount, tax, total
- Has a discount code input field

### Scope Demonstration

Add a section that shows:
- A variable defined in global scope
- A variable defined inside a function (not accessible outside)
- A closure that remembers a value

---

## What Good Looks Like

- Cart functions never mutate the original array — they return new arrays
- Default parameters are used for `quantity` and `taxRate`
- The order summary updates in real time when items are added/removed
- Discount codes work correctly

---

## Submission

Submit `shopping-cart.html`.
