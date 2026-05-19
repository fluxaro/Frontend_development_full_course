# 24 — Form Events and Validation

## What Is This Lesson About?

Forms are the primary way users input data. JavaScript lets you intercept form submission, validate inputs, and provide real-time feedback.

---

## Form Events

```javascript
const form = document.querySelector('form');
const input = document.querySelector('input');

// submit — fires when form is submitted
form.addEventListener('submit', (e) => {
  e.preventDefault(); // prevent page reload
  const data = new FormData(form);
  console.log(Object.fromEntries(data));
});

// input — fires on every keystroke
input.addEventListener('input', (e) => {
  console.log('Current value:', e.target.value);
});

// change — fires when value changes and element loses focus
input.addEventListener('change', (e) => {
  console.log('Changed to:', e.target.value);
});

// focus / blur
input.addEventListener('focus', () => input.classList.add('focused'));
input.addEventListener('blur', () => input.classList.remove('focused'));
```

---

## Reading Form Values

```javascript
// Text inputs
input.value;

// Checkbox
checkbox.checked; // true/false

// Radio buttons
document.querySelector('input[name="gender"]:checked')?.value;

// Select
select.value;
select.options[select.selectedIndex].text;

// FormData (all fields at once)
const data = new FormData(form);
data.get('email');
Object.fromEntries(data); // convert to plain object
```

---

## Validation

```javascript
function validateEmail(email) {
  return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
}

function validateForm(e) {
  e.preventDefault();
  const email = document.querySelector('#email').value;
  const password = document.querySelector('#password').value;
  const errors = [];

  if (!email) errors.push('Email is required');
  else if (!validateEmail(email)) errors.push('Invalid email format');

  if (password.length < 8) errors.push('Password must be at least 8 characters');

  if (errors.length > 0) {
    showErrors(errors);
    return;
  }

  // Submit
  console.log('Form is valid!');
}
```

---

## Common Mistakes

- Forgetting `e.preventDefault()` on submit (page reloads)
- Using `change` when you want real-time feedback (use `input` instead)
- Not trimming whitespace from input values before validation
- Relying only on client-side validation (always validate on the server too)
