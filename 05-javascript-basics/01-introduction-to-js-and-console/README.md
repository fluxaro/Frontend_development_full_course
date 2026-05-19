# 01 — Introduction to JavaScript and the Console

## What Is This Lesson About?

JavaScript is the programming language of the web. It runs in every browser and lets you make pages interactive — responding to clicks, fetching data, updating content without reloading. This lesson covers what JavaScript is, where it runs, and how to use the browser console as your primary learning tool.

---

## What JavaScript Does

- **Responds to user actions** — clicks, typing, scrolling
- **Manipulates the DOM** — changes HTML and CSS dynamically
- **Fetches data** — communicates with APIs and servers
- **Stores data** — saves information in localStorage
- **Runs logic** — conditions, loops, calculations

---

## Where JavaScript Runs

JavaScript runs in two environments:

| Environment | Examples |
|---|---|
| **Browser** | Chrome, Firefox, Safari, Edge |
| **Server (Node.js)** | Backend APIs, build tools, scripts |

This course focuses on browser JavaScript.

---

## Adding JavaScript to HTML

```html
<!-- Inline (avoid for anything more than one line) -->
<button onclick="alert('Hello!')">Click me</button>

<!-- Internal script tag -->
<script>
  console.log('Hello from internal script');
</script>

<!-- External file (recommended) -->
<script src="app.js" defer></script>
```

Always use `defer` on external scripts — it loads the script after HTML parsing is complete.

---

## The Browser Console

The console is your most important debugging tool. Open it with:
- **Mac:** `Cmd + Option + J`
- **Windows/Linux:** `Ctrl + Shift + J`
- Or: Right-click → Inspect → Console tab

### Console Methods

```javascript
console.log('Hello, world!');          // general output
console.log(42, true, [1,2,3]);        // multiple values
console.error('Something went wrong'); // red error message
console.warn('Be careful');            // yellow warning
console.table([{name:'Alex', age:25}]);// table format
console.group('Group name');           // collapsible group
console.groupEnd();
console.time('timer');                 // start timer
console.timeEnd('timer');              // end timer, shows ms
console.clear();                       // clear the console
```

---

## Your First JavaScript

```javascript
// This is a comment

// Output to console
console.log('Hello, JavaScript!');

// Basic math
console.log(2 + 2);    // 4
console.log(10 / 3);   // 3.3333...
console.log(2 ** 8);   // 256 (exponentiation)

// String
console.log('My name is Alex');

// Boolean
console.log(true);
console.log(5 > 3);    // true
console.log(5 < 3);    // false
```

---

## Common Mistakes

- Forgetting semicolons (optional but consistent style matters)
- Using `console.log` in production code (remove before deploying)
- Not opening DevTools to see errors — always check the console
- Confusing `=` (assignment) with `==` (comparison) and `===` (strict comparison)
