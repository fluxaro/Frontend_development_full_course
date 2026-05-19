# Assignment — API Response Handler

## What You Are Building

A page that simulates receiving API responses and uses destructuring to extract and display the data cleanly.

---

## Requirements

Create `api-handler.html` with these simulated API responses:

```javascript
const userResponse = {
  status: 200,
  data: {
    user: {
      id: 42,
      name: 'Alex Rivera',
      email: 'alex@example.com',
      profile: {
        bio: 'Frontend developer',
        avatar: 'https://i.pravatar.cc/100?u=alex',
        location: { city: 'Lagos', country: 'Nigeria' },
      },
      stats: { posts: 24, followers: 1200, following: 340 },
    },
  },
  meta: { requestId: 'req_abc123', timestamp: Date.now() },
};

const postsResponse = {
  status: 200,
  data: {
    posts: [
      { id: 1, title: 'Getting Started with JavaScript', likes: 142, tags: ['js', 'beginner'] },
      { id: 2, title: 'CSS Grid vs Flexbox', likes: 89, tags: ['css', 'layout'] },
      { id: 3, title: 'React Hooks Explained', likes: 203, tags: ['react', 'hooks'] },
    ],
    pagination: { page: 1, perPage: 10, total: 3 },
  },
};
```

### Part 1 — User Profile (object destructuring)

Use destructuring to extract and display:
- `status` from the response
- `name`, `email` from `data.user`
- `bio`, `avatar` from `data.user.profile`
- `city`, `country` from `data.user.profile.location`
- `posts`, `followers`, `following` from `data.user.stats`
- `requestId` from `meta`

All in one destructuring statement (nested).

### Part 2 — Posts List (array + object destructuring)

Use destructuring to:
- Extract `posts` and `pagination` from `postsResponse.data`
- Loop through posts using `for-of` with destructuring
- Display each post's `title`, `likes`, and `tags`
- Show pagination info

### Part 3 — Variable Swap

Show a before/after demo of swapping two variables using array destructuring.

### Part 4 — Function Parameters

Write a `formatPost({ title, likes, tags = [] })` function that uses parameter destructuring and returns a formatted string.

### Part 5 — Default Values

Show examples where destructuring defaults kick in:
- A user with no `bio` (default: 'No bio provided')
- A post with no `tags` (default: `[]`)
- A config with missing keys (defaults for all)

---

## Submission

Submit `api-handler.html`.
