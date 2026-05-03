# 13 — Forms Validation: required, pattern, and HTML5 Constraints

## What Is This Lesson About?

HTML5 has built-in form validation that works without JavaScript. You can require fields, set minimum and maximum lengths, validate email formats, and use regular expressions — all in HTML.

---

## Built-in Validation Attributes

### required

The field must have a value before the form can be submitted:

```html
<input type="text" name="name" required>
```

### minlength and maxlength

Minimum and maximum number of characters:

```html
<input type="text" name="username" minlength="3" maxlength="20">
```

### min and max

Minimum and maximum values for numbers and dates:

```html
<input type="number" name="age" min="18" max="120">
<input type="date" name="birthday" min="1900-01-01" max="2010-12-31">
```

### type validation

Certain input types validate automatically:

```html
<input type="email">    <!-- must be valid email format -->
<input type="url">      <!-- must be valid URL format -->
<input type="number">   <!-- must be a number -->
```

### pattern

A regular expression the value must match:

```html
<!-- Only letters, 2-10 characters -->
<input type="text" pattern="[A-Za-z]{2,10}">

<!-- UK postcode format -->
<input type="text" pattern="[A-Z]{1,2}[0-9]{1,2}[A-Z]?\s?[0-9][A-Z]{2}">

<!-- Phone number: digits, spaces, dashes, parentheses -->
<input type="tel" pattern="[\d\s\-\(\)\+]{7,15}">
```

---

## Validation Feedback

### title attribute

The `title` attribute provides a custom message shown in the browser's validation tooltip:

```html
<input
  type="text"
  pattern="[A-Za-z]{3,20}"
  title="Username must be 3–20 letters only"
>
```

### novalidate

Disable browser validation on the entire form (useful when you want to handle validation with JavaScript):

```html
<form novalidate>
  <!-- browser won't validate these -->
</form>
```

---

## CSS Pseudo-classes for Validation

You can style inputs based on their validation state:

```css
/* Valid input */
input:valid {
  border-color: green;
}

/* Invalid input */
input:invalid {
  border-color: red;
}

/* Required but empty */
input:required:invalid {
  border-color: orange;
}

/* Optional and empty */
input:optional {
  border-color: gray;
}
```

---

## Common Pattern Examples

```html
<!-- Email -->
<input type="email">
<!-- HTML5 handles this automatically -->

<!-- Password: min 8 chars, at least one number -->
<input type="password" pattern="(?=.*\d).{8,}" title="At least 8 characters including one number">

<!-- Username: letters and numbers only, 3-20 chars -->
<input type="text" pattern="[A-Za-z0-9]{3,20}" title="3-20 letters and numbers only">

<!-- Phone: international format -->
<input type="tel" pattern="\+?[\d\s\-\(\)]{7,15}" title="Valid phone number">

<!-- Zip code (US) -->
<input type="text" pattern="\d{5}(-\d{4})?" title="5-digit zip code, optionally followed by -XXXX">

<!-- Date of birth: must be 18+ -->
<input type="date" max="2007-01-01" title="You must be at least 18 years old">
```

---

## Full Validated Form Example

```html
<form action="/signup" method="POST">

  <label for="username">Username *</label>
  <input
    type="text"
    id="username"
    name="username"
    required
    minlength="3"
    maxlength="20"
    pattern="[A-Za-z0-9_]+"
    title="3–20 characters: letters, numbers, and underscores only"
  >

  <label for="email">Email *</label>
  <input
    type="email"
    id="email"
    name="email"
    required
  >

  <label for="password">Password *</label>
  <input
    type="password"
    id="password"
    name="password"
    required
    minlength="8"
    pattern="(?=.*[A-Z])(?=.*\d).{8,}"
    title="At least 8 characters, one uppercase letter, and one number"
  >

  <label for="age">Age *</label>
  <input
    type="number"
    id="age"
    name="age"
    required
    min="18"
    max="120"
  >

  <button type="submit">Sign Up</button>
</form>
```
