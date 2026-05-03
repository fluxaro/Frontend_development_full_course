# Assignment — HTTP & HTTPS Reference Guide

**Due:** Next class session  
**Estimated time:** 1.5–2 hours

---

## Your Task

Create a styled **HTTP Reference Page** — a complete guide to HTTP methods, status codes, and headers that you could use as a cheat sheet while building web apps.

---

## Requirements

### The page must include:

#### Section 1: HTTP Methods
A card or table for each method showing:
- Method name (GET, POST, PUT, PATCH, DELETE, HEAD, OPTIONS)
- What it does
- When to use it
- Example use case

#### Section 2: Status Codes
Grouped by category (2xx, 3xx, 4xx, 5xx), each showing:
- The code number
- The name
- What it means
- When you'd see it

#### Section 3: Common Headers
A table or card list of at least 8 common headers (mix of request and response), showing:
- Header name
- Type (request/response/both)
- What it does
- Example value

### Design Requirements:
- Embedded CSS (in a `<style>` tag)
- Color-coded by category (e.g., 2xx = green, 4xx = red, 5xx = orange)
- Clean, readable layout
- Works in a browser without any external files

---

## Starter Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>HTTP Reference Guide</title>
  <style>
    body {
      font-family: sans-serif;
      background: #f8fafc;
      color: #1e293b;
      padding: 40px 20px;
      max-width: 1000px;
      margin: 0 auto;
    }

    h1 { color: #1e293b; margin-bottom: 8px; }
    h2 { color: #3b82f6; margin: 40px 0 20px; border-bottom: 2px solid #e2e8f0; padding-bottom: 8px; }

    .method-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 16px;
    }

    .method-card {
      background: white;
      border-radius: 10px;
      padding: 20px;
      border-top: 4px solid #3b82f6;
      box-shadow: 0 2px 8px rgba(0,0,0,0.06);
    }

    /* Add more styles... */
  </style>
</head>
<body>
  <h1>📡 HTTP Reference Guide</h1>
  <p>A complete reference for HTTP methods, status codes, and headers.</p>

  <h2>HTTP Methods</h2>
  <div class="method-grid">
    <div class="method-card">
      <h3>GET</h3>
      <p>Retrieve data from the server. No body sent.</p>
      <p><strong>Use when:</strong> Loading a page, fetching data</p>
    </div>
    <!-- Add more methods -->
  </div>

  <h2>Status Codes</h2>
  <!-- Add status codes grouped by category -->

  <h2>Common Headers</h2>
  <!-- Add headers table -->

</body>
</html>
```

---

## Bonus Challenges

- Add a search/filter input that filters status codes as you type
- Add a "copy to clipboard" button on each header name
- Make the page dark-mode friendly
- Add a "HTTP vs HTTPS" comparison section

---

## Grading Criteria

| Criteria | Points |
|----------|--------|
| All 7 HTTP methods covered | 25 |
| Status codes grouped by category (2xx–5xx) | 25 |
| At least 8 headers documented | 20 |
| Color-coded by category | 15 |
| Clean, readable styling | 15 |
| **Bonus:** Search filter, dark mode | +10 |

**Total: 100 points**

---

## Submission

Submit your `http-reference.html` file. Make sure all sections are visible and styled.
