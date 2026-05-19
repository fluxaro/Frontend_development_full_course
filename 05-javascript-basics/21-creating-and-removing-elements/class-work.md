# Class Work — Creating and Removing DOM Elements

## What You Will Build

A dynamic card builder that creates, clones, and removes cards using `createElement`, `appendChild`, `cloneNode`, and `remove`.

**Time:** 35 minutes  
**Output:** `create-remove-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Create and Remove Elements</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; }
    h1 { margin-bottom: 2rem; }
    h2 { margin: 2rem 0 1rem; color: #555; border-bottom: 2px solid #dee2e6; padding-bottom: 0.5rem; }
    .form-row { display: flex; gap: 0.75rem; align-items: center; margin-bottom: 1rem; flex-wrap: wrap; }
    input { flex: 1; min-width: 150px; padding: 0.5rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; }
    input:focus { border-color: #3498db; }
    button { padding: 0.5rem 1rem; border: none; border-radius: 6px; cursor: pointer; font-size: 0.85rem; font-family: inherit; }
    .btn-blue { background: #3498db; color: white; }
    .btn-green { background: #27ae60; color: white; }
    .btn-red { background: #e74c3c; color: white; }
    .btn-orange { background: #e67e22; color: white; }
    .btn-grey { background: #95a5a6; color: white; }
    .card-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 1rem; min-height: 100px; }
    .card { background: white; border: 1px solid #dee2e6; border-radius: 8px; padding: 1.25rem; position: relative; transition: box-shadow 0.2s; }
    .card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
    .card h3 { font-size: 0.95rem; margin-bottom: 0.4rem; }
    .card p { font-size: 0.85rem; color: #666; margin-bottom: 0.75rem; }
    .card-actions { display: flex; gap: 0.4rem; }
    .delete-btn { position: absolute; top: 0.5rem; right: 0.5rem; background: none; border: none; cursor: pointer; font-size: 1rem; color: #ccc; padding: 0.25rem; }
    .delete-btn:hover { color: #e74c3c; }
    .empty-state { text-align: center; color: #aaa; padding: 2rem; font-size: 0.9rem; grid-column: 1/-1; }
    .count-badge { background: #3498db; color: white; border-radius: 999px; padding: 0.2rem 0.6rem; font-size: 0.8rem; font-weight: bold; margin-left: 0.5rem; }
  </style>
</head>
<body>
  <h1>Creating and Removing Elements</h1>
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Card Builder

Add this HTML before `<script>`:

```html
<h2>Card Builder</h2>
<div class="form-row">
  <input type="text" id="card-title" placeholder="Card title">
  <input type="text" id="card-desc" placeholder="Card description">
  <button class="btn-blue" onclick="addCard()">Add Card</button>
  <button class="btn-grey" onclick="clearAll()">Clear All</button>
</div>
<p>Cards: <span class="count-badge" id="card-count">0</span></p>
<div class="card-grid" id="card-grid">
  <div class="empty-state" id="empty-state">No cards yet. Add one above!</div>
</div>
```

Add this JavaScript:

```javascript
let cardCount = 0;

function addCard() {
  const titleInput = document.getElementById('card-title');
  const descInput = document.getElementById('card-desc');
  const title = titleInput.value.trim();
  const desc = descInput.value.trim();

  if (!title) {
    titleInput.focus();
    return;
  }

  // Remove empty state
  const emptyState = document.getElementById('empty-state');
  if (emptyState) emptyState.remove();

  // Create card using createElement (not innerHTML)
  const card = document.createElement('div');
  card.className = 'card';
  card.dataset.id = ++cardCount;

  const h3 = document.createElement('h3');
  h3.textContent = title; // safe — textContent, not innerHTML

  const p = document.createElement('p');
  p.textContent = desc || 'No description';

  const actions = document.createElement('div');
  actions.className = 'card-actions';

  const cloneBtn = document.createElement('button');
  cloneBtn.className = 'btn-green';
  cloneBtn.textContent = 'Clone';
  cloneBtn.onclick = () => cloneCard(card);

  const deleteBtn = document.createElement('button');
  deleteBtn.className = 'delete-btn';
  deleteBtn.textContent = '✕';
  deleteBtn.title = 'Delete card';
  deleteBtn.onclick = () => removeCard(card);

  actions.appendChild(cloneBtn);
  card.appendChild(h3);
  card.appendChild(p);
  card.appendChild(actions);
  card.appendChild(deleteBtn);

  document.getElementById('card-grid').appendChild(card);

  // Clear inputs
  titleInput.value = '';
  descInput.value = '';
  titleInput.focus();

  updateCount();
}

