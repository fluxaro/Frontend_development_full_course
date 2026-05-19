# 22 — Events: addEventListener

## What Is This Lesson About?

Events are things that happen in the browser — clicks, key presses, form submissions, page loads. `addEventListener` lets you respond to them.

---

## addEventListener

```javascript
const btn = document.querySelector('#myBtn');

btn.addEventListener('click', function(event) {
  console.log('Button clicked!', event);
});

// Arrow function
btn.addEventListener('click', (e) => {
  console.log('Clicked at:', e.clientX, e.clientY);
});
```

---

## The Event Object

```javascript
btn.addEventListener('click', (e) => {
  e.target;           // element that was clicked
  e.currentTarget;    // element the listener is on
  e.type;             // 'click'
  e.preventDefault(); // prevent default browser action
  e.stopPropagation(); // stop event bubbling
  e.clientX;          // mouse X position
  e.clientY;          // mouse Y position
  e.key;              // key pressed (for keyboard events)
});
```

---

## Common Events

```javascript
// Mouse
'click', 'dblclick', 'mouseenter', 'mouseleave', 'mousemove'

// Keyboard
'keydown', 'keyup', 'keypress'

// Form
'submit', 'change', 'input', 'focus', 'blur'

// Window/Document
'load', 'DOMContentLoaded', 'resize', 'scroll'
```

---

## Removing Event Listeners

```javascript
function handleClick(e) {
  console.log('clicked');
}

btn.addEventListener('click', handleClick);
btn.removeEventListener('click', handleClick); // must be same function reference
```

---

## Once Option

```javascript
btn.addEventListener('click', handler, { once: true }); // fires only once
```

---

## Common Mistakes

- Using `onclick = fn` instead of `addEventListener` (can only have one handler)
- Passing `handler()` instead of `handler` (calls immediately, not on event)
- Trying to `removeEventListener` with an anonymous function (won't work)
- Not calling `e.preventDefault()` on form submit (page reloads)
