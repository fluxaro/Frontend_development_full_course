# Assignment — Smart Form with Modern Selectors

## What You Are Building

Create a smart form that uses :has() for real-time validation feedback without JavaScript.

---

## Requirements

Create `smart-form.html` and `smart-form.css` with:

### Form Fields

- Name (text, required, minlength 2)
- Email (email, required)
- Password (password, required, minlength 8)
- Confirm password (password, required)
- Country (select, required)
- Bio (textarea, optional)

### :has() Behaviors

- Field wrapper turns green when input is valid
- Field wrapper turns red when input is invalid (after typing)
- Label changes color based on field state
- Submit button is styled differently when form has any invalid field
- Form shows a success message when all fields are valid

### :is() and :where()

- Use `:is()` to group heading styles
- Use `:where()` for default link styles that are easy to override
- Use `:not()` to exclude the optional bio field from required styling

---

## Submission

Submit `smart-form.html` and `smart-form.css`.
