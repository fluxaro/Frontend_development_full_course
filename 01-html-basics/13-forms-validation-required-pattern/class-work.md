# Class Work — Build a Validated Sign-Up Form

## What You Will Build

A sign-up form with full HTML5 validation — required fields, length limits, pattern matching, and CSS feedback for valid/invalid states.

**Time:** 40 minutes

---

## Step 1 — Set Up the Page

Create a file called `signup-form.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sign Up</title>
    <style>
      /* Validation feedback styles */
      input:valid { border: 2px solid green; }
      input:invalid:not(:placeholder-shown) { border: 2px solid red; }
      input:required { border-left: 4px solid orange; }
    </style>
  </head>
  <body>
    <h1>Create Account</h1>
  </body>
</html>
```

---

## Step 2 — Username Field with Pattern

```html
<form action="/signup" method="POST" novalidate>

  <div>
    <label for="username">Username *</label>
    <input
      type="text"
      id="username"
      name="username"
      required
      minlength="3"
      maxlength="20"
      pattern="[A-Za-z0-9_]+"
      title="3–20 characters. Letters, numbers, and underscores only."
      placeholder="e.g. john_doe123"
    >
    <small>3–20 characters. Letters, numbers, and underscores only.</small>
  </div>
```

**Test it:** Try submitting with:
- An empty field (required error)
- "ab" (too short — minlength error)
- "john doe" (space not allowed — pattern error)
- "john_doe123" (valid)

---

## Step 3 — Email Field

```html
  <div>
    <label for="email">Email Address *</label>
    <input
      type="email"
      id="email"
      name="email"
      required
      placeholder="you@example.com"
    >
    <small>We will never share your email.</small>
  </div>
```

**Test it:** Try submitting with:
- "notanemail" (invalid format)
- "test@" (incomplete)
- "test@example.com" (valid)

---

## Step 4 — Password with Pattern

```html
  <div>
    <label for="password">Password *</label>
    <input
      type="password"
      id="password"
      name="password"
      required
      minlength="8"
      pattern="(?=.*[A-Z])(?=.*[0-9]).{8,}"
      title="At least 8 characters, including one uppercase letter and one number."
    >
    <small>At least 8 characters, one uppercase letter, one number.</small>
  </div>
```

---

## Step 5 — Age with min/max

```html
  <div>
    <label for="age">Age *</label>
    <input
      type="number"
      id="age"
      name="age"
      required
      min="18"
      max="120"
      title="You must be at least 18 years old."
    >
    <small>Must be 18 or older.</small>
  </div>
```

---

## Step 6 — Phone with Pattern

```html
  <div>
    <label for="phone">Phone Number</label>
    <input
      type="tel"
      id="phone"
      name="phone"
      pattern="\+?[\d\s\-\(\)]{7,15}"
      title="Enter a valid phone number (7–15 digits)."
      placeholder="+1 555 000 0000"
    >
    <small>Optional. Include country code for international numbers.</small>
  </div>
```

---

## Step 7 — Date with max

```html
  <div>
    <label for="dob">Date of Birth *</label>
    <input
      type="date"
      id="dob"
      name="date_of_birth"
      required
      max="2007-01-01"
      title="You must be at least 18 years old."
    >
  </div>
```

---

## Step 8 — Website URL

```html
  <div>
    <label for="website">Website</label>
    <input
      type="url"
      id="website"
      name="website"
      placeholder="https://yourwebsite.com"
      title="Enter a valid URL starting with https://"
    >
  </div>
```

---

## Step 9 — Terms Checkbox (required)

```html
  <div>
    <input type="checkbox" id="terms" name="terms" required>
    <label for="terms">I agree to the Terms of Service *</label>
  </div>

  <div>
    <button type="submit">Create Account</button>
    <button type="reset">Clear</button>
  </div>

</form>
```

---

## Step 10 — Test All Validation

Try submitting the form with:
1. All fields empty — what errors appear?
2. Invalid email format — what happens?
3. Password without uppercase — what happens?
4. Age below 18 — what happens?
5. All fields valid — does it submit?

---

## Checklist

- [ ] `required` on all required fields
- [ ] `minlength`/`maxlength` on text fields
- [ ] `pattern` on username, password, and phone
- [ ] `min`/`max` on age and date
- [ ] `type="email"` validates email format
- [ ] `type="url"` validates URL format
- [ ] `title` attribute provides helpful error messages
- [ ] CSS `:valid` and `:invalid` styles applied
