# Notes — DOM: Selecting Elements

## What is the DOM?

The DOM (Document Object Model) is a tree of objects representing the HTML page. JavaScript can select, read, and modify any element in the DOM.

```
document
└── html
    ├── head
    │   └── title
    └── body
        ├── header
        │   └── h1
        ├── main
        │   ├── section
        │   │   └── p
        │   └── div.card
        └── footer
```

## Selecting Elements

```javascript
// By ID — returns one element or null
const header = document.getElementById('header');
// Note: no # prefix — just the ID string

// By CSS selector — returns FIRST match or null
const btn = document.querySelector('.btn');
const title = document.querySelector('h1');
const input = document.querySelector('input[type="email"]');
const firstCard = document.querySelector('.card');
const nav = document.querySelector('nav > ul > li:first-child');

// By CSS selector — returns NodeList of ALL matches
const cards = document.querySelectorAll('.card');
const links = document.querySelectorAll('a[href^="https"]');
const inputs = document.querySelectorAll('input, textarea, select');

// Legacy methods (still work, less flexible)
document.getElementsByClassName('card');  // HTMLCollection (live)
document.getElementsByTagName('p');       // HTMLCollection (live)
document.getElementsByName('email');      // NodeList
```

## querySelector vs getElementById

| Method | Returns | Accepts |
|---|---|---|
| `getElementById` | One element | ID string (no #) |
| `querySelector` | First match | Any CSS selector |
| `querySelectorAll` | NodeList | Any CSS selector |

Use `querySelector` and `querySelectorAll` for most cases — they accept any CSS selector.

## Traversing the DOM

```javascript
const el = document.querySelector('.card');

// Parent
el.parentElement;              // direct parent element
el.closest('.container');      // nearest ancestor matching selector

// Children
el.children;                   // HTMLCollection of child elements
el.firstElementChild;          // first child element
el.lastElementChild;           // last child element
el.childElementCount;          // number of child elements

// Siblings
el.nextElementSibling;         // next sibling element
el.previousElementSibling;     // previous sibling element
```

## NodeList vs Array

`querySelectorAll` returns a NodeList, not an array:

```javascript
const cards = document.querySelectorAll('.card');

// forEach works directly on NodeList
cards.forEach(card => card.classList.add('active'));

// But map, filter, reduce do NOT work on NodeList
// Convert to array first:
const cardsArray = Array.from(cards);
const cardsArray = [...cards];

// Now you can use all array methods
const activeCards = cardsArray.filter(c => c.classList.contains('active'));
```

## Checking if Element Exists

```javascript
const el = document.querySelector('.modal');

if (el) {
  // element exists — safe to use
  el.classList.add('open');
} else {
  console.warn('Modal element not found');
}
```

## Common Mistakes

- `getElementById` doesn't take a `#` prefix — just the ID string
- `querySelector` returns `null` if nothing matches — always check before using
- NodeList is not an array — `map`, `filter`, `reduce` don't work directly on it
- Selecting elements before the DOM is loaded — use `defer` on script tags or `DOMContentLoaded`
- `getElementsByClassName` returns a live HTMLCollection — it updates automatically (can cause bugs in loops)
