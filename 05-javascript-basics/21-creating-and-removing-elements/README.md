# 21 — Creating and Removing Elements

## What Is This Lesson About?

You can dynamically create new HTML elements with JavaScript and add them to the page, or remove existing elements.

---

## Creating Elements

```javascript
// Create an element
const div = document.createElement('div');
const p = document.createElement('p');
const img = document.createElement('img');

// Set content and attributes
div.textContent = 'Hello!';
div.classList.add('card');
img.src = 'photo.jpg';
img.alt = 'A photo';
```

---

## Adding to the DOM

```javascript
const container = document.querySelector('.container');
const newCard = document.createElement('div');
newCard.className = 'card';
newCard.textContent = 'New Card';

container.appendChild(newCard);          // add as last child
container.prepend(newCard);              // add as first child
container.insertBefore(newCard, refEl);  // before a reference element
refEl.insertAdjacentElement('afterend', newCard); // after reference
```

---

## innerHTML vs createElement

```javascript
// innerHTML — fast but risky with user data
container.innerHTML += '<div class="card">New</div>';

// createElement — safer and more flexible
const card = document.createElement('div');
card.className = 'card';
card.textContent = userInput; // safe — no HTML parsing
container.appendChild(card);
```

---

## Removing Elements

```javascript
const el = document.querySelector('.card');

el.remove();                    // remove element itself
el.parentElement.removeChild(el); // older way

// Remove all children
container.innerHTML = '';       // fast but loses event listeners
while (container.firstChild) {
  container.removeChild(container.firstChild); // preserves listeners
}
```

---

## Cloning Elements

```javascript
const original = document.querySelector('.card');
const clone = original.cloneNode(true); // true = deep clone (includes children)
container.appendChild(clone);
```

---

## DocumentFragment — Batch DOM Updates

```javascript
const fragment = document.createDocumentFragment();
for (let i = 0; i < 100; i++) {
  const li = document.createElement('li');
  li.textContent = `Item ${i}`;
  fragment.appendChild(li);
}
list.appendChild(fragment); // one DOM update instead of 100
```

---

## Common Mistakes

- Using `innerHTML +=` in a loop (re-parses entire HTML each time — use `appendChild`)
- Forgetting to append the created element to the DOM
- Using `innerHTML` with user input (XSS risk)
- Not using DocumentFragment for large lists (causes layout thrashing)
