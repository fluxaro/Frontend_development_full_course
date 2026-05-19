# Notes — Event Bubbling and Delegation

## Event Propagation Phases

When an event fires, it travels through three phases:

1. **Capture phase** — from `window` down to the target
2. **Target phase** — at the target element
3. **Bubble phase** — from the target back up to `window`

```
window → document → html → body → div → button (target)
button → div → body → html → document → window (bubble)
```

## Event Bubbling

By default, events bubble up from the target to the root:

```javascript
document.querySelector('button').addEventListener('click', () => {
  console.log('button clicked');
});

document.querySelector('div').addEventListener('click', () => {
  console.log('div clicked'); // also fires when button is clicked!
});

document.querySelector('body').addEventListener('click', () => {
  console.log('body clicked'); // also fires!
});
```

Clicking the button logs: "button clicked", "div clicked", "body clicked"

## stopPropagation

```javascript
btn.addEventListener('click', (e) => {
  e.stopPropagation(); // stops bubbling — parent listeners won't fire
  console.log('only button fires');
});

// stopImmediatePropagation — also stops other listeners on the SAME element
btn.addEventListener('click', (e) => {
  e.stopImmediatePropagation();
});
```

## Event Delegation

Instead of adding listeners to each child, add ONE listener to the parent:

```javascript
// ❌ Without delegation — adds N listeners (slow, doesn't work for dynamic elements)
document.querySelectorAll('.btn').forEach(btn => {
  btn.addEventListener('click', handleClick);
});

// ✅ With delegation — one listener handles all current AND future elements
document.querySelector('.btn-container').addEventListener('click', (e) => {
  if (e.target.matches('.btn')) {
    handleClick(e);
  }
  // Handle different child types
  if (e.target.matches('.delete-btn')) {
    deleteItem(e);
  }
});
```

### Why delegation is better:

- Works for **dynamically added elements** (elements added after the listener was set up)
- Uses **less memory** (one listener vs many)
- **Easier to manage** (one place to handle all events)

## Practical Delegation Example

```javascript
const list = document.querySelector('#todo-list');

list.addEventListener('click', (e) => {
  // Find the closest li ancestor
  const item = e.target.closest('li');
  if (!item) return;

  // Handle delete button
  if (e.target.matches('.delete-btn')) {
    item.remove();
    return;
  }

  // Handle complete button
  if (e.target.matches('.complete-btn')) {
    item.classList.toggle('done');
    return;
  }

  // Handle clicking the item itself
  if (e.target === item || e.target.matches('.item-text')) {
    item.classList.toggle('selected');
  }
});
```

## e.target vs e.currentTarget

```javascript
list.addEventListener('click', (e) => {
  e.target;         // the element that was actually clicked (could be a child)
  e.currentTarget;  // the element the listener is attached to (always list)
});
```

## Common Mistakes

- Using `e.target` when you mean `e.currentTarget` — target is the clicked element, currentTarget is where the listener is
- Not using `closest()` to find the right ancestor when delegating
- Calling `stopPropagation()` too aggressively — breaks other listeners
- Forgetting that `stopPropagation` also stops other listeners on the same element (use `stopImmediatePropagation` for that)
