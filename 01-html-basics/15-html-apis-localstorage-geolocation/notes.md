# Notes — HTML APIs: localStorage, sessionStorage, Geolocation

## localStorage Cheat Sheet

```javascript
// Set
localStorage.setItem('key', 'value');
localStorage.setItem('user', JSON.stringify({ name: 'Alex' }));

// Get
localStorage.getItem('key');                          // 'value'
JSON.parse(localStorage.getItem('user'));             // { name: 'Alex' }

// Remove
localStorage.removeItem('key');

// Clear all
localStorage.clear();

// Check if exists
localStorage.getItem('key') !== null

// Get all keys
Object.keys(localStorage)
```

## sessionStorage Cheat Sheet

Same API as localStorage:
```javascript
sessionStorage.setItem('key', 'value');
sessionStorage.getItem('key');
sessionStorage.removeItem('key');
sessionStorage.clear();
```

## Geolocation Cheat Sheet

```javascript
// One-time position
navigator.geolocation.getCurrentPosition(
  (pos) => {
    console.log(pos.coords.latitude, pos.coords.longitude);
  },
  (err) => console.error(err.message)
);

// Watch position
const id = navigator.geolocation.watchPosition(callback);
navigator.geolocation.clearWatch(id);
```

## localStorage vs sessionStorage

| | localStorage | sessionStorage |
|---|---|---|
| Persists after close? | Yes | No |
| Shared between tabs? | Yes | No |
| Limit | ~5–10 MB | ~5 MB |

## Common Mistakes

- Storing objects without JSON.stringify (stores "[object Object]")
- Forgetting JSON.parse when reading objects
- Storing sensitive data (passwords, tokens) in localStorage
- Not handling the case where localStorage is null (first visit)
- Not wrapping in try/catch (localStorage can be disabled)

## Safe localStorage Pattern

```javascript
function getItem(key, defaultValue) {
  try {
    const item = localStorage.getItem(key);
    return item ? JSON.parse(item) : defaultValue;
  } catch (e) {
    return defaultValue;
  }
}

function setItem(key, value) {
  try {
    localStorage.setItem(key, JSON.stringify(value));
  } catch (e) {
    console.error('localStorage not available');
  }
}
```
