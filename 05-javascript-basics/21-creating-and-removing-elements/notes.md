# Notes — Creating and Removing Elements

## Creating Elements

```javascript
// Create an element
const div = document.createElement('div');
const p = document.createElement('p');
const img = document.createElement('img');
const a = document.createElement('a');

// Set content and attributes
div.textContent = 'Hello!';
div.className = 'card';
div.id = 'my-card';
img.src = 'photo.jpg';
img.alt = 'A photo';
a.href = '/about';
a.textContent = 'About';

// Set multiple attributes at once
Object.assign(img, { src: 'photo.jpg', alt: 'Photo', width: 300 });
```

## Adding to the DOM

```javascript
const container = document.querySelector('.container');
const newCard = document.createElement('div');
newCard.className = 'card';
newCard.textContent = 'New Card';

// Add as last child
container.appendChild(newCard);

// Add as first child
container.prepend(newCard);

// Insert before a reference element
const refEl = document.querySelector('.card:nth-child(2)');
container.insertBefore(newCard, refEl);

// insertAdjacentElement — most flexible
refEl.insertAdjacentElement('beforebegin', newCard); // before refEl
refEl.insertAdjacentElement('afterbegin', newCard);  // first child of refEl
refEl.insertAdjacentElement('beforeend', newCard);   // last child of refEl
refEl.insertAdjacentElement('afterend', newCard);    // after refEl

// insertAdjacentHTML — insert HTML string
container.insertAdjacentHTML('beforeend', '<div class="card">New</div>');
```

## innerHTML vs createElement

```javascript
// innerHTML — fast but risky with user data
container.innerHTML += '<div class="card">New</div>';
// ❌ Resets all event listeners on existing children
// ❌ XSS risk if content includes user input

// createElement — safer and more flexible
const card = document.createElement('div');
card.className = 'card';
card.textContent = userInput; // safe — no HTML parsing
container.appendChild(card);
// ✅ Preserves existing event listeners
// ✅ Safe with user input
```

## Removing Elements

```javascript
const el = document.querySelector('.card');

// Modern — remove the element itself
el.remove();

// Older — remove via parent
el.parentElement.removeChild(el);

// Remove all children
container.innerHTML = '';                    // fast but loses event listeners
while (container.firstChild) {
  container.removeChild(container.firstChild); // preserves listeners
}
container.replaceChildren();                 // modern, clean
```

## Cloning Elements

```javascript
const original = document.querySelector('.card');

// Shallow clone — element only, no children
const shallowClone = original.cloneNode(false);

// Deep clone — element AND all children
const deepClone = original.cloneNode(true);

container.appendChild(deepClone);
// Note: cloned elements do NOT have event listeners from the original
```

## DocumentFragment — Batch DOM Updates

```javascript
// ❌ Slow — 100 DOM updates
for (let i = 0; i < 100; i++) {
  const li = document.createElement('li');
  li.textContent = `Item ${i}`;
  list.appendChild(li); // triggers layout each time
}

// ✅ Fast — 1 DOM update
const fragment = document.createDocumentFragment();
for (let i = 0; i < 100; i++) {
  const li = document.createElement('li');
  li.textContent = `Item ${i}`;
  fragment.appendChild(li); // no DOM update yet
}
list.appendChild(fragment); // one DOM update
```

## Common Mistakes

- Using `innerHTML +=` in a loop (re-parses entire HTML each time — use `appendChild`)
- Forgetting to append the created element to the DOM
- Using `innerHTML` with user input (XSS risk)
- Not using DocumentFragment for large lists (causes layout thrashing)
- Cloning an element and expecting its event listeners to be copied (they're not)
