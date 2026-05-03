# Class Work — HTTP & HTTPS: Request/Response

## Activity 1: Inspect a Real HTTP Request (20 minutes)

### Setup
1. Open Chrome or Firefox
2. Press `F12` → click **Network** tab
3. Check "Disable cache"
4. Visit `https://httpbin.org/get`

---

### Step 1 — Find the Main Request

Click on the first request in the list.

**Fill in this table:**

| Field | Your Finding |
|-------|-------------|
| Request URL | |
| Request Method | |
| Status Code | |
| HTTP Version | |
| Content-Type (response) | |
| Server header | |

---

### Step 2 — Read the Request Headers

Click the **Headers** tab on the request.

**Find and record:**

| Header | Value |
|--------|-------|
| `Host` | |
| `User-Agent` | |
| `Accept` | |
| `Accept-Language` | |
| `Accept-Encoding` | |

**Question:** What does the `Accept` header tell the server?

---

### Step 3 — Read the Response Headers

**Find and record:**

| Header | Value |
|--------|-------|
| `Content-Type` | |
| `Content-Length` | |
| `Access-Control-Allow-Origin` | |
| Any other interesting header | |

---

### Step 4 — Test Different Status Codes

Visit these URLs and record the status code:

| URL | Status Code | Category |
|-----|-------------|----------|
| `https://httpstat.us/200` | | |
| `https://httpstat.us/201` | | |
| `https://httpstat.us/301` | | |
| `https://httpstat.us/404` | | |
| `https://httpstat.us/500` | | |
| `https://httpstat.us/503` | | |

---

### Step 5 — Find a POST Request

Visit `https://httpbin.org/post` — but this time, use the browser console to make a POST request:

1. Open the **Console** tab in DevTools
2. Paste and run this code:

```javascript
fetch('https://httpbin.org/post', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ name: 'Your Name', bootcamp: 'Frontend' })
})
.then(res => res.json())
.then(data => console.log(data));
```

3. Switch back to the **Network** tab and find the POST request
4. What's different about a POST request vs a GET request?

---

## Activity 2: Document Your Findings (15 minutes)

Create an HTML file called `my-http-findings.html` that documents what you found.

Include:
1. A table of the request headers you found
2. A table of the response headers you found
3. The status codes you tested and what they mean
4. The difference between GET and POST (in your own words)

---

## Discussion Questions

1. Why is HTTPS important? What could go wrong with plain HTTP?
2. When would you use POST instead of GET?
3. What's the difference between a 401 and a 403 error?
4. Why does the browser send a `User-Agent` header?

---

## Deliverable

Share your `my-http-findings.html` with the class.
