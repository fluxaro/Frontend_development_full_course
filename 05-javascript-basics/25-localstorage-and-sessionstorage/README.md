# 25 — localStorage and sessionStorage

## What Is This Lesson About?

Web Storage lets you save data in the browser. `localStorage` persists until cleared; `sessionStorage` clears when the tab closes.

---

## localStorage

```javascript
// Store data (values must be strings)
localStorage.setItem('username', 'Alex');
localStorage.setItem('theme', 'dark');

// Retrieve data
const username = localStorage.getItem('username'); // 'Alex'
const missing = localStorage.getItem('nothing');   // null

// Remove one item
localStorage.removeItem('username');

// Clear all
localStorage.clear();

// Check length
localStorage.length;
```

---

## Storing Objects (JSON)

localStorage only stores strings. Use `JSON.stringify` and `JSON.parse`:

```javascript
const user = { name: 'Alex', age: 25, theme: 'dark' };

// Save
localStorage.setItem('user', JSON.stringify(user));

// Load
const saved = localStorage.getItem('user');
const user = saved ? JSON.parse(saved) : null;
```

---

## sessionStorage

Same API as localStorage, but data is cleared when the tab/window closes:

```javascript
sessionStorage.setItem('token', 'abc123');
sessionStorage.getItem('token');
sessionStorage.removeItem('token');
sessionStorage.clear();
```

---

## localStorage vs sessionStorage vs Cookies

| | localStorage | sessionStorage | Cookies |
|---|---|---|---|
| Expires | Never | Tab close | Set expiry |
| Size | ~5MB | ~5MB | ~4KB |
| Sent to server | ❌ | ❌ | ✅ |
| Accessible from JS | ✅ | ✅ | ✅ |

---

## Practical Pattern

```javascript
// Save user preferences
function savePreferences(prefs) {
  localStorage.setItem('prefs', JSON.stringify(prefs));
}

// Load with fallback
function loadPreferences() {
  const saved = localStorage.getItem('prefs');
  return saved ? JSON.parse(saved) : { theme: 'light', lang: 'en' };
}
```

---

## Common Mistakes

- Storing objects without `JSON.stringify` (stores `[object Object]`)
- Not handling `null` from `getItem` (item doesn't exist)
- Storing sensitive data (passwords, tokens) in localStorage — it's not secure
- Not wrapping `JSON.parse` in try/catch (corrupted data throws)
