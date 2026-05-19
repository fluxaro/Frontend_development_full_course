# Notes — Template Literals and String Methods

## Template Literals

```javascript
const name = 'Alex';
const age = 25;

// Basic interpolation
`Hello, ${name}!`           // 'Hello, Alex!'
`You are ${age} years old.` // 'You are 25 years old.'

// Expressions inside ${}
`2 + 2 = ${2 + 2}`          // '2 + 2 = 4'
`Next year: ${age + 1}`     // 'Next year: 26'
`${name.toUpperCase()}`     // 'ALEX'
`${age >= 18 ? 'Adult' : 'Minor'}` // 'Adult'

// Multi-line strings (preserves newlines)
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

## Essential String Methods

```javascript
const str = '  Hello, World!  ';

// Whitespace
str.trim()          // 'Hello, World!'
str.trimStart()     // 'Hello, World!  '
str.trimEnd()       // '  Hello, World!'

// Case
str.toUpperCase()   // '  HELLO, WORLD!  '
str.toLowerCase()   // '  hello, world!  '

// Search
str.includes('World')     // true
str.startsWith('  Hello') // true
str.endsWith('!  ')       // true
str.indexOf('o')          // 4 (first occurrence)
str.lastIndexOf('o')      // 8 (last occurrence)

// Extract
str.slice(2, 7)           // 'Hello'
str.slice(-3)             // '!  ' (from end)
str.substring(2, 7)       // 'Hello'
str.at(-1)                // ' ' (last char, modern)

// Replace
str.replace('World', 'JS')     // '  Hello, JS!  '
str.replaceAll('l', 'L')       // '  HeLLo, WorLd!  '
str.replace(/\s+/g, ' ')       // replace multiple spaces with one

// Split
'a,b,c'.split(',')        // ['a', 'b', 'c']
'hello'.split('')         // ['h','e','l','l','o']
'hello world'.split(' ')  // ['hello', 'world']

// Pad
'5'.padStart(3, '0')      // '005'
'hi'.padEnd(5, '.')       // 'hi...'
'42'.padStart(5)          // '   42' (default pad char is space)

// Repeat
'ha'.repeat(3)            // 'hahaha'
'-'.repeat(20)            // '--------------------'

// Check
str.length                // 18
```

## String Immutability

Strings are immutable — methods return new strings, they don't modify the original:

```javascript
const str = 'hello';
str.toUpperCase(); // 'HELLO'
console.log(str);  // 'hello' — unchanged!

const upper = str.toUpperCase(); // must assign to a variable
```

## Common Patterns

```javascript
// Capitalise first letter
const capitalise = str => str.charAt(0).toUpperCase() + str.slice(1);

// Truncate with ellipsis
const truncate = (str, max) => str.length > max ? str.slice(0, max) + '...' : str;

// Slugify
const slugify = str => str.toLowerCase().trim().replace(/\s+/g, '-').replace(/[^\w-]/g, '');

// Count words
const countWords = str => str.trim().split(/\s+/).length;

// Check palindrome
const isPalindrome = str => {
  const clean = str.toLowerCase().replace(/[^a-z0-9]/g, '');
  return clean === clean.split('').reverse().join('');
};
```

## Common Mistakes

- Template literals use backticks `` ` `` not single or double quotes
- `slice` accepts negative indices; `substring` does not
- `replace` only replaces the **first** match — use `replaceAll` or `/g` regex for all
- Strings are immutable — always assign the result to a variable
