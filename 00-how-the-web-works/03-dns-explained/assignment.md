# Assignment — DNS Explained

**Due:** Next class session  
**Estimated time:** 1.5–2 hours

---

## Your Task

Build a **"Fake DNS Lookup Tool"** — an interactive HTML page where a user can type a domain name, click a button, and see a fake DNS record table appear.

---

## Requirements

### The page must have:

1. **A header** — "DNS Lookup Tool" with a subtitle
2. **An input field** — where the user types a domain name (e.g., `google.com`)
3. **A "Lookup" button** — triggers the fake lookup
4. **A results section** that shows:
   - The domain that was searched
   - A table of DNS records (A, CNAME, MX, NS, TXT)
   - Each record with: Type, Name, Value, TTL
5. **Hardcoded data** — you don't need a real API, just fake data for a few domains

### Domains to support (hardcoded):
- `google.com`
- `github.com`
- `twitter.com`
- Any other domain → show a "Domain not found" message

---

## Example Output

When user types `google.com` and clicks Lookup:

```
DNS Records for: google.com
┌──────┬────────────┬──────────────────────┬────────┐
│ Type │ Name       │ Value                │ TTL    │
├──────┼────────────┼──────────────────────┼────────┤
│ A    │ google.com │ 142.250.80.46        │ 300    │
│ MX   │ google.com │ aspmx.l.google.com   │ 600    │
│ NS   │ google.com │ ns1.google.com       │ 21600  │
│ TXT  │ google.com │ v=spf1 include:...   │ 3600   │
└──────┴────────────┴──────────────────────┴────────┘
```

---

## Starter Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>DNS Lookup Tool</title>
  <style>
    body {
      font-family: 'Courier New', monospace;
      background: #0f172a;
      color: #e2e8f0;
      padding: 40px 20px;
      max-width: 800px;
      margin: 0 auto;
    }
    /* Add your styles */
  </style>
</head>
<body>
  <h1>🔍 DNS Lookup Tool</h1>
  
  <div class="search-box">
    <input type="text" id="domainInput" placeholder="Enter domain (e.g. google.com)" />
    <button onclick="lookup()">Lookup</button>
  </div>
  
  <div id="results"></div>

  <script>
    // DNS data (hardcoded)
    const dnsData = {
      'google.com': [
        { type: 'A',    name: 'google.com', value: '142.250.80.46',       ttl: 300   },
        { type: 'MX',   name: 'google.com', value: 'aspmx.l.google.com',  ttl: 600   },
        { type: 'NS',   name: 'google.com', value: 'ns1.google.com',      ttl: 21600 },
        { type: 'TXT',  name: 'google.com', value: 'v=spf1 include:_spf.google.com ~all', ttl: 3600 },
      ],
      // Add more domains...
    };

    function lookup() {
      const domain = document.getElementById('domainInput').value.trim().toLowerCase();
      const resultsDiv = document.getElementById('results');
      
      if (!domain) {
        resultsDiv.innerHTML = '<p>Please enter a domain name.</p>';
        return;
      }
      
      const records = dnsData[domain];
      
      if (!records) {
        resultsDiv.innerHTML = `<p>❌ Domain "${domain}" not found in our records.</p>`;
        return;
      }
      
      // Build the results table
      // TODO: Build and display the table here
    }
  </script>
</body>
</html>
```

---

## Bonus Challenges

- Add a loading animation (fake 1-second delay before showing results)
- Color-code each record type (A = blue, MX = green, etc.)
- Add a "Clear" button to reset the results
- Support pressing Enter in the input field to trigger the lookup
- Add more domains to the hardcoded data

---

## Grading Criteria

| Criteria | Points |
|----------|--------|
| Input field and button work | 20 |
| Results table appears with correct data | 30 |
| At least 3 domains supported | 20 |
| "Not found" message for unknown domains | 10 |
| Page is styled (not plain HTML) | 20 |
| **Bonus:** Loading animation, Enter key support | +10 |

**Total: 100 points**

---

## Submission

Submit your `dns-lookup-tool.html` file. Test it with at least 3 domains before submitting.
