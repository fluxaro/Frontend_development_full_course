# Notes — Introduction to JavaScript and the Console

## Adding JS to HTML

```html
<!-- External (recommended) -->
<script src="app.js" defer></script>

<!-- Internal -->
<script>
  console.log('hello');
</script>
```

## Console Methods

```javascript
console.log('message');          // general output
console.error('error message');  // red
console.warn('warning');         // yellow
console.table(array);            // table view
console.group('label');          // collapsible group
console.groupEnd();
console.time('label');           // start timer
console.timeEnd('label');        // stop timer
console.clear();                 // clear console
```

## Open DevTools Console

| OS | Shortcut |
|---|---|
| Mac | Cmd + Option + J |
| Windows | Ctrl + Shift + J |

## Comments

```javascript
// Single line comment

/*
  Multi-line
  comment
*/
```

## Common Mistakes

- Not checking the console for errors
- Using `=` instead of `===` for comparison
- Forgetting `defer` on script tags (script runs before DOM is ready)
- Leaving `console.log` in production code
