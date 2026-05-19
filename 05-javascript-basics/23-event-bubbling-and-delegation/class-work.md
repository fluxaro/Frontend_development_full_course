# Class Work — Event Bubbling and Delegation

## What You Will Build

A page that demonstrates event bubbling with a visual propagation path, and event delegation with a dynamic todo list that handles all interactions with one listener.

**Time:** 35 minutes  
**Output:** `bubbling-delegation-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bubbling and Delegation</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; margin-bottom: 1rem; }

    /* Bubbling demo */
    .outer { background: #fadbd8; border: 3px solid #e74c3c; border-radius: 8px; padding: 2rem; cursor: pointer; }
    .middle { background: #fdebd0; border: 3px solid #e67e22; border-radius: 6px; padding: 1.5rem; }
    .inner { background: #d5f5e3; border: 3px solid #27ae60; border-radius: 4px; padding: 1rem; text-align: center; font-weight: bold; }
    .outer.fired { border-color: #c0392b; background: #f1948a; }
    .middle.fired { border-color: #d35400; background: #f0b27a; }
    .inner.fired { border-color: #1e8449; background: #82e0aa; }
    .log { background: #1e293b; color: #e2e8f0; border-radius: 6px; padding: 0.75rem; font-family: monospace; font-size: 0.82rem; line-height: 1.8; max-height: 120px; overflow-y: auto; margin-top: 0.75rem; }

    /* Todo list */
    .todo-input-row { display: flex; gap: 0.75rem; margin-bottom: 1rem; }
    .todo-input-row input { flex: 1; padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; }
    .todo-input-row input:focus { border-color: #3498db; }
    .todo-input-row button { padding: 0.5rem 1.25rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.9rem; }
    .todo-input-row button:hover { background: #2980b9; }
    #todo-list { list-style: none; }
    .todo-item { display: flex; align-items: center; gap: 0.75rem; padding: 0.75rem 1rem; border-bottom: 1px solid #f0f0f0; transition: background 0.15s; }
    .todo-item:hover { background: #f8f9fa; }
    .todo-item.done .todo-text { text-decoration: line-through; opacity: 0.5; }
    .todo-text { flex: 1; font-size: 0.9rem; }
    .todo-item button { padding: 0.25rem 0.6rem; border: none; border-radius: 4px; cursor: pointer; font-size: 0.8rem; }
    .complete-btn { background: #d5f5e3; color: #1e8449; }
    .delete-btn { background: #fadbd8; color: #922b21; }
    .todo-count { font-size: 0.85rem; color: #888; margin-top: 0.5rem; }
  </style>
</head>
<body>
  <h1>Event Bubbling and Delegation</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Bubbling Visualiser

Add this HTML before `<script>`:

```html
<h2>Event Bubbling</h2>
<div class="card">
  <p style="margin-bottom:1rem;font-size:0.9rem">Click the inner green box. Watch the event bubble up through all three boxes.</p>
  <div class="outer" id="outer">
    Outer (red)
    <div class="middle" id="middle">
      Middle (orange)
      <div class="inner" id="inner">
        Click Me! (inner green)
      </div>
    </div>
  </div>
  <div class="log" id="bubble-log">Click the inner box to see bubbling...</div>
</div>
```

Add this JavaScript:

```javascript
const bubbleLog = document.getElementById('bubble-log');
let bubbleEntries = [];

function addBubbleLog(msg) {
  bubbleEntries.unshift(msg);
  if (bubbleEntries.length > 8) bubbleEntries.pop();
  bubbleLog.innerHTML = bubbleEntries.map(e => `<div>${e}</div>`).join('');
}

function flashElement(id) {
  const el = document.getElementById(id);
  el.classList.add('fired');
  setTimeout(() => el.classList.remove('fired'), 600);
}

document.getElementById('inner').addEventListener('click', (e) => {
  flashElement('inner');
  addBubbleLog('1. inner fired (target)');
});

document.getElementById('middle').addEventListener('click', (e) => {
  flashElement('middle');
  addBubbleLog('2. middle fired (bubbled up)');
});