function cloneCard(original) {
  const clone = original.cloneNode(true); // deep clone
  clone.dataset.id = ++cardCount;

  // Re-attach event listeners (cloneNode doesn't copy them)
  clone.querySelector('.delete-btn').onclick = () => removeCard(clone);
  clone.querySelector('.btn-green').onclick = () => cloneCard(clone);

  // Insert after the original
  original.insertAdjacentElement('afterend', clone);
  updateCount();
}

function removeCard(card) {
  card.remove();
  updateCount();

  // Show empty state if no cards
  const grid = document.getElementById('card-grid');
  if (grid.children.length === 0) {
    const emptyState = document.createElement('div');
    emptyState.className = 'empty-state';
    emptyState.id = 'empty-state';
    emptyState.textContent = 'No cards yet. Add one above!';
    grid.appendChild(emptyState);
  }
}

function clearAll() {
  const grid = document.getElementById('card-grid');
  grid.replaceChildren(); // modern way to remove all children

  const emptyState = document.createElement('div');
  emptyState.className = 'empty-state';
  emptyState.id = 'empty-state';
  emptyState.textContent = 'No cards yet. Add one above!';
  grid.appendChild(emptyState);

  updateCount();
}

function updateCount() {
  const cards = document.querySelectorAll('.card');
  document.getElementById('card-count').textContent = cards.length;
}
```

---

## Step 3 — DocumentFragment Demo

Add this HTML:

```html
<h2>DocumentFragment — Batch Insert (Performance)</h2>
<div class="form-row">
  <input type="number" id="item-count" value="20" min="1" max="100">
  <button class="btn-orange" onclick="addManyItems()">Add Items with Fragment</button>
  <button class="btn-red" onclick="clearList()">Clear List</button>
</div>
<ul id="item-list" style="background:white;border:1px solid #dee2e6;border-radius:8px;padding:1rem;max-height:200px;overflow-y:auto;list-style:none"></ul>
```

Add this JavaScript:

```javascript
function addManyItems() {
  const count = Number(document.getElementById('item-count').value);
  const list = document.getElementById('item-list');

  // Use DocumentFragment for batch insert — one DOM update
  const fragment = document.createDocumentFragment();

  for (let i = 1; i <= count; i++) {
    const li = document.createElement('li');
    li.textContent = `Item ${i}`;
    li.style.cssText = 'padding:0.3rem 0;border-bottom:1px solid #f0f0f0;font-size:0.85rem';
    fragment.appendChild(li);
  }

  list.appendChild(fragment); // ONE DOM update instead of ${count}
}

function clearList() {
  document.getElementById('item-list').replaceChildren();
}
```

---

## Checklist

- [ ] Cards are created with `createElement`, not `innerHTML`
- [ ] Card title uses `textContent` (safe with user input)
- [ ] Clone button creates a deep clone with `cloneNode(true)`
- [ ] Cloned card has re-attached event listeners
- [ ] Delete button uses `el.remove()`
- [ ] "Clear All" uses `replaceChildren()` to remove all children
- [ ] Empty state shows when no cards exist
- [ ] DocumentFragment adds many items in one DOM update

---

## Bonus Challenges

1. Add drag-and-drop reordering using the HTML5 Drag and Drop API
2. Add a "Prepend" button that adds a card to the beginning using `prepend()`
3. Add an animation when cards are added (CSS transition on opacity and transform)
