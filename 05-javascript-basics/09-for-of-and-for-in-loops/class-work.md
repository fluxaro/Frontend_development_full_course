# Class Work — for-of and for-in in Practice

## What You Will Build

A page that uses `for-of` to process an array of products and `for-in` to inspect object properties, showing the difference between the two loop types clearly.

**Time:** 30 minutes  
**Output:** `for-loops-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>for-of and for-in Practice</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .card-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 1rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1rem; }
    .card h3 { font-size: 0.95rem; margin-bottom: 0.4rem; }
    .card p { font-size: 0.85rem; color: #666; }
    .price { font-size: 1.1rem; font-weight: bold; color: #27ae60; margin-top: 0.5rem; }
    table { border-collapse: collapse; width: 100%; max-width: 500px; background: white; border-radius: 8px; overflow: hidden; }
    th, td { padding: 0.6rem 1rem; text-align: left; border-bottom: 1px solid #dee2e6; font-size: 0.88rem; }
    th { background: #2c3e50; color: white; }
    .stat-box { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1rem; display: inline-block; margin-right: 1rem; margin-bottom: 1rem; text-align: center; }
    .stat-val { font-size: 1.5rem; font-weight: bold; color: #3498db; }
    .stat-label { font-size: 0.8rem; color: #888; margin-top: 0.25rem; }
  </style>
</head>
<body>
  <h1>for-of and for-in Practice</h1>
  <script>
    const products = [
      { name: 'Laptop', price: 999, category: 'Electronics', inStock: true },
      { name: 'Headphones', price: 79, category: 'Electronics', inStock: true },
      { name: 'Desk Chair', price: 249, category: 'Furniture', inStock: false },
      { name: 'Notebook', price: 12, category: 'Stationery', inStock: true },
      { name: 'Monitor', price: 399, category: 'Electronics', inStock: true },
      { name: 'Pen Set', price: 8, category: 'Stationery', inStock: true },
    ];
  </script>
</body>
</html>
```

---

## Step 2 — Display Products with for-of

Add this HTML before `<script>`:

```html
<h2>Product Cards (for-of)</h2>
<div class="card-grid" id="products-grid"></div>
```

Add this JavaScript inside `<script>`:

```javascript
// for-of: loop over array values
const grid = document.getElementById('products-grid');

for (const product of products) {
  const stockLabel = product.inStock ? '✅ In Stock' : '❌ Out of Stock';
  grid.innerHTML += `
    <div class="card">
      <h3>${product.name}</h3>
      <p>${product.category}</p>
      <p>${stockLabel}</p>
      <div class="price">$${product.price}</div>
    </div>
  `;
}
```

---

## Step 3 — Inspect Object with for-in

Add this HTML:

```html
<h2>Object Inspector (for-in)</h2>
<p>Inspecting the first product object:</p>
<table>
  <thead><tr><th>Property</th><th>Value</th><th>Type</th></tr></thead>
  <tbody id="inspector-body"></tbody>
</table>
```

Add this JavaScript:

```javascript
// for-in: loop over object keys
const firstProduct = products[0];
const tbody = document.getElementById('inspector-body');

for (const key in firstProduct) {
  tbody.innerHTML += `
    <tr>
      <td><strong>${key}</strong></td>
      <td>${firstProduct[key]}</td>
      <td><code>${typeof firstProduct[key]}</code></td>
    </tr>
  `;
}
```

---

## Step 4 — Statistics with for-of

Add this HTML:

```html
<h2>Statistics (for-of accumulation)</h2>
<div id="stats"></div>
```

Add this JavaScript:

```javascript
// Calculate stats using for-of
let totalPrice = 0;
let mostExpensive = products[0];
let inStockCount = 0;

for (const product of products) {
  totalPrice += product.price;

  if (product.price > mostExpensive.price) {
    mostExpensive = product;
  }

  if (product.inStock) {
    inStockCount++;
  }
}

const avgPrice = (totalPrice / products.length).toFixed(2);

document.getElementById('stats').innerHTML = `
  <div class="stat-box">
    <div class="stat-val">${products.length}</div>
    <div class="stat-label">Total Products</div>
  </div>
  <div class="stat-box">
    <div class="stat-val">$${avgPrice}</div>
    <div class="stat-label">Average Price</div>
  </div>
  <div class="stat-box">
    <div class="stat-val">${mostExpensive.name}</div>
    <div class="stat-label">Most Expensive ($${mostExpensive.price})</div>
  </div>
  <div class="stat-box">
    <div class="stat-val">${inStockCount}</div>
    <div class="stat-label">In Stock</div>
  </div>
`;
```

---

## Step 5 — for-of vs forEach (console)

Add this to your JavaScript:

```javascript
console.log('--- for-of ---');
for (const product of products) {
  console.log(product.name, '$' + product.price);
}

console.log('--- forEach ---');
products.forEach((product, index) => {
  console.log(index, product.name, '$' + product.price);
});

// Key difference: for-of supports break, forEach does not
console.log('--- for-of with break ---');
for (const product of products) {
  if (product.price > 300) {
    console.log('First expensive product:', product.name);
    break; // ← this works in for-of
  }
}
```

---

## Checklist

- [ ] Product cards display all 6 products using `for-of`
- [ ] Object inspector shows all properties of the first product using `for-in`
- [ ] Statistics are calculated correctly using `for-of`
- [ ] Console shows the difference between `for-of` and `forEach`
- [ ] `break` works inside `for-of` but not `forEach`

---

## Bonus Challenges

1. Use `for-of` with `entries()` to show the product index on each card
2. Use `for-in` to count how many properties each product has
3. Group products by category using `for-of` and display each group separately
