# 28 — Promises: Basics

## What Is This Lesson About?

Promises represent the eventual result of an asynchronous operation. They replace callback hell with a cleaner, chainable syntax.

---

## Promise States

A Promise is always in one of three states:
- **Pending** — initial state, not yet settled
- **Fulfilled** — operation completed successfully
- **Rejected** — operation failed

---

## Creating a Promise

```javascript
const promise = new Promise((resolve, reject) => {
  // async work here
  const success = true;

  if (success) {
    resolve('Data loaded!'); // fulfil with a value
  } else {
    reject(new Error('Something went wrong')); // reject with an error
  }
});
```

---

## Consuming Promises

```javascript
promise
  .then(value => {
    console.log('Success:', value); // 'Data loaded!'
  })
  .catch(error => {
    console.error('Error:', error.message);
  })
  .finally(() => {
    console.log('Always runs'); // cleanup
  });
```

---

## Promise.all — Wait for All

```javascript
const p1 = fetch('/api/users');
const p2 = fetch('/api/posts');

Promise.all([p1, p2])
  .then(([users, posts]) => {
    console.log(users, posts);
  })
  .catch(err => {
    // fails if ANY promise rejects
    console.error(err);
  });
```

---

## Promise.allSettled — Wait for All (no fail)

```javascript
Promise.allSettled([p1, p2, p3])
  .then(results => {
    results.forEach(result => {
      if (result.status === 'fulfilled') console.log(result.value);
      else console.error(result.reason);
    });
  });
```

---

## Promise.race — First to Settle

```javascript
Promise.race([fetch('/api/fast'), fetch('/api/slow')])
  .then(result => console.log('First result:', result));
```

---

## Common Mistakes

- Forgetting `.catch()` — unhandled rejections crash Node.js
- Not returning promises in `.then()` chains (breaks the chain)
- Using `Promise.all` when you want `Promise.allSettled` (one failure kills all)
- Creating unnecessary `new Promise` wrappers around already-promise-returning functions
