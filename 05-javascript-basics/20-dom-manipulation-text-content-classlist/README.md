# 20 — DOM Manipulation: textContent, classList

## What Is This Lesson About?

Once you've selected an element, you can read and change its content, attributes, styles, and classes.

---

## Reading and Setting Content

```javascript
const el = document.querySelector('h1');

// Text content (safe — no HTML parsing)
el.textContent;           // get text
el.textContent = 'Hello'; // set text

// HTML content (parses HTML — use carefully)
el.innerHTML;                          // get HTML
el.innerHTML = '<strong>Bold</strong>'; // set HTML

// Input values
const input = document.querySelector('input');
input.value;          // get value
input.value = 'Alex'; // set value
```

---

## classList

```javascript
const el = document.querySelector('.card');

el.classList.add('active');           // add class
el.classList.remove('active');        // remove class
el.classList.toggle('active');        // add if absent, remove if present
el.classList.contains('active');      // true/false
el.classList.replace('old', 'new');   // replace class
el.className;                         // all classes as string
```

---

## Attributes

```javascript
el.getAttribute('href');              // get attribute
el.setAttribute('href', '/about');    // set attribute
el.removeAttribute('disabled');       // remove attribute
el.hasAttribute('disabled');          // true/false

// Data attributes
el.dataset.userId;                    // data-user-id attribute
el.dataset.userId = '123';            // set data-user-id
```

---

## Styles

```javascript
// Inline styles (camelCase)
el.style.color = 'red';
el.style.backgroundColor = '#3498db';
el.style.display = 'none';

// Get computed style (what's actually applied)
getComputedStyle(el).color;
```

---

## Common Mistakes

- Using `innerHTML` with user input — XSS vulnerability. Use `textContent` for text
- `classList.toggle` returns `true` if class was added, `false` if removed
- Inline styles override CSS — prefer adding/removing classes instead
- `style.backgroundColor` not `style.background-color` (camelCase in JS)
