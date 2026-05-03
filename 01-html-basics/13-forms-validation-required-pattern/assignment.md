# Assignment — Fully Validated Sign-Up Form

## What You Are Building

Create an HTML page called `signup-form.html` — a complete sign-up form with full HTML5 validation on every field.

---

## Requirements

### Form Fields (all required unless noted)

1. **Username** — required, 3–20 characters, letters/numbers/underscores only (pattern)
2. **Email** — required, valid email format (type="email")
3. **Password** — required, min 8 characters, must contain at least one uppercase letter and one number (pattern)
4. **Confirm Password** — required, min 8 characters
5. **Age** — required, number, min 18, max 120
6. **Date of Birth** — required, date, max must be 18 years ago
7. **Phone** — optional, pattern for valid phone number
8. **Website** — optional, type="url"
9. **Country** — required, select with at least 5 options
10. **Bio** — optional, textarea, maxlength 300
11. **Terms checkbox** — required

### Validation Requirements

Every field must have:
- Appropriate `type` attribute
- `required` where applicable
- `minlength`/`maxlength` where applicable
- `min`/`max` where applicable
- `pattern` where applicable
- `title` attribute with a helpful error message
- `placeholder` with an example value

### CSS Validation Feedback

Add a `<style>` block with:
- Green border for `:valid` inputs
- Red border for `:invalid` inputs that have been touched (use `:not(:placeholder-shown)`)
- Orange left border for `:required` inputs

---

## What Good Looks Like

- Every field validates correctly
- Error messages (via `title`) are helpful and specific
- The form cannot be submitted with invalid data
- The CSS feedback is visible as you type
- The page passes W3C validation

---

## Bonus Challenges

- Add `aria-describedby` pointing to hint text for each field
- Add `autocomplete` attributes to all relevant fields
- Add a `<datalist>` for the country field
- Add a password strength indicator using only HTML (no JS)

---

## Submission

Save as `signup-form.html` and submit via GitHub.
