# 15 — HTML APIs: localStorage, sessionStorage, and Geolocation

## What Is This Lesson About?

Modern browsers expose powerful APIs that you can use directly from HTML and JavaScript. This lesson covers the three most commonly used browser APIs: localStorage, sessionStorage, and the Geolocation API.

---

## localStorage

localStorage lets you store data in the browser that persists even after the browser is closed. The data stays until you explicitly delete it.

```javascript
// Store data
localStorage.setItem('username', 'alex');
localStorage.setItem('theme', 'dark');

// Retrieve data
const username = localStorage.getItem('username');  // 'alex'

// Remove one item
localStorage.removeItem('username');

// Clear all items
localStorage.clear();

// Check if item exists
if (localStorage.getItem('theme')) {
  // theme is set
}
```

### Storing Objects

localStorage only stores strings. Use JSON to store objects:

```javascript
// Store an object
const user = { name: 'Alex', age: 25 };
localStorage.setItem('user', JSON.stringify(user));

// Retrieve an object
const storedUser = JSON.parse(localStorage.getItem('user'));
console.log(storedUser.name);  // 'Alex'
```

---

## sessionStorage

sessionStorage works exactly like localStorage, but the data is cleared when the browser tab is closed.

```javascript
sessionStorage.setItem('cart', JSON.stringify(cartItems));
const cart = JSON.parse(sessionStorage.getItem('cart'));
```

---

## localStorage vs sessionStorage

| Feature | localStorage | sessionStorage |
|---|---|---|
| Persists after tab close? | Yes | No |
| Persists after browser close? | Yes | No |
| Shared between tabs? | Yes | No |
| Storage limit | ~5–10 MB | ~5 MB |
| Use for | User preferences, saved data | Temporary session data |

---

## Geolocation API

The Geolocation API lets you get the user's current location. The browser always asks for permission first.

```javascript
// Get current position
navigator.geolocation.getCurrentPosition(
  function(position) {
    const lat = position.coords.latitude;
    const lng = position.coords.longitude;
    console.log(`Latitude: ${lat}, Longitude: ${lng}`);
  },
  function(error) {
    console.error('Error:', error.message);
  }
);

// Watch position (updates as user moves)
const watchId = navigator.geolocation.watchPosition(
  function(position) {
    // Called every time position changes
  }
);

// Stop watching
navigator.geolocation.clearWatch(watchId);
```

---

## Other Browser APIs

| API | Purpose |
|---|---|
| `localStorage` | Persistent key-value storage |
| `sessionStorage` | Session-only key-value storage |
| `navigator.geolocation` | User's location |
| `navigator.clipboard` | Copy/paste |
| `navigator.share` | Native share dialog |
| `Notification` | Browser notifications |
| `IndexedDB` | Large structured data storage |
| `Cache API` | Cache network requests (Service Workers) |
| `navigator.onLine` | Check internet connection |
| `window.history` | Browser history navigation |

---

## Security and Privacy

- localStorage data is accessible to any JavaScript on the same domain
- Never store passwords, tokens, or sensitive data in localStorage
- Geolocation requires explicit user permission
- HTTPS is required for Geolocation API
