# Class Work — Form Validation in Practice

## What You Will Build

A login and signup form with real-time validation, showing how to use `input`, `blur`, `focus`, and `submit` events together.

**Time:** 35 minutes  
**Output:** `form-validation-practice.html`

---

## Step 1 — Create the File

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Form Validation Practice</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: sans-serif; background: #f8f9fa; color: #333; padding: 2rem; display: flex; gap: 2rem; flex-wrap: wrap; }
    h1 { width: 100%; margin-bottom: 1rem; }
    .form-card { background: white; border: 1px solid #dee2e6; border-radius: 12px; padding: 2rem; flex: 1; min-width: 300px; max-width: 420px; }
    .form-card h2 { font-size: 1.3rem; margin-bottom: 1.5rem; }
    .form-group { margin-bottom: 1.25rem; }
    label { display: block; font-size: 0.85rem; font-weight: 600; margin-bottom: 0.3rem; color: #555; }
    input { width: 100%; padding: 0.6rem 0.75rem; border: 2px solid #dee2e6; border-radius: 6px; font-size: 0.9rem; outline: none; transition: border-color 0.2s; }
    input:focus { border-color: #3498db; }
    input.valid { border-color: #27ae60; }
    input.invalid { border-color: #e74c3c; }
    .hint { font-size: 0.78rem; margin-top: 0.25rem; min-height: 1.2em; }
    .hint.success { color: #27ae60; }
    .hint.error { color: #e74c3c; }
    .btn { width: 100%; padding: 0.75rem; background: #3498db; color: white; border: none; border-radius: 6px; cursor: pointer; font-size: 0.95rem; font-weight: 600; font-family: inherit; transition: background 0.2s; }
    .btn:hover { background: #2980b9; }
    .btn:disabled { background: #bdc3c7; cursor: not-allowed; }
    .result { margin-top: 1rem; padding: 0.75rem 1rem; border-radius: 6px; font-size: 0.9rem; display: none; }
    .result.success { background: #d4edda; color: #155724; border: 1px solid #c3e6cb; }
    .result.error { background: #f8d7da; color: #721c24; border: 1px solid #f5c6cb; }
    .strength-bar { height: 6px; border-radius: 999px; background: #f0f0f0; margin-top: 0.5rem; overflow: hidden; }
    .strength-fill { height: 100%; border-radius: 999px; transition: width 0.3s, background 0.3s; width: 0%; }
    .strength-label { font-size: 0.75rem; margin-top: 0.25rem; }
  </style>
</head>
<body>
  <h1>Form Validation Practice</h1>
  <!-- forms go here -->
  <script>
    // JavaScript goes here
  </script>
</body>
</html>
```

---

## Step 2 — Login Form

Add this HTML before `<script>`:

```html
<div class="form-card">
  <h2>Login</h2>
  <form id="login-form">
    <div class="form-group">
      <label for="login-email">Email</label>
      <input type="email" id="login-email" placeholder="your@email.com">
      <div class="hint" id="login-email-hint"></div>
    </div>
    <div class="form-group">
      <label for="login-password">Password</label>
      <input type="password" id="login-password" placeholder="Your password">
      <div class="hint" id="login-password-hint"></div>
    </div>
    <button type="submit" class="btn">Sign In</button>
    <div class="result" id="login-result"></div>
  </form>
</div>
```

Add this JavaScript:

```javascript
// Validation helpers
function validateEmail(email) {
  return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
}

function setFieldState(inputId, hintId, isValid, message) {
  const input = document.getElementById(inputId);
  const hint = document.getElementById(hintId);
  input.className = isValid ? 'valid' : 'invalid';
  hint.textContent = message;
  hint.className = `hint ${isValid ? 'success' : 'error'}`;
  return isValid;
}

// Login form
const loginEmail = document.getElementById('login-email');
const loginPassword = document.getElementById('login-password');

loginEmail.addEventListener('input', () => {
  const val = loginEmail.value.trim();
  if (!val) { loginEmail.className = ''; document.getElementById('login-email-hint').textContent = ''; return; }
  setFieldState('login-email', 'login-email-hint', validateEmail(val),
    validateEmail(val) ? '✓ Valid email' : 'Please enter a valid email address');
});

loginPassword.addEventListener('input', () => {
  const val = loginPassword.value;
  if (!val) { loginPassword.className = ''; document.getElementById('login-password-hint').textContent = ''; return; }
  setFieldState('login-password', 'login-password-hint', val.length >= 6,
    val.length >= 6 ? '✓ Password entered' : 'Password must be at least 6 characters');
});

document.getElementById('login-form').addEventListener('submit', (e) => {
  e.preventDefault();
  const emailValid = setFieldState('login-email', 'login-email-hint',
    validateEmail(loginEmail.value.trim()), validateEmail(loginEmail.value.trim()) ? '✓ Valid' : 'Invalid email');
  const passValid = setFieldState('login-password', 'login-password-hint',
    loginPassword.value.length >= 6, loginPassword.value.length >= 6 ? '✓ OK' : 'Too short');

  const result = document.getElementById('login-result');
  result.style.display = 'block';
  if (emailValid && passValid) {
    result.className = 'result success';
    result.textContent = `✅ Logged in as ${loginEmail.value}`;
  } else {
    result.className = 'result error';
    result.textContent = '❌ Please fix the errors above.';
  }
});
```

---

## Step 3 — Signup Form with Password Strength

Add this HTML:

```html
<div class="form-card">
  <h2>Sign Up</h2>
  <form id="signup-form">
    <div class="form-group">
      <label for="signup-name">Full Name</label>
      <input type="text" id="signup-name" placeholder="Alex Rivera">
      <div class="hint" id="signup-name-hint"></div>
    </div>
    <div class="form-group">
      <label for="signup-email">Email</label>
      <input type="email" id="signup-email" placeholder="your@email.com">
      <div class="hint" id="signup-email-hint"></div>
    </div>
    <div class="form-group">
      <label for="signup-password">Password</label>
      <input type="password" id="signup-password" placeholder="Create a strong password">
      <div class="strength-bar"><div class="strength-fill" id="strength-fill"></div></div>
      <div class="strength-label" id="strength-label"></div>
    </div>
    <div class="form-group">
      <label for="signup-confirm">Confirm Password</label>
      <input type="password" id="signup-confirm" placeholder="Repeat your password">
      <div class="hint" id="signup-confirm-hint"></div>
    </div>
    <button type="submit" class="btn">Create Account</button>
    <div class="result" id="signup-result"></div>
  </form>
</div>
```

Add this JavaScript:

```javascript
// Name validation
document.getElementById('signup-name').addEventListener('input', (e) => {
  const val = e.target.value.trim();
  if (!val) { e.target.className = ''; return; }
  const valid = val.length >= 2 && val.includes(' ');
  setFieldState('signup-name', 'signup-name-hint', valid,
    valid ? '✓ Full name looks good' : 'Please enter your first and last name');
});

// Email validation
document.getElementById('signup-email').addEventListener('input', (e) => {
  const val = e.target.value.trim();
  if (!val) { e.target.className = ''; return; }
  setFieldState('signup-email', 'signup-email-hint', validateEmail(val),
    validateEmail(val) ? '✓ Valid email' : 'Invalid email format');
});

// Password strength
document.getElementById('signup-password').addEventListener('input', (e) => {
  const val = e.target.value;
  const fill = document.getElementById('strength-fill');
  const label = document.getElementById('strength-label');

  const checks = {
    length: val.length >= 8,
    upper: /[A-Z]/.test(val),
    lower: /[a-z]/.test(val),
    number: /\d/.test(val),
    special: /[!@#$%^&*]/.test(val),
  };

  const score = Object.values(checks).filter(Boolean).length;
  const levels = [
    { pct: 0, color: '#f0f0f0', text: '' },
    { pct: 20, color: '#e74c3c', text: 'Weak' },
    { pct: 40, color: '#e67e22', text: 'Fair' },
    { pct: 70, color: '#f39c12', text: 'Good' },
    { pct: 90, color: '#27ae60', text: 'Strong' },
    { pct: 100, color: '#1e8449', text: 'Very Strong' },
  ];

  const level = val.length === 0 ? levels[0] : levels[Math.min(score, 5)];
  fill.style.width = level.pct + '%';
  fill.style.background = level.color;
  label.textContent = level.text;
  label.style.color = level.color;

  // Also check confirm password
  const confirm = document.getElementById('signup-confirm').value;
  if (confirm) {
    setFieldState('signup-confirm', 'signup-confirm-hint', val === confirm,
      val === confirm ? '✓ Passwords match' : 'Passwords do not match');
  }
});

// Confirm password
document.getElementById('signup-confirm').addEventListener('input', (e) => {
  const password = document.getElementById('signup-password').value;
  const val = e.target.value;
  if (!val) { e.target.className = ''; return; }
  setFieldState('signup-confirm', 'signup-confirm-hint', val === password,
    val === password ? '✓ Passwords match' : 'Passwords do not match');
});

// Signup submit
document.getElementById('signup-form').addEventListener('submit', (e) => {
  e.preventDefault();
  const name = document.getElementById('signup-name').value.trim();
  const email = document.getElementById('signup-email').value.trim();
  const password = document.getElementById('signup-password').value;
  const confirm = document.getElementById('signup-confirm').value;

  const errors = [];
  if (!name || !name.includes(' ')) errors.push('Full name required');
  if (!validateEmail(email)) errors.push('Valid email required');
  if (password.length < 8) errors.push('Password must be 8+ characters');
  if (password !== confirm) errors.push('Passwords must match');

  const result = document.getElementById('signup-result');
  result.style.display = 'block';
  if (errors.length === 0) {
    result.className = 'result success';
    result.textContent = `✅ Account created for ${name}!`;
  } else {
    result.className = 'result error';
    result.textContent = '❌ ' + errors.join(', ');
  }
});
```

---

## Checklist

- [ ] Login form validates email format in real time
- [ ] Login form shows error on submit if fields are invalid
- [ ] Signup name requires first and last name (space check)
- [ ] Password strength bar updates in real time
- [ ] Confirm password shows match/mismatch in real time
- [ ] Both forms use `e.preventDefault()` — no page reload
- [ ] Success message shows on valid submission

---

## Bonus Challenges

1. Add a "Show/Hide Password" toggle button
2. Add a username field with async validation (simulate checking if username is taken with `setTimeout`)
3. Add a phone number field with format validation
