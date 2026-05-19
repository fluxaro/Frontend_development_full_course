# 30 — Fetch API: POST, PUT, DELETE

## What Is This Lesson About?

Beyond GET requests, the Fetch API supports all HTTP methods for creating, updating, and deleting data.

---

## POST — Create Data

```javascript
async function createUser(userData) {
  const response = await fetch('https://api.example.com/users', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
    },
    body: JSON.stringify(userData),
  });

  if (!response.ok) throw new Error(`HTTP ${response.status}`);
  return response.json();
}

const newUser = await createUser({ name: 'Alex', email: 'alex@example.com' });
```

---

## PUT — Replace Data

```javascript
async function updateUser(id, userData) {
  const response = await fetch(`https://api.example.com/users/${id}`, {
    method: 'PUT',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(userData),
  });
  return response.json();
}
```

---

## PATCH — Partial Update

```javascript
async function patchUser(id, changes) {
  const response = await fetch(`https://api.example.com/users/${id}`, {
    method: 'PATCH',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(changes), // only the fields to update
  });
  return response.json();
}
```

---

## DELETE — Remove Data

```javascript
async function deleteUser(id) {
  const response = await fetch(`https://api.example.com/users/${id}`, {
    method: 'DELETE',
  });

  if (!response.ok) throw new Error(`HTTP ${response.status}`);
  return true;
}
```

---

## HTTP Methods Summary

| Method | Purpose | Has Body |
|---|---|---|
| GET | Read data | ❌ |
| POST | Create data | ✅ |
| PUT | Replace data | ✅ |
| PATCH | Partial update | ✅ |
| DELETE | Remove data | Optional |

---

## Common Mistakes

- Forgetting `Content-Type: application/json` header on POST/PUT
- Forgetting `JSON.stringify(body)` — body must be a string
- Using POST when PATCH is more appropriate (partial updates)
- Not handling the response from DELETE (some APIs return 204 No Content)
