# 38 — Debugging: Console and Breakpoints

## What Is This Lesson About?

Debugging is the process of finding and fixing bugs. The browser DevTools provide powerful tools: the console for logging, and the debugger for stepping through code line by line.

---

## Console Debugging

```javascript
// Basic logging
console.log('value:', myVar);
console.error('Error:', error);
console.warn('Warning:', message);
console.table(arrayOfObjects);

// Grouping
console.group('API Call');
console.log('URL:', url);
console.log('Response:', data);
console.groupEnd();

// Timing
console.time('operation');
doExpensiveOperation();
console.timeEnd('operation'); // shows ms

// Assertions
console.assert(value > 0, 'Value must be positive', value);

// Styled output
console.log('%cError!', 'color: red; font-size: 20px');
```

---

## The debugger Statement

Pauses execution at that line (only when DevTools is open):

```javascript
function calculateTotal(items) {
  debugger; // execution pauses here
  return items.reduce((sum, item) => sum + item.price, 0);
}
```

---

## DevTools Breakpoints

1. Open DevTools → Sources tab
2. Click a line number to set a breakpoint
3. Reload or trigger the code
4. Execution pauses at the breakpoint

### Breakpoint Controls

| Button | Action |
|---|---|
| ▶ Resume | Continue to next breakpoint |
| ↷ Step over | Run current line, stay in function |
| ↓ Step into | Enter the called function |
| ↑ Step out | Exit current function |

---

## Common Debugging Techniques

```javascript
// 1. Binary search — comment out half the code to isolate the bug
// 2. Log before and after suspicious code
// 3. Check types: console.log(typeof value)
// 4. Check for null/undefined: console.log(value === null, value === undefined)
// 5. Use the Network tab to inspect API calls
// 6. Use the Elements tab to inspect DOM changes
```

---

## Common Mistakes

- Leaving `console.log` in production code
- Not using the debugger — `console.log` everywhere is slower
- Not checking the Network tab for API errors
- Ignoring the red error messages in the console
