# Assignment — Sales Dashboard

## What You Are Building

A sales dashboard that uses `reduce`, `find`, `some`, and `every` to analyse a dataset of sales transactions and display meaningful statistics.

---

## Requirements

Create `sales-dashboard.html` with this dataset:

```javascript
const sales = [
  { id: 1, product: 'Laptop', amount: 1299, region: 'North', rep: 'Alex', month: 'Jan' },
  { id: 2, product: 'Phone', amount: 699, region: 'South', rep: 'Sam', month: 'Jan' },
  { id: 3, product: 'Tablet', amount: 449, region: 'North', rep: 'Alex', month: 'Feb' },
  { id: 4, product: 'Laptop', amount: 1299, region: 'East', rep: 'Jordan', month: 'Feb' },
  { id: 5, product: 'Headphones', amount: 89, region: 'South', rep: 'Sam', month: 'Mar' },
  { id: 6, product: 'Monitor', amount: 449, region: 'West', rep: 'Morgan', month: 'Mar' },
  { id: 7, product: 'Keyboard', amount: 149, region: 'North', rep: 'Alex', month: 'Mar' },
  { id: 8, product: 'Phone', amount: 699, region: 'East', rep: 'Jordan', month: 'Apr' },
  { id: 9, product: 'Laptop', amount: 1299, region: 'West', rep: 'Morgan', month: 'Apr' },
  { id: 10, product: 'Tablet', amount: 449, region: 'South', rep: 'Sam', month: 'Apr' },
];
```

### Part 1 — Summary Statistics (reduce)

Use `reduce` to calculate:
- Total revenue across all sales
- Revenue by region (object: `{ North: 1997, South: ... }`)
- Revenue by sales rep
- Revenue by product
- Revenue by month

Display each as a bar chart (use CSS width percentages).

### Part 2 — Search and Find (find, findIndex)

- A search input for sale ID
- Use `find` to locate the sale and display its details
- Show "Not found" if the ID doesn't exist

### Part 3 — Validation (some, every)

Display answers to these questions using `some` and `every`:
- Does any sale exceed $1000?
- Does every sale have a region assigned?
- Does any rep have more than 2 sales?
- Are all sales from 2024?

### Part 4 — Top Performers (reduce + sort)

Use `reduce` to group sales by rep, then calculate each rep's:
- Total sales count
- Total revenue
- Average sale amount

Display as a leaderboard sorted by total revenue.

---

## What Good Looks Like

- All statistics are accurate
- Bar charts are proportional to the values
- Search works correctly for valid and invalid IDs
- `some`/`every` questions show clear yes/no answers with the reasoning

---

## Submission

Submit `sales-dashboard.html`.
