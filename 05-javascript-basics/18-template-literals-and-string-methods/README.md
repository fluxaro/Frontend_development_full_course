# 18 — Template Literals and String Methods

## What Is This Lesson About?

Template literals provide a cleaner way to build strings with embedded expressions. Combined with JavaScript's rich string methods, you can handle almost any text manipulation task.

---

## Template Literals

```javascript
const name = 'Alex';
const age = 25;

// Basic interpolation
`Hello, ${name}!`           // 'Hello, Alex!'
`You are ${age} years old.` // 'You are 25 years old.'

// Expressions
`2 + 2 = ${2 + 2}`          // '2 + 2 = 4'
`Next year: ${age + 1}`     // 'Next year: 26'

// Multi-line strings
const html = `
  <div class="card">
    <h2>${name}</h2>
    <p>Age: ${age}</p>
  </div>
`;

// Nested template literals
const items = ['HTML', 'CSS', 'JS'];
const list = `<ul>${items.map(i => `<li>${i}</li>`).join('')}</ul>`;
```

---

## Essential String Methods

```javascript
const str = '  Hello, World!  ';

// Whitespace
str.trim()        // 'Hello, World!'
str.trimStart()   // 'Hello, World!  '
str.trimEnd()     // '  Hello, World!'

// Case
str.toUpperCase() // '  HELLO, WORLD!  '
str.toLowerCase() // '  hello, world!  '

// Search
str.includes('World')    // true
str.startsWith('  Hello') // true
str.endsWith('!  ')      // true
str.indexOf('o')         // 4
str.lastIndexOf('o')     // 8

// Extract
str.slice(2, 7)          // 'Hello'
str.slice(-3)            // '!  '
str.substring(2, 7)      // 'Hello'

// Replace
str.replace('World', 'JS')    // '  Hello, JS!  '
str.replaceAll('l', 'L')      // '  HeLLo, WorLd!  '

// Split
'a,b,c'.split(',')       // ['a', 'b', 'c']
'hello'.split('')        // ['h','e','l','l','o']

// Pad
'5'.padStart(3, '0')     // '005'
'hi'.padEnd(5, '.')      // 'hi...'

// Repeat
'ha'.repeat(3)           // 'hahaha'

// Check
str.length               // 18
```

---

## Common Mistakes

- Template literals use backticks `` ` `` not quotes
- `slice` accepts negative indices; `substring` does not
- `replace` only replaces the first match — use `replaceAll` for all
- `split('')` on an emoji may give unexpected results (use `[...str]` instead)
