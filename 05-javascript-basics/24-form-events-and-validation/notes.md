# Notes — Form Events and Validation

## Form Events

```javascript
const form = document.querySelector('form');
const input = document.querySelector('input');

// submit — fires when form is submitted (button click or Enter key)
form.addEventListener('submit', (e) => {
  e.preventDefault(); // ALWAYS prevent default to stop page reload
  const data = new FormData(form);
  console.log(Object.fromEntries(data));
});

// input — fires on EVERY keystroke (real-time)
input.addEventListener('input', (e) => {
  console.log('Current value:', e.target.value);
  console.log('Length:', e.target.value.length);
});

// change — fires when value changes AND element loses focus
input.addEventListener('change', (e) => {
  console.log('Final value:', e.target.value);
});

// focus — element gains focus (user clicks or tabs to it)
input.addEventListener('focus', (e) => {
  e.target.parentElement.classList.add('focused');
});

// blur — element loses focus (user clicks away or tabs out)
input.addEventListener('blur', (e) => {
  e.target.parentElement.classList.remove('focused');
  validateField(e.target); // validate when user leaves the field
});
```

## Reading Form Values

```javascript
// Text, email, password, number inputs
input.value;                    // current value as string
input.value.trim();             // trimmed value

// Checkbox
checkbox.checked;               // true/false

// Radio buttons
document.querySelector('input[name="gender"]:checked')?.value;

// Select
select.value;                   // selected option value
select.options[select.selectedIndex].text; // selected option text

// Multiple select
[...select.selectedOptions].map(o => o.value);

// FormData — all fields at once
const data = new FormData(form);
data.get('email');              // get one field
data.getAll('tags');            // get multiple values (checkboxes)
Object.fromEntries(data);       // convert to plain object
```

## Validation Patterns

```javascript
// Required field
function validateRequired(value) {
  return value.trim() !== '';
}

// Email
function validateEmail(email) {
  return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
}

// Password strength
function validatePassword(password) {
  return {
    length: password.length >= 8,
    uppercase: /[A-Z]/.test(password),
    lowercase: /[a-z]/.test(password),
    number: /\d/.test(password),
    special: /[!@#$%^&*]/.test(password),
  };
}

// Phone (basic)
function validatePhone(phone) {
  return /^\+?[\d\s\-()]{10,}$/.test(phone);
}

// URL
function validateURL(url) {
  try { new URL(url); return true; }
  catch { return false; }
}
```

## Showing Validation Feedback

```javascript
function showError(input, message) {
  input.classList.add('invalid');
  input.classList.remove('valid');
  const hint = input.nextElementSibling;
  if (hint) { hint.textContent = message; hint.className = 'hint error'; }
}

function showSuccess(input) {
  input.classList.add('valid');
  input.classList.remove('invalid');
  const hint = input.nextElementSibling;
  if (hint) { hint.textContent = '✓ Looks good!'; hint.className = 'hint success'; }
}
```

## Common Mistakes

- Forgetting `e.preventDefault()` on submit (page reloads)
- Using `change` when you want real-time feedback (use `input` instead)
- Not trimming whitespace before validation
- Relying only on client-side validation (always validate on the server too)
- Using `keypress` (deprecated) instead of `keydown` for keyboard events
