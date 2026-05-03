# Class Work — Audit and Fix an Inaccessible Page

## What You Will Do

You will audit an inaccessible HTML page, identify all the problems, fix them, and then build a fully accessible contact form.

**Time:** 45 minutes

---

## Part 1: Accessibility Audit (15 minutes)

Here is an inaccessible page. Find and list every accessibility problem:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Contact</title>
</head>
<body>

  <div style="font-size: 24px; font-weight: bold;">Contact Us</div>

  <div>
    <div>Name</div>
    <input type="text" placeholder="Your name">
  </div>

  <div>
    <div>Email</div>
    <input type="text" placeholder="Your email">
  </div>

  <div>
    <div>Message</div>
    <textarea placeholder="Your message"></textarea>
  </div>

  <div onclick="submitForm()" style="background: red; color: white; padding: 10px;">
    Submit
  </div>

  <img src="office.jpg">

  <div style="color: #aaa; background: #fff;">
    This text has poor contrast.
  </div>

</body>
</html>
```

**Find all the problems. There are at least 10. Write them down:**

1. Missing `lang` attribute on `<html>`
2. `<div>` used as heading instead of `<h1>`
3. ...

---

## Part 2: Fix the Page (15 minutes)

Rewrite the page fixing every problem you found. The fixed version must:

- Have `lang="en"` on `<html>`
- Use `<h1>` for the main heading
- Have `<label>` for every input with matching `for` and `id`
- Use `type="email"` for the email field
- Use `<button type="submit">` instead of a `<div>` with onclick
- Have `alt` text on the image
- Have a `<form>` element wrapping the inputs
- Have `required` on required fields
- Have a skip link at the top

---

## Part 3: Build an Accessible Contact Form (15 minutes)

Create a file called `accessible-contact.html`. Build a fully accessible contact form that includes:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Contact Us — Accessible Form</title>
</head>
<body>

  <!-- Skip link -->
  <a href="#main-content">Skip to main content</a>

  <header>
    <h1>Contact Us</h1>
  </header>

  <main id="main-content">
    <form action="/contact" method="POST" novalidate>

      <div>
        <label for="name">Full Name *</label>
        <input
          type="text"
          id="name"
          name="name"
          required
          aria-required="true"
          autocomplete="name"
        >
      </div>

      <div>
        <label for="email">Email Address *</label>
        <input
          type="email"
          id="email"
          name="email"
          required
          aria-required="true"
          autocomplete="email"
          aria-describedby="email-hint"
        >
        <p id="email-hint">We will never share your email address.</p>
      </div>

      <div>
        <label for="subject">Subject *</label>
        <select id="subject" name="subject" required aria-required="true">
          <option value="">-- Select a subject --</option>
          <option value="general">General Inquiry</option>
          <option value="support">Technical Support</option>
          <option value="billing">Billing</option>
          <option value="other">Other</option>
        </select>
      </div>

      <div>
        <label for="message">Message *</label>
        <textarea
          id="message"
          name="message"
          rows="6"
          required
          aria-required="true"
          aria-describedby="message-hint"
        ></textarea>
        <p id="message-hint">Minimum 20 characters. Maximum 1000 characters.</p>
      </div>

      <div>
        <button type="submit">Send Message</button>
        <button type="reset">Clear Form</button>
      </div>

    </form>
  </main>

</body>
</html>
```

---

## Checklist

- [ ] `lang="en"` on `<html>`
- [ ] Skip link at the top
- [ ] All headings use proper `<h1>`, `<h2>` etc.
- [ ] All inputs have `<label>` with matching `for` and `id`
- [ ] `aria-required="true"` on required fields
- [ ] `aria-describedby` pointing to hint text
- [ ] `<button>` used instead of `<div>` for submit
- [ ] `type="email"` for email field
- [ ] `<form>` wraps all inputs
- [ ] Page is fully navigable by keyboard only
