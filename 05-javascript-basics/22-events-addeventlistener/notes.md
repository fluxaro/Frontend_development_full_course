# Notes — Events: addEventListener

## addEventListener Syntax

```javascript
element.addEventListener(eventType, handler, options);

// Basic click
const btn = document.querySelector('#myBtn');
btn.addEventListener('click', function(event) {
  console.log('Clicked!', event);
});

// Arrow function
btn.addEventListener('click', (e) => {
  console.log('Clicked at:', e.clientX, e.clientY);
});

// Named function (can be removed later)
function handleClick(e) {
  console.log('Clicked!');
}
btn.addEventListener('click', handleClick);
btn.removeEventListener('click', handleClick); // must be same reference
```

## The Event Object

```javascript
btn.addEventListener('click', (e) => {
  e.type;              // 'click'
  e.target;            // element that was clicked (could be a child)
  e.currentTarget;     // element the listener is attached to
  e.preventDefault();  // prevent default browser action (form submit, link follow)
  e.stopPropagation(); // stop event from bubbling up to parent elements

  // Mouse events
  e.clientX;           // X position relative to viewport
  e.clientY;           // Y position relative to viewport
  e.pageX;             // X position relative to document
  e.button;            // 0=left, 1=middle, 2=right

  // Keyboard events
  e.key;               // 'Enter', 'Escape', 'a', 'ArrowUp', etc.
  e.code;              // 'KeyA', 'Enter', 'Space' (physical key)
  e.ctrlKey;           // true if Ctrl held
  e.shiftKey;          // true if Shift held
  e.altKey;            // true if Alt held
  e.metaKey;           // true if Cmd (Mac) or Win key held
});
```

## Common Events

```javascript
// Mouse
'click'         // single click
'dblclick'      // double click
'mouseenter'    // mouse enters element (doesn't bubble)
'mouseleave'    // mouse leaves element (doesn't bubble)
'mouseover'     // mouse enters element or child (bubbles)
'mouseout'      // mouse leaves element or child (bubbles)
'mousemove'     // mouse moves over element
'contextmenu'   // right-click

// Keyboard
'keydown'       // key pressed (fires repeatedly when held)
'keyup'         // key released
'keypress'      // deprecated — use keydown

// Form
'submit'        // form submitted
'change'        // value changed and element loses focus
'input'         // value changed (fires on every keystroke)
'focus'         // element gains focus
'blur'          // element loses focus
'reset'         // form reset

// Window/Document
'load'          // page fully loaded (images, scripts, etc.)
'DOMContentLoaded' // HTML parsed (before images)
'resize'        // window resized
'scroll'        // page or element scrolled
'beforeunload'  // user about to leave page
```

## Options

```javascript
// Once — fires only once, then auto-removes
btn.addEventListener('click', handler, { once: true });

// Passive — improves scroll performance (cannot call preventDefault)
window.addEventListener('scroll', handler, { passive: true });

// Capture — fires during capture phase (before bubbling)
document.addEventListener('click', handler, { capture: true });
// or shorthand:
document.addEventListener('click', handler, true);
```

## Removing Event Listeners

```javascript
// Must use the SAME function reference
function handleClick(e) { console.log('clicked'); }

btn.addEventListener('click', handleClick);
btn.removeEventListener('click', handleClick); // ✅ works

// ❌ This does NOT work — different function reference
btn.addEventListener('click', () => console.log('clicked'));
btn.removeEventListener('click', () => console.log('clicked')); // no effect
```

## Common Mistakes

- Using `onclick = fn` instead of `addEventListener` (can only have one handler)
- Passing `handler()` instead of `handler` (calls immediately, not on event)
- Trying to `removeEventListener` with an anonymous function (won't work)
- Not calling `e.preventDefault()` on form submit (page reloads)
- Using `keypress` (deprecated) instead of `keydown`
