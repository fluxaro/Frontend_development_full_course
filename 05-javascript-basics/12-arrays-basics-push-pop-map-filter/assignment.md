# Assignment — Product Catalogue

## What You Are Building

An interactive product catalogue that uses array methods to filter, sort, and display products. This demonstrates `map`, `filter`, `sort`, and other array methods in a real-world context.

---

## Requirements

Create `product-catalogue.html` with this dataset:

```javascript
const products = [
  { id: 1, name: 'Laptop Pro', price: 1299, category: 'Electronics', rating: 4.8, inStock: true },
  { id: 2, name: 'Wireless Headphones', price: 89, category: 'Electronics', rating: 4.5, inStock: true },
  { id: 3, name: 'Ergonomic Chair', price: 349, category: 'Furniture', rating: 4.7, inStock: false },
  { id: 4, name: 'Standing Desk', price: 599, category: 'Furniture', rating: 4.6, inStock: true },
  { id: 5, name: 'Mechanical Keyboard', price: 149, category: 'Electronics', rating: 4.9, inStock: true },
  { id: 6, name: 'USB-C Hub', price: 49, category: 'Electronics', rating: 4.3, inStock: true },
  { id: 7, name: 'Monitor 27"', price: 449, category: 'Electronics', rating: 4.7, inStock: false },
  { id: 8, name: 'Desk Lamp', price: 39, category: 'Furniture', rating: 4.2, inStock: true },
];
```

### Part 1 — Display All Products (map)

- Use `map` to render each product as a card
- Show: name, price, category, rating (as stars), stock status
- Out-of-stock products should be visually dimmed

### Part 2 — Filter Controls

Add filter controls that update the display in real time:
- Category dropdown (All, Electronics, Furniture)
- In-stock only checkbox
- Price range slider (min/max)
- Minimum rating filter

### Part 3 — Sort Controls

Add sort options:
- Price: Low to High
- Price: High to Low
- Rating: High to Low
- Name: A to Z

### Part 4 — Statistics Bar

Show at the top:
- Total products shown (after filtering)
- Price range of shown products
- Average rating of shown products

### Part 5 — Cart

- "Add to Cart" button on each product
- Cart shows count in a badge
- Cart panel shows items with `push`/`splice` for add/remove

---

## What Good Looks Like

- Filters and sort work together correctly
- Statistics update when filters change
- Cart correctly adds and removes items
- Out-of-stock items cannot be added to cart

---

## Submission

Submit `product-catalogue.html`.
