# 23 — Event Bubbling and Delegation

## What Is This Lesson About?

Events bubble up the DOM tree from the target element to the root. Event delegation uses this to handle events on many elements with a single listener on a parent.

---

## Event Bubbling

When an event fires on an element, it bubbles up through all ancestors:

```
button → div → section → main → body → html → document → window
```

```javascript
document.querySelector('button').addEventListener('click', () => {
  console.log('button clicked');
});

document.querySelector('div').addEventListener('click', () => {
  console.log('div clicked'); // also fires when button is clicked!
});
```

---

## stopPropagation

```javascript
btn.addEventListener('click', (e) => {
  e.stopPropagation(); // stops bubbling — parent listeners won't fire
});
```

---

## Event Delegation

Instead of adding listeners to each child, add one listener to the parent:

```javascript
// ❌ Without delegation — adds 100 listeners
document.querySelectorAll('.btn').forEach(btn => {
  btn.addEventListener('click', handleClick);
});

// ✅ With delegation — one listener handles all
document.querySelector('.btn-container').addEventListener('click', (e) => {
  if (e.target.matches('.btn')) {
    handleClick(e);
  }
});
```

### Why delegation is better:
- Works for dynamically added elements
- Uses less memory (one listener vs many)
- Easier to manage

---

## Practical Delegation Example

```javascript
const list = document.querySelector('#todo-list');

list.addEventListener('click', (e) => {
  // Delete button
  if (e.target.matches('.delete-btn')) {
    e.target.closest('li').remove();
  }
  // Complete button
  if (e.target.matches('.complete-btn')) {
    e.target.closest('li').classList.toggle('done');
  }
});
```

---

## Common Mistakes

- Using `e.target` when you mean `e.currentTarget` (target is the clicked element, currentTarget is where the listener is)
- Forgetting that `stopPropagation` also stops other listeners on the same element from running (use `stopImmediatePropagation` for that)
- Not using `closest()` to find the right ancestor when delegating
