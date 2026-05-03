# Class Work — Build a "Remember Me" Feature

## What You Will Build

A page that remembers the user's name using localStorage. When the user visits again, it greets them by name.

**Time:** 35 minutes

---

## Step 1 — Set Up the Page

Create a file called `localstorage-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Remember Me — localStorage Demo</title>
  </head>
  <body>
    <h1>localStorage Demo</h1>
  </body>
</html>
```

---

## Step 2 — Add the Greeting Section

```html
<section>
  <h2 id="greeting">Welcome!</h2>
  <p id="greeting-message">We do not know your name yet.</p>
</section>
```

---

## Step 3 — Add the Name Form

```html
<section>
  <h2>Tell Us Your Name</h2>
  <form id="name-form">
    <label for="user-name">Your Name:</label>
    <input type="text" id="user-name" placeholder="Enter your name" required>
    <button type="submit">Save My Name</button>
  </form>
</section>
```

---

## Step 4 — Add the Saved Data Display

```html
<section>
  <h2>What Is Stored</h2>
  <dl>
    <dt>Key</dt>
    <dd><code>username</code></dd>
    <dt>Value</dt>
    <dd id="stored-value">Nothing stored yet</dd>
  </dl>
  <button id="clear-btn">Clear Saved Name</button>
</section>
```

---

## Step 5 — Add the JavaScript

```html
<script>
  // On page load: check if name is saved
  window.addEventListener('load', function() {
    const savedName = localStorage.getItem('username');

    if (savedName) {
      document.getElementById('greeting').textContent = 'Welcome back, ' + savedName + '!';
      document.getElementById('greeting-message').textContent = 'We remembered you from your last visit.';
      document.getElementById('stored-value').textContent = savedName;
      document.getElementById('user-name').value = savedName;
    }
  });

  // Save name when form is submitted
  document.getElementById('name-form').addEventListener('submit', function(event) {
    event.preventDefault();

    const name = document.getElementById('user-name').value.trim();

    if (name) {
      // Save to localStorage
      localStorage.setItem('username', name);

      // Update the greeting
      document.getElementById('greeting').textContent = 'Hello, ' + name + '!';
      document.getElementById('greeting-message').textContent = 'Your name has been saved. Reload the page to see it remembered.';
      document.getElementById('stored-value').textContent = name;
    }
  });

  // Clear saved name
  document.getElementById('clear-btn').addEventListener('click', function() {
    localStorage.removeItem('username');
    document.getElementById('greeting').textContent = 'Welcome!';
    document.getElementById('greeting-message').textContent = 'We do not know your name yet.';
    document.getElementById('stored-value').textContent = 'Nothing stored yet';
    document.getElementById('user-name').value = '';
  });
</script>
```

---

## Step 6 — Test It

1. Open the page in your browser
2. Enter your name and click "Save My Name"
3. Reload the page — does it remember your name?
4. Close the browser completely and reopen the page — does it still remember?
5. Click "Clear Saved Name" — does it forget?

---

## Step 7 — Add sessionStorage Demo

Add a second section that uses sessionStorage:

```html
<section>
  <h2>Session Notes (sessionStorage)</h2>
  <p>These notes will be cleared when you close this tab.</p>
  <label for="session-notes">Notes:</label>
  <textarea id="session-notes" rows="4" placeholder="Type something..."></textarea>
</section>

<script>
  // Load session notes
  const savedNotes = sessionStorage.getItem('notes');
  if (savedNotes) {
    document.getElementById('session-notes').value = savedNotes;
  }

  // Save notes as you type
  document.getElementById('session-notes').addEventListener('input', function() {
    sessionStorage.setItem('notes', this.value);
  });
</script>
```

---

## Checklist

- [ ] localStorage saves the username
- [ ] Page greets user by name on reload
- [ ] Clear button removes the saved name
- [ ] sessionStorage saves notes
- [ ] Notes are cleared when tab is closed
- [ ] All inputs have labels
