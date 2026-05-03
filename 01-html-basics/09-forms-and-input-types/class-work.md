# Class Work — Build a User Registration Form

## What You Will Build

A complete user registration form using all major HTML input types. By the end you will have a form with text, email, password, date, number, radio, checkbox, select, file, textarea, and more.

**Time:** 45 minutes

---

## Step 1 — Set Up the Page

Create a file called `registration-form.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Create Account</title>
  </head>
  <body>
    <h1>Create Your Account</h1>
    <p>Fields marked with * are required.</p>
  </body>
</html>
```

---

## Step 2 — Create the Form Element

```html
<form action="/register" method="POST">
  <!-- All inputs go here -->
</form>
```

**What `action` does:** Where the form data is sent when submitted.
**What `method="POST"` does:** Sends data in the request body (not visible in URL).

---

## Step 3 — Personal Information Fieldset

```html
<fieldset>
  <legend>Personal Information</legend>

  <div>
    <label for="full-name">Full Name *</label>
    <input type="text" id="full-name" name="full_name" placeholder="John Smith" required>
  </div>

  <div>
    <label for="email">Email Address *</label>
    <input type="email" id="email" name="email" placeholder="john@example.com" required>
  </div>

  <div>
    <label for="phone">Phone Number</label>
    <input type="tel" id="phone" name="phone" placeholder="+1 555 000 0000">
  </div>

  <div>
    <label for="dob">Date of Birth *</label>
    <input type="date" id="dob" name="date_of_birth" required>
  </div>

</fieldset>
```

**What `<fieldset>` does:** Groups related inputs together.
**What `<legend>` does:** Labels the group.
**Why `for` and `id` must match:** Clicking the label focuses the input. Screen readers use this connection.

---

## Step 4 — Account Security Fieldset

```html
<fieldset>
  <legend>Account Security</legend>

  <div>
    <label for="username">Username *</label>
    <input type="text" id="username" name="username" placeholder="Choose a username" required minlength="3" maxlength="20">
  </div>

  <div>
    <label for="password">Password *</label>
    <input type="password" id="password" name="password" placeholder="Min 8 characters" required minlength="8">
  </div>

</fieldset>
```

---

## Step 5 — Profile Fieldset with Select and Textarea

```html
<fieldset>
  <legend>Profile</legend>

  <div>
    <label for="country">Country *</label>
    <select id="country" name="country" required>
      <option value="">-- Select your country --</option>
      <option value="us">United States</option>
      <option value="uk">United Kingdom</option>
      <option value="ca">Canada</option>
      <option value="ng">Nigeria</option>
      <option value="gh">Ghana</option>
      <option value="other">Other</option>
    </select>
  </div>

  <div>
    <label for="avatar">Profile Picture</label>
    <input type="file" id="avatar" name="avatar" accept="image/jpeg,image/png,image/webp">
  </div>

  <div>
    <label for="bio">Short Bio</label>
    <textarea id="bio" name="bio" rows="4" placeholder="Tell us about yourself..." maxlength="300"></textarea>
  </div>

</fieldset>
```

---

## Step 6 — Interests with Checkboxes

```html
<fieldset>
  <legend>Interests (select all that apply)</legend>

  <div>
    <input type="checkbox" id="interest-frontend" name="interests" value="frontend">
    <label for="interest-frontend">Frontend Development</label>
  </div>
  <div>
    <input type="checkbox" id="interest-backend" name="interests" value="backend">
    <label for="interest-backend">Backend Development</label>
  </div>
  <div>
    <input type="checkbox" id="interest-design" name="interests" value="design">
    <label for="interest-design">UI/UX Design</label>
  </div>
  <div>
    <input type="checkbox" id="interest-data" name="interests" value="data">
    <label for="interest-data">Data Science</label>
  </div>

</fieldset>
```

**Key point:** All checkboxes in a group share the same `name`. Each has a unique `id` and `value`.

---

## Step 7 — Experience Level with Radio Buttons

```html
<fieldset>
  <legend>Experience Level *</legend>

  <div>
    <input type="radio" id="level-beginner" name="experience" value="beginner" checked>
    <label for="level-beginner">Beginner (0–1 years)</label>
  </div>
  <div>
    <input type="radio" id="level-intermediate" name="experience" value="intermediate">
    <label for="level-intermediate">Intermediate (1–3 years)</label>
  </div>
  <div>
    <input type="radio" id="level-advanced" name="experience" value="advanced">
    <label for="level-advanced">Advanced (3+ years)</label>
  </div>

</fieldset>
```

**Key point:** All radio buttons in a group share the same `name`. Only one can be selected at a time.

---

## Step 8 — Terms and Submit

```html
<fieldset>
  <legend>Terms</legend>

  <div>
    <input type="checkbox" id="terms" name="terms" required>
    <label for="terms">I agree to the Terms of Service *</label>
  </div>

</fieldset>

<div>
  <button type="submit">Create Account</button>
  <button type="reset">Clear Form</button>
</div>
```

---

## Checklist

- [ ] `<form>` has `action` and `method` attributes
- [ ] All inputs have `<label>` with matching `for` and `id`
- [ ] Related inputs are grouped in `<fieldset>` with `<legend>`
- [ ] `type="text"`, `email`, `password`, `date`, `tel`, `file` all used
- [ ] `<select>` with `<option>` elements
- [ ] `<textarea>` for multi-line text
- [ ] Checkboxes with same `name`, unique `id` and `value`
- [ ] Radio buttons with same `name`, unique `id` and `value`
- [ ] Required fields have `required` attribute
- [ ] Submit and reset buttons present
