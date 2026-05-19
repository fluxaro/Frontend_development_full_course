# 31 — async/await and Error Handling

## What Is This Lesson About?

`async/await` is syntactic sugar over Promises that makes asynchronous code look and behave like synchronous code. Combined with `try/catch`, it provides clean error handling.

---

## async Functions

An `async` function always returns a Promise:

```javascript
async function getData() {
  return 42; // automatically wrapped in Promise.resolve(42)
}

getData().then(console.log); // 42
```

---

## await

`await` pauses execution inside an `async` function until the Promise resolves:

```javascript
async function loadUser(id) {
  const response = await fetch(`/api/users/${id}`);
  const user = await response.json();
  return user;
}
```

---

## Error Handling with try/catch

```javascript
async function loadUser(id) {
  try {
    const response = await fetch(`/api/users/${id}`);

    if (!response.ok) {
      throw new Error(`User not found: ${response.status}`);
    }

    const user = await response.json();
    return user;
  } catch (error) {
    console.error('Failed to load user:', error.message);
    return null;
  } finally {
    console.log('Request complete'); // always runs
  }
}
```

---

## Parallel Requests

```javascript
// Sequential — slow (waits for each)
const user = await getUser(id);
const posts = await getPosts(id);

// Parallel — fast (both start at once)
const [user, posts] = await Promise.all([
  getUser(id),
  getPosts(id),
]);
```

---

## Error Types

```javascript
try {
  const data = await fetchData();
} catch (error) {
  if (error instanceof TypeError) {
    // Network error (no internet, CORS, etc.)
  } else if (error.message.includes('404')) {
    // Not found
  } else {
    // Unknown error
  }
}
```

---

## Common Mistakes

- Using `await` outside an `async` function (SyntaxError)
- Not wrapping `await` in try/catch (unhandled rejection)
- Sequential `await` when parallel `Promise.all` would be faster
- Forgetting that `async` functions always return a Promise
