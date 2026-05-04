# Assignment — Utility-First Rebuild

## What You Are Building

Take a provided traditional CSS component and rebuild it using only Tailwind utility classes. This forces you to map CSS properties to Tailwind utilities and proves you understand the utility-first approach.

---

## Requirements

Create `utility-rebuild.html` that contains **both** versions side by side:

### Left Side — Traditional CSS Version (provided)

Use this exact HTML and CSS as-is:

```html
<style>
  .profile-card {
    background: white;
    border-radius: 16px;
    padding: 2rem;
    box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    max-width: 300px;
    text-align: center;
  }
  .profile-card .avatar {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background: linear-gradient(135deg, #3b82f6, #8b5cf6);
    margin: 0 auto 1rem;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 2rem;
    font-weight: bold;
  }
  .profile-card h2 { font-size: 1.25rem; font-weight: 700; margin-bottom: 0.25rem; }
  .profile-card .role { color: #6b7280; font-size: 0.875rem; margin-bottom: 1rem; }
  .profile-card .follow-btn {
    background: #3b82f6;
    color: white;
    border: none;
    padding: 0.5rem 1.5rem;
    border-radius: 9999px;
    font-weight: 600;
    cursor: pointer;
    font-size: 0.875rem;
  }
</style>

<div class="profile-card">
  <div class="avatar">JD</div>
  <h2>Jordan Davis</h2>
  <p class="role">UI Designer</p>
  <button class="follow-btn">Follow</button>
</div>
```

### Right Side — Tailwind Rebuild

Recreate the exact same visual result using only Tailwind utility classes. No `<style>` block allowed for the Tailwind version.

---

## Utility Mapping Hints

| CSS Property | Tailwind Class |
|---|---|
| `background: white` | `bg-white` |
| `border-radius: 16px` | `rounded-2xl` |
| `padding: 2rem` | `p-8` |
| `box-shadow: 0 4px 20px ...` | `shadow-lg` |
| `max-width: 300px` | `max-w-xs` |
| `text-align: center` | `text-center` |
| `width: 80px; height: 80px` | `w-20 h-20` |
| `border-radius: 50%` | `rounded-full` |
| `font-size: 1.25rem` | `text-xl` |
| `font-weight: 700` | `font-bold` |
| `color: #6b7280` | `text-gray-500` |
| `border-radius: 9999px` | `rounded-full` |

---

## What Good Looks Like

- Both cards look visually identical
- The Tailwind version has zero lines of custom CSS
- Class names are readable and make sense
- The gradient avatar uses `bg-gradient-to-br from-blue-500 to-purple-500`

---

## Submission

Submit `utility-rebuild.html`.
