# Class Work — DNS Explained

## Activity 1: Terminal DNS Lookups (15 minutes)

### Step 1 — Open Your Terminal
- **Mac/Linux:** Open Terminal
- **Windows:** Open Command Prompt or PowerShell

### Step 2 — Run nslookup Commands

Run each of these commands and record the results:

```bash
nslookup google.com
nslookup github.com
nslookup twitter.com
nslookup amazon.com
nslookup localhost
```

**Fill in this table:**

| Domain | IP Address(es) Found | Server Used |
|--------|---------------------|-------------|
| google.com | | |
| github.com | | |
| twitter.com | | |
| amazon.com | | |
| localhost | | |

**Questions:**
1. Why does Google return multiple IP addresses?
2. What IP address does `localhost` resolve to? Why?
3. What DNS server did your computer use for the lookups?

---

### Step 3 — Try dig (Mac/Linux) or nslookup with record types

On Mac/Linux, run:
```bash
dig google.com A
dig google.com MX
dig google.com NS
```

On Windows:
```bash
nslookup -type=A google.com
nslookup -type=MX google.com
nslookup -type=NS google.com
```

**Record what you find:**

| Record Type | Result |
|-------------|--------|
| A record for google.com | |
| MX record for google.com | |
| NS record for google.com | |

---

## Activity 2: Check DNS Cache (10 minutes)

### View your DNS cache:

**Windows:**
```bash
ipconfig /displaydns
```

**Mac:**
```bash
sudo dscacheutil -cachedump -entries Host
```

**Linux:**
```bash
systemd-resolve --statistics
```

- How many entries are in your DNS cache?
- Can you find any familiar domain names?

---

## Activity 3: Build a DNS Explainer Page (25 minutes)

Create an HTML file called `my-dns-notes.html` that explains DNS in your own words.

Your page should include:
1. A title: "How DNS Works"
2. A simple explanation of what DNS does (in your own words)
3. The results from your nslookup commands in a table
4. A list of the DNS record types you learned about

### Starter HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>How DNS Works</title>
  <style>
    body { font-family: sans-serif; max-width: 800px; margin: 40px auto; padding: 0 20px; }
    table { width: 100%; border-collapse: collapse; margin: 20px 0; }
    th, td { border: 1px solid #ddd; padding: 10px; text-align: left; }
    th { background: #f0f4f8; font-weight: bold; }
    .record-type { 
      display: inline-block; 
      background: #dbeafe; 
      color: #1d4ed8; 
      padding: 2px 8px; 
      border-radius: 4px; 
      font-family: monospace;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>🔍 How DNS Works</h1>
  
  <h2>What is DNS?</h2>
  <p><!-- Your explanation here --></p>
  
  <h2>My nslookup Results</h2>
  <!-- Your table here -->
  
  <h2>DNS Record Types</h2>
  <!-- Your list here -->
</body>
</html>
```

---

## Discussion Questions

1. What would happen if DNS didn't exist? How would you visit websites?
2. Why is DNS caching important for performance?
3. What's the difference between an A record and a CNAME record?
4. Why might a company have multiple A records for the same domain?

---

## Deliverable

Share your `my-dns-notes.html` and your nslookup findings with the class.
