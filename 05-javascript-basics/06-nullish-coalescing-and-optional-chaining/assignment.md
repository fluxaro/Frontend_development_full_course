# Assignment — Safe Data Access

## What You Are Building

A user profile display that safely handles missing or null data using `?.` and `??`.

---

## Requirements

Create `safe-access.html` with:

### User Objects
Create 3 user objects with varying levels of completeness:
- `fullUser` — all properties filled
- `partialUser` — some nested properties missing
- `emptyUser = null`

### Display Function
Write `displayUser(user)` that safely accesses:
- `user?.name ?? 'Anonymous'`
- `user?.profile?.bio ?? 'No bio provided'`
- `user?.address?.city ?? 'Location unknown'`
- `user?.scores?.[0] ?? 0`
- `user?.getGreeting?.() ?? 'Hello!'`

### ?? vs || Comparison
Show a table comparing `??` and `||` for values: `0`, `''`, `false`, `null`, `undefined`

---

## Submission

Submit `safe-access.html`.
