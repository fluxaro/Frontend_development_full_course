# 19 — DOM: Selecting Elements

## What Is This Lesson About?

The DOM (Document Object Model) is a tree of objects representing the HTML page. JavaScript can select, read, and modify any element in the DOM.

---

## Selecting Elements

```javascript
// By ID — returns one element or null
const header = document.getElementById('header');

// By CSS selector — returns first match or null
const btn = document.querySelector('.btn');
const title = document.querySelector('h1');
const input = document.querySelector('input[type="email"]');

// By CSS selector — returns NodeList of all matches
const cards = document.querySelectorAll('.card');
const links = document.querySelectorAll('a');

// Legacy methods (still work)
document.getElementsByClassName('card'); // HTMLCollection
document.getElementsByTagName('p');      // HTMLCollection
```

---

## querySelector vs getElementById

| Method | Returns | Speed |
|---|---|---|
| `getElementById` | One element | Fastest |
| `querySelector` | First match | Flexible |
| `querySelectorAll` | NodeList | Flexible |

Use `querySelector` and `querySelectorAll` for most cases — they accept any CSS selector.

---

## Traversing the DOM

```javascript
const el = document.querySelector('.card');

el.parentElement;           // parent element
el.children;                // child elements (HTMLCollection)
el.firstElementChild;       // first child element
el.lastElementChild;        // last child element
el.nextElementSibling;      // next sibling element
el.previousElementSibling;  // previous sibling element
el.closest('.container');   // nearest ancestor matching selector
```

---

## NodeList vs Array

`querySelectorAll` returns a NodeList, not an array. Convert it to use array methods:

```javascript
const cards = document.querySelectorAll('.card');

// Convert to array
const cardsArray = Array.from(cards);
const cardsArray = [...cards];

// forEach works on NodeList directly
cards.forEach(card => card.classList.add('active'));
```

---

## Common Mistakes

- `getElementById` doesn't take a `#` prefix — just the ID string
- `querySelector` returns `null` if nothing matches — always check before using
- NodeList is not an array — `map`, `filter` don't work directly on it
- Selecting elements before the DOM is loaded (use `defer` or `DOMContentLoaded`)
