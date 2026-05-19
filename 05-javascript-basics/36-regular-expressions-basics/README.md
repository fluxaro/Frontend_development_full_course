# 36 — Regular Expressions Basics

## What Is This Lesson About?

Regular expressions (regex) are patterns for matching, searching, and replacing text. They're essential for form validation and text processing.

---

## Creating Regex

```javascript
// Literal syntax (preferred)
const pattern = /hello/;
const caseInsensitive = /hello/i;

// Constructor (for dynamic patterns)
const dynamic = new RegExp('hello', 'i');
```

---

## Flags

```javascript
/pattern/i  // case-insensitive
/pattern/g  // global — find all matches
/pattern/m  // multiline
/pattern/gi // combine flags
```

---

## Testing and Matching

```javascript
/hello/.test('hello world');  // true
/hello/.test('HELLO');        // false
/hello/i.test('HELLO');       // true

'hello world'.match(/\w+/g);  // ['hello', 'world']
'hello world'.search(/world/); // 6 (index)
'hello world'.replace(/world/, 'JS'); // 'hello JS'
'a,b,c'.split(/,/);           // ['a', 'b', 'c']
```

---

## Common Patterns

```javascript
// Email
/^[^\s@]+@[^\s@]+\.[^\s@]+$/

// Phone (basic)
/^\+?[\d\s\-()]{10,}$/

// URL
/^https?:\/\/.+/

// Only letters
/^[a-zA-Z]+$/

// Only numbers
/^\d+$/

// Alphanumeric
/^[a-zA-Z0-9]+$/

// Password (8+ chars, letter + number)
/^(?=.*[A-Za-z])(?=.*\d).{8,}$/
```

---

## Character Classes

```javascript
\d   // digit [0-9]
\D   // non-digit
\w   // word char [a-zA-Z0-9_]
\W   // non-word char
\s   // whitespace
\S   // non-whitespace
.    // any char except newline
[abc] // a, b, or c
[^abc] // not a, b, or c
[a-z] // a through z
```

---

## Quantifiers

```javascript
*    // 0 or more
+    // 1 or more
?    // 0 or 1 (optional)
{3}  // exactly 3
{3,} // 3 or more
{3,6} // 3 to 6
```

---

## Common Mistakes

- Forgetting to escape special characters: `.`, `*`, `+`, `?`, `(`, `)`, `[`, `]`, `{`, `}`, `^`, `$`, `|`, `\`
- Using `test()` with the `g` flag (stateful — use `exec` or `match` instead)
- Not anchoring patterns with `^` and `$` for full-string validation