document.getElementById('outer').addEventListener('click', (e) => {
  flashElement('outer');
  addBubbleLog('3. outer fired (bubbled up)');
  addBubbleLog('--- click complete ---');
});
```

---

## Step 3 — Dynamic Todo List with Delegation

Add this HTML:

```html
<h2>Event Delegation — One Listener for All Todos</h2>
<div class="card">
  <div class="todo-input-row">
    <input type="text" id="todo-input" placeholder="Add a new task...">
    <button onclick="addTodo()">Add</button>
  </div>
  <ul id="todo-list"></ul>
  <p class="todo-count" id="todo-count"></p>
</div>
```

Add this JavaScript:

```javascript
let todos = [
  { id: 1, text: 'Learn event bubbling', done: true },
  { id: 2, text: 'Practice event delegation', done: false },
  { id: 3, text: 'Build a todo app', done: false },
];
let nextId = 4;

function renderTodos() {
  const list = document.getElementById('todo-list');
  list.innerHTML = todos.map(todo => `
    <li class="todo-item ${todo.done ? 'done' : ''}" data-id="${todo.id}">
      <span class="todo-text">${todo.text}</span>
      <button class="complete-btn" data-action="complete">
        ${todo.done ? 'Undo' : 'Done'}
      </button>
      <button class="delete-btn" data-action="delete">Delete</button>
    </li>
  `).join('');

  const remaining = todos.filter(t => !t.done).length;
  document.getElementById('todo-count').textContent =
    `${remaining} of ${todos.length} remaining`;
}

// ONE listener on the list handles ALL todo interactions
// This works for dynamically added todos too!
document.getElementById('todo-list').addEventListener('click', (e) => {
  // Find the closest li ancestor
  const item = e.target.closest('li[data-id]');
  if (!item) return;

  const id = Number(item.dataset.id);
  const action = e.target.dataset.action;

  if (action === 'complete') {
    todos = todos.map(t => t.id === id ? { ...t, done: !t.done } : t);
    renderTodos();
  }

  if (action === 'delete') {
    todos = todos.filter(t => t.id !== id);
    renderTodos();
  }
});

function addTodo() {
  const input = document.getElementById('todo-input');
  const text = input.value.trim();
  if (!text) return;

  todos.push({ id: nextId++, text, done: false });
  input.value = '';
  renderTodos();
  // The delegation listener automatically handles the new todo!
}

renderTodos();
```

---

## Step 4 — e.target vs e.currentTarget

Add this HTML:

```html
<h2>e.target vs e.currentTarget</h2>
<div class="card">
  <p style="margin-bottom:0.75rem;font-size:0.9rem">One listener on the container. Click any button.</p>
  <div id="btn-container" style="display:flex;gap:0.75rem;margin-bottom:0.75rem">
    <button style="padding:0.5rem 1rem;background:#3498db;color:white;border:none;border-radius:6px;cursor:pointer">Button A</button>
    <button style="padding:0.5rem 1rem;background:#27ae60;color:white;border:none;border-radius:6px;cursor:pointer">Button B</button>
    <button style="padding:0.5rem 1rem;background:#9b59b6;color:white;border:none;border-radius:6px;cursor:pointer">Button C</button>
  </div>
  <div class="log" id="target-log">Click a button...</div>
</div>
```

Add this JavaScript:

```javascript
document.getElementById('btn-container').addEventListener('click', (e) => {
  document.getElementById('target-log').innerHTML = `
    <div>e.target: &lt;${e.target.tagName.toLowerCase()}&gt; "${e.target.textContent}"</div>
    <div>e.currentTarget: &lt;${e.currentTarget.tagName.toLowerCase()}#${e.currentTarget.id}&gt;</div>
    <div>Same element? ${e.target === e.currentTarget}</div>
  `;
});
```

---

## Checklist

- [ ] Clicking the inner box fires all three listeners (inner, middle, outer)
- [ ] Bubbling log shows the correct order (inner → middle → outer)
- [ ] Todo list uses ONE listener on `<ul>` for all interactions
- [ ] Delegation works for dynamically added todos
- [ ] `e.target.closest('li')` finds the correct list item
- [ ] `e.target.dataset.action` identifies which button was clicked
- [ ] `e.target` shows the clicked button, `e.currentTarget` shows the container

---

## Bonus Challenges

1. Add a `stopPropagation()` button to the middle box that stops bubbling
2. Add a "Select All" checkbox that uses delegation to check/uncheck all todos
3. Add keyboard support: pressing Delete while a todo is focused removes it
