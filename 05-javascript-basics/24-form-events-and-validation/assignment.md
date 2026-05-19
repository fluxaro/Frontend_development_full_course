# Assignment — Registration Form with Full Validation

## What You Are Building

A complete user registration form with real-time validation, password strength indicator, and a multi-step form flow.

---

## Requirements

Create `registration-form.html` with:

### Form Fields

1. **First Name** — required, 2–50 characters
2. **Last Name** — required, 2–50 characters
3. **Email** — required, valid email format
4. **Username** — required, 3–20 characters, alphanumeric + underscore only
5. **Password** — required, minimum 8 characters
6. **Confirm Password** — must match password
7. **Date of Birth** — required, must be 13+ years old
8. **Country** — required, select dropdown
9. **Terms** — required checkbox

### Validation Rules

Each field must:
- Show a green checkmark when valid
- Show a red error message when invalid
- Validate in real time on `input` event
- Also validate on `blur` (when user leaves the field)

### Password Strength Indicator

Show a strength bar with 4 levels:
- Weak (red) — less than 8 chars
- Fair (orange) — 8+ chars
- Good (yellow) — 8+ chars + uppercase + number
- Strong (green) — 8+ chars + uppercase + lowercase + number + special char

### Form Submission

On submit:
- Validate all fields
- If any field is invalid, focus the first invalid field and show errors
- If all valid, show a success message with the submitted data (no page reload)

### Multi-Step Flow

Split the form into 2 steps:
- Step 1: Personal info (name, email, username)
- Step 2: Security (password, confirm, DOB, country, terms)
- "Next" button validates step 1 before proceeding
- "Back" button returns to step 1
- Progress indicator shows current step

---

## What Good Looks Like

- All validation rules are enforced
- Password strength updates in real time
- Multi-step navigation works correctly
- Success message shows the submitted data
- No page reload on submit

---

## Submission

Submit `registration-form.html`.
