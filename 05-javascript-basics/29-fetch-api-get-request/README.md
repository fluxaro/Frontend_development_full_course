# 29 — Fetch API: GET Request

## What Is This Lesson About?

The Fetch API is the modern way to make HTTP requests from JavaScript. It returns Promises and works with any REST API.

---

## Basic GET Request

```javascript
fetch('https://jsonplaceholder.typicode.com/users')
  .then(response => {
    if (!response.ok) {
      throw new Error(`HTTP error: ${response.status}`);
    }
    return response.json(); // parse JSON body
  })
  .then(data => {
    console.log(data); // array of users
  })
  .catch(error => {
    console.error('Fetch failed:', error);
  });
```

---

## With async/await (preferred)

```javascript
async function getUsers() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/users');

    if (!response.ok) {
      throw new Error(`HTTP ${response.status}: ${response.statusText}`);
    }

    const users = await response.json();
    return users;
  } catch (error) {
    console.error('Error:', error.message);
    return [];
  }
}

const users = await getUsers();
```

---

## The Response Object

```javascript
response.ok;          // true if status 200-299
response.status;      // 200, 404, 500, etc.
response.statusText;  // 'OK', 'Not Found', etc.
response.headers;     // response headers
response.url;         // final URL (after redirects)

// Body parsing methods (each returns a Promise)
response.json();      // parse as JSON
response.text();      // parse as plain text
response.blob();      // parse as binary (images, files)
```

---

## Query Parameters

```javascript
const params = new URLSearchParams({
  page: 1,
  limit: 10,
  search: 'alex',
});

fetch(`https://api.example.com/users?${params}`)
  .then(r => r.json())
  .then(data => console.log(data));
```

---

## Common Mistakes

- Not checking `response.ok` — fetch only rejects on network errors, not 4xx/5xx
- Forgetting to `await response.json()` (it returns a Promise)
- Not handling errors with try/catch or `.catch()`
- Calling `response.json()` twice (body can only be read once)
