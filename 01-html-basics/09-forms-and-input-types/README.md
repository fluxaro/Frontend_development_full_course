# 09 — Forms and Input Types

## What Is This Lesson About?

Forms are how users send data to a server — login forms, signup forms, search boxes, contact forms, checkout forms. HTML5 provides a rich set of input types that handle validation, mobile keyboards, and user experience automatically.

---

## The `<form>` Element

```html
<form action="/submit" method="POST">
  <!-- form fields go here -->
</form>
```

| Attribute | Purpose | Values |
|---|---|---|
| `action` | Where to send the form data | URL path |
| `method` | How to send it | `GET` or `POST` |
| `novalidate` | Disable browser validation | (boolean) |
| `autocomplete` | Enable/disable autocomplete | `on` or `off` |

---

## The `<label>` Element

Every input must have a label. The `for` attribute connects the label to the input's `id`:

```html
<label for="email">Email Address</label>
<input type="email" id="email" name="email">
```

When the label is clicked, the input gets focus. This is important for accessibility.

---

## All Input Types

```html
<!-- Text -->
<input type="text">

<!-- Email — validates email format -->
<input type="email">

<!-- Password — hides characters -->
<input type="password">

<!-- Number — shows number keyboard on mobile -->
<input type="number" min="0" max="100">

<!-- Date — shows date picker -->
<input type="date">

<!-- Time -->
<input type="time">

<!-- Date and time -->
<input type="datetime-local">

<!-- Phone number -->
<input type="tel">

<!-- URL — validates URL format -->
<input type="url">

<!-- Search — shows search keyboard on mobile -->
<input type="search">

<!-- Color picker -->
<input type="color">

<!-- Range slider -->
<input type="range" min="0" max="100" step="5">

<!-- File upload -->
<input type="file" accept="image/*">

<!-- Checkbox -->
<input type="checkbox" id="agree" name="agree">
<label for="agree">I agree</label>

<!-- Radio button -->
<input type="radio" id="yes" name="answer" value="yes">
<label for="yes">Yes</label>

<!-- Hidden field -->
<input type="hidden" name="csrf_token" value="abc123">

<!-- Submit button -->
<input type="submit" value="Submit">

<!-- Reset button -->
<input type="reset" value="Clear">
```

---

## Other Form Elements

### Textarea
```html
<label for="message">Message</label>
<textarea id="message" name="message" rows="5" cols="40"></textarea>
```

### Select (Dropdown)
```html
<label for="country">Country</label>
<select id="country" name="country">
  <option value="">-- Select --</option>
  <option value="us">United States</option>
  <option value="uk">United Kingdom</option>
</select>
```

### Fieldset and Legend
```html
<fieldset>
  <legend>Personal Information</legend>
  <!-- related inputs -->
</fieldset>
```

### Button
```html
<button type="submit">Submit Form</button>
<button type="reset">Clear Form</button>
<button type="button">Just a Button</button>
```

---

## Important Input Attributes

| Attribute | Purpose | Example |
|---|---|---|
| `name` | Key in the form data | `name="email"` |
| `id` | Links to `<label for>` | `id="email"` |
| `value` | Default value | `value="John"` |
| `placeholder` | Hint text | `placeholder="Enter email"` |
| `required` | Field must be filled | `required` |
| `disabled` | Field cannot be edited | `disabled` |
| `readonly` | Field can be read but not changed | `readonly` |
| `autofocus` | Focus this field on page load | `autofocus` |
| `autocomplete` | Browser autocomplete hint | `autocomplete="email"` |
| `minlength` | Minimum character count | `minlength="8"` |
| `maxlength` | Maximum character count | `maxlength="100"` |
| `min` | Minimum value (number/date) | `min="0"` |
| `max` | Maximum value (number/date) | `max="100"` |
| `pattern` | Regex validation pattern | `pattern="[A-Za-z]{3,}"` |
| `multiple` | Allow multiple values | `multiple` |
| `accept` | File types for file input | `accept="image/*"` |
