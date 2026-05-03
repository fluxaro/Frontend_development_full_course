# Class Work — Interactive Navigation and Table

## What You Will Build

A navigation menu with hover effects and a data table with zebra striping and row highlighting.

**Time:** 35 minutes

---

## Step 1 — Create the HTML

Create `pseudo-classes-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pseudo-classes Demo</title>
  <link rel="stylesheet" href="pseudo-classes.css">
</head>
<body>

  <nav>
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/about">About</a></li>
      <li><a href="/services">Services</a></li>
      <li><a href="/blog">Blog</a></li>
      <li><a href="/contact">Contact</a></li>
    </ul>
  </nav>

  <main>
    <h1>Pseudo-classes Demo</h1>

    <section>
      <h2>Form with Focus States</h2>
      <form>
        <label for="name">Name:</label>
        <input type="text" id="name" placeholder="Enter your name" required>

        <label for="email">Email:</label>
        <input type="email" id="email" placeholder="Enter your email" required>

        <button type="submit">Submit</button>
        <button type="button" disabled>Disabled Button</button>
      </form>
    </section>

    <section>
      <h2>Data Table with nth-child</h2>
      <table>
        <thead>
          <tr>
            <th>Rank</th>
            <th>Language</th>
            <th>Creator</th>
            <th>Year</th>
            <th>Type</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>1</td><td>JavaScript</td><td>Brendan Eich</td><td>1995</td><td>Dynamic</td></tr>
          <tr><td>2</td><td>Python</td><td>Guido van Rossum</td><td>1991</td><td>Dynamic</td></tr>
          <tr><td>3</td><td>TypeScript</td><td>Microsoft</td><td>2012</td><td>Static</td></tr>
          <tr><td>4</td><td>Java</td><td>James Gosling</td><td>1995</td><td>Static</td></tr>
          <tr><td>5</td><td>C#</td><td>Microsoft</td><td>2000</td><td>Static</td></tr>
          <tr><td>6</td><td>Go</td><td>Google</td><td>2009</td><td>Static</td></tr>
        </tbody>
      </table>
    </section>

    <section>
      <h2>List with nth-child Styling</h2>
      <ul class="styled-list">
        <li>First item (bold)</li>
        <li>Second item</li>
        <li>Third item (highlighted)</li>
        <li>Fourth item</li>
        <li>Fifth item</li>
        <li>Last item (different color)</li>
      </ul>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `pseudo-classes.css`:

```css
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: sans-serif;
  color: #333;
  line-height: 1.6;
}

/* Navigation */
nav { background: #2c3e50; padding: 0 20px; }
nav ul { list-style: none; display: flex; }
nav li { }
nav a {
  display: block;
  padding: 16px 20px;
  color: #bdc3c7;
  text-decoration: none;
  transition: color 0.2s, background 0.2s;
}

/* :hover on nav links */
nav a:hover {
  color: white;
  background: #34495e;
}

/* :active on nav links */
nav a:active {
  background: #1a252f;
}

/* Main content */
main { max-width: 900px; margin: 40px auto; padding: 0 20px; }
h1 { font-size: 2rem; margin-bottom: 30px; }
h2 { font-size: 1.4rem; margin: 30px 0 15px; color: #2c3e50; }
section { margin-bottom: 40px; }

/* Form */
form { display: flex; flex-direction: column; gap: 12px; max-width: 400px; }
label { font-weight: 600; font-size: 0.9rem; }
input {
  padding: 10px 14px;
  border: 2px solid #ddd;
  border-radius: 6px;
  font-size: 1rem;
  outline: none;
  transition: border-color 0.2s;
}

/* :focus on inputs */
input:focus {
  border-color: #3498db;
  box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.2);
}

/* :valid and :invalid */
input:valid:not(:placeholder-shown) { border-color: #27ae60; }
input:invalid:not(:placeholder-shown) { border-color: #e74c3c; }

/* Buttons */
button {
  padding: 10px 20px;
  background: #3498db;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-size: 1rem;
  transition: background 0.2s, transform 0.1s;
}

/* :hover on button */
button:hover { background: #2980b9; }

/* :active on button */
button:active { transform: translateY(1px); }

/* :disabled on button */
button:disabled {
  background: #bdc3c7;
  cursor: not-allowed;
  opacity: 0.6;
}

/* Table */
table { width: 100%; border-collapse: collapse; }
th, td { padding: 12px 16px; text-align: left; border-bottom: 1px solid #eee; }
th { background: #2c3e50; color: white; }

/* :nth-child(even) — zebra striping */
tbody tr:nth-child(even) { background: #f8f9fa; }

/* :hover on table rows */
tbody tr:hover { background: #ebf5fb; }

/* :first-child on th */
th:first-child { border-radius: 4px 0 0 0; }
th:last-child { border-radius: 0 4px 0 0; }

/* Styled list */
.styled-list { list-style: none; padding: 0; }
.styled-list li {
  padding: 10px 16px;
  border-bottom: 1px solid #eee;
}

/* :first-child */
.styled-list li:first-child { font-weight: bold; color: #2c3e50; }

/* :last-child */
.styled-list li:last-child { border-bottom: none; color: #e74c3c; }

/* :nth-child(3) */
.styled-list li:nth-child(3) { background: #fef9e7; }

/* :not(:last-child) */
.styled-list li:not(:last-child):hover { background: #f0f0f0; }
```

---

## Checklist

- [ ] `:hover` on nav links changes color
- [ ] `:active` on nav links shows pressed state
- [ ] `:focus` on inputs shows visible ring
- [ ] `:valid` and `:invalid` on inputs
- [ ] `:disabled` on button
- [ ] `:nth-child(even)` for table zebra striping
- [ ] `:hover` on table rows
- [ ] `:first-child` and `:last-child` on list items
- [ ] `:not()` used at least once
