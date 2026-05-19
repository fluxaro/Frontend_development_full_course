# Notes — DOM Manipulation: textContent, classList

## Reading and Setting Content

```javascript
const el = document.querySelector('h1');

// textContent — plain text (safe, no HTML parsing)
el.textContent;                    // get text
el.textContent = 'New Heading';    // set text (HTML is escaped)
el.textContent = '<b>Bold</b>';    // displays literally: <b>Bold</b>

// innerHTML — parses HTML (use carefully — XSS risk with user input)
el.innerHTML;                      // get HTML
el.innerHTML = '<strong>Bold</strong>'; // renders as bold
el.innerHTML = userInput;          // ❌ DANGEROUS — XSS vulnerability

// innerText — like textContent but respects CSS visibility
el.innerText;                      // get visible text only

// Input values
const input = document.querySelector('input');
input.value;                       // get current value
input.value = 'Alex';              // set value
input.placeholder = 'Enter name'; // set placeholder
```

## classList

```javascript
const el = document.querySelector('.card');

el.classList.add('active');              // add one class
el.classList.add('active', 'featured'); // add multiple
el.classList.remove('active');           // remove class
el.classList.toggle('active');           // add if absent, remove if present
el.classList.toggle('active', true);     // force add
el.classList.toggle('active', false);    // force remove
el.classList.contains('active');         // true/false
el.classList.replace('old', 'new');      // replace class
el.classList.length;                     // number of classes
el.className;                            // all classes as string
[...el.classList];                       // convert to array
```

## Attributes

```javascript
el.getAttribute('href');                 // get attribute value
el.setAttribute('href', '/about');       // set attribute
el.removeAttribute('disabled');          // remove attribute
el.hasAttribute('disabled');             // true/false
el.toggleAttribute('disabled');          // toggle boolean attribute

// Data attributes
el.dataset.userId;                       // data-user-id
el.dataset.userId = '123';              // set data-user-id
el.dataset.isActive;                     // data-is-active
Object.keys(el.dataset);                 // all data attributes
```

## Styles

```javascript
// Inline styles (camelCase property names)
el.style.color = 'red';
el.style.backgroundColor = '#3498db';   // not background-color
el.style.fontSize = '1.5rem';
el.style.display = 'none';
el.style.cssText = 'color: red; font-size: 1.5rem;'; // set multiple

// Get computed style (what's actually applied, including CSS)
const computed = getComputedStyle(el);
computed.color;                          // 'rgb(255, 0, 0)'
computed.fontSize;                       // '24px'
computed.display;                        // 'block'
```

## Best Practices

```javascript
// ✅ Prefer classList over style for toggling
el.classList.toggle('hidden');           // better
el.style.display = 'none';              // worse (hard to undo)

// ✅ Use textContent for user-generated content (safe)
el.textContent = userInput;             // safe

// ❌ Never use innerHTML with user input
el.innerHTML = userInput;               // XSS vulnerability!

// ✅ Use innerHTML only for trusted HTML
el.innerHTML = `<strong>${trustedText}</strong>`;
```

## Common Mistakes

- Using `innerHTML` with user input — XSS vulnerability. Always use `textContent` for text
- `classList.toggle` returns `true` if class was added, `false` if removed
- Inline styles override CSS — prefer adding/removing classes instead
- `style.backgroundColor` not `style.background-color` (camelCase in JS)
- `innerText` triggers layout reflow; `textContent` does not
