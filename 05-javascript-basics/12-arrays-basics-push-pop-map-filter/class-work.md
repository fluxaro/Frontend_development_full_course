# Class Work — Array Methods in Practice

## What You Will Build

An interactive page that demonstrates `push`, `pop`, `map`, `filter`, and other array methods with a live todo list and a data transformation demo.

**Time:** 35 minutes  
**Output:** `arrays-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Arrays Practice</title>
  <style>
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .form-row { display: flex; gap: 0.75rem; align-items: center; margin-bottom: 1rem; flex-wrap: wrap; }
    input[type="text"] { flex: 1; min-width: 200px; padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; }
    input:focus { border-color: #3498db; }
    button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; }
    button:hover { background: #2980b9; }
    button.danger { background: #e74c3c; }
    button.danger:hover { background: #c0392b; }
    .todo-item { display: flex; align-items: center; gap: 0.75rem; background: white; border: 1px solid #dee2e6; border-radius: 6px; padding: 0.75rem 1rem; margin-bottom: 0.5rem; }
    .todo-item.done { opacity: 0.5; text-decoration: line-through; }
    .todo-text { flex: 1; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; }
    .result { font-family: monospace; font-size: 0.85rem; line-height: 1.8; }
    .tag { display: inline-block; padding: 0.2rem 0.6rem; border-radius: 999px; font-size: 0.75rem; font-weight: bold; margin: 0.1rem; }
    .tag-blue { background: #d6eaf8; color: #1a5276; }
    .tag-green { background: #d5f5e3; color: #1e8449; }
    .tag-red { background: #fadbd8; color: #922b21; }
  </style>
</head>
<body>
  <h1>Array Methods Practice</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Todo List (push, splice, filter)

Add this HTML before `<script>`:

```html
<h2>Todo List (push, splice, filter)</h2>
<div class="form-row">
  <input type="text" id="todo-input" placeholder="Add a new task...">
  <button onclick="addTodo()">Add</button>
  <button onclick="clearDone()" style="background:#27ae60">Clear Done</button>
</div>
<div id="todo-list"></div>
<p id="todo-stats" style="font-size:0.85rem;color:#888;margin-top:0.5rem"></p>
```

Add this JavaScript:

```javascript
let todos = [
  { id: 1, text: 'Learn JavaScript arrays', done: true },
  { id: 2, text: 'Build a todo app', done: false },
  { id: 3, text: 'Practice map and filter', done: false },
];
let nextId = 4;

function renderTodos() {
  const list = document.getElementById('todo-list');
  const stats = document.getElementById('todo-stats');

  list.innerHTML = todos.map(todo => `
    <div class="todo-item ${todo.done ? 'done' : ''}">
      <input type="checkbox" ${todo.done ? 'checked' : ''} onchange="toggleTodo(${todo.id})">
      <span class="todo-text">${todo.text}</span>
      <button class="danger" onclick="removeTodo(${todo.id})" style="padding:0.25rem 0.6rem;font-size:0.8rem">✕</button>
    </div>
  `).join('');

  const done = todos.filter(t => t.done).length;
  stats.textContent = `${done} of ${todos.length} tasks completed`;
}

function addTodo() {
  const input = document.getElementById('todo-input');
  const text = input.value.trim();
  if (!text) return;

  todos.push({ id: nextId++, text, done: false }); // push adds to end
  input.value = '';
  renderTodos();
}

function toggleTodo(id) {
  todos = todos.map(t => t.id === id ? { ...t, done: !t.done } : t);
  renderTodos();
}

function removeTodo(id) {
  const index = todos.findIndex(t => t.id === id);
  todos.splice(index, 1); // splice removes from array
  renderTodos();
}

function clearDone() {
  todos = todos.filter(t => !t.done); // filter keeps only undone
  renderTodos();
}

renderTodos();
```

---

## Step 3 — map and filter Demos

Add this HTML:

```html
<h2>map and filter Demos</h2>
<div class="card" id="map-filter-demo"></div>
```

Add this JavaScript:

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const words = ['hello', 'world', 'javascript', 'is', 'awesome'];

// map examples
const doubled = numbers.map(n => n * 2);
const squared = numbers.map(n => n ** 2);
const upperWords = words.map(w => w.toUpperCase());
const wordLengths = words.map(w => ({ word: w, length: w.length }));

// filter examples
const evens = numbers.filter(n => n % 2 === 0);
const longWords = words.filter(w => w.length > 4);
const bigNumbers = numbers.filter(n => n > 5);

// chaining
const evenSquares = numbers
  .filter(n => n % 2 === 0)
  .map(n => n ** 2);

document.getElementById('map-filter-demo').innerHTML = `
  <div class="result">
    <strong>map:</strong><br>
    doubled: [${doubled}]<br>
    squared: [${squared}]<br>
    upperWords: [${upperWords}]<br>
    <br>
    <strong>filter:</strong><br>
    evens: [${evens}]<br>
    longWords: [${longWords}]<br>
    bigNumbers: [${bigNumbers}]<br>
    <br>
    <strong>chained (filter evens, then square):</strong><br>
    evenSquares: [${evenSquares}]
  </div>
`;
```

---

## Step 4 — Sort Demo

Add this HTML:

```html
<h2>Sorting Arrays</h2>
<div class="card" id="sort-demo"></div>
```

Add this JavaScript:

```javascript
const nums = [10, 3, 25, 1, 8, 100, 42];
const names = ['Charlie', 'Alice', 'Bob', 'Diana'];

// ❌ Default sort (treats as strings)
const wrongSort = [...nums].sort();

// ✅ Numeric sort
const ascSort = [...nums].sort((a, b) => a - b);
const descSort = [...nums].sort((a, b) => b - a);

// String sort
const alphaSort = [...names].sort();
const reverseAlpha = [...names].sort().reverse();

document.getElementById('sort-demo').innerHTML = `
  <div class="result">
    Original: [${nums}]<br>
    <span style="color:#e74c3c">❌ .sort() (wrong): [${wrongSort}]</span><br>
    <span style="color:#27ae60">✅ .sort((a,b) => a-b): [${ascSort}]</span><br>
    <span style="color:#27ae60">✅ .sort((a,b) => b-a): [${descSort}]</span><br>
    <br>
    Names: [${names}]<br>
    Alphabetical: [${alphaSort}]<br>
    Reverse: [${reverseAlpha}]
  </div>
`;
```

---

## Checklist

- [ ] Todo list renders correctly on page load
- [ ] Adding a todo uses `push` and re-renders
- [ ] Removing a todo uses `splice` and re-renders
- [ ] Toggling uses `map` to create a new array (not mutate)
- [ ] "Clear Done" uses `filter` to keep only undone todos
- [ ] `map` examples show correct transformations
- [ ] `filter` examples show correct filtering
- [ ] Chaining works: filter then map
- [ ] Numeric sort uses `(a, b) => a - b` not default `.sort()`

---

## Bonus Challenges

1. Add a "Sort by" dropdown to the todo list (by date added, alphabetically)
2. Add a search input that filters todos by text using `filter` and `includes`
3. Add a "Move to Top" button that uses `splice` and `unshift` to move a todo to the top
