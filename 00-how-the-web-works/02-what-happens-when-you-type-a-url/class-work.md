# Class Work — What Happens When You Type a URL

## What You Will Do

You will trace the full journey of a URL request using your browser's developer tools, then document each step you observe.

**Time:** 35–40 minutes

---

## Activity 1: Trace a Real Request (20 minutes)

### Step 1 — Open DevTools and Go to the Network Tab

Open Chrome or Firefox. Press `F12` (Windows) or `Cmd + Option + I` (Mac). Click the **Network** tab.

### Step 2 — Visit GitHub

With the Network tab open, type `https://github.com` in the address bar and press Enter.

Watch the Network tab fill up with requests.

### Step 3 — Find the Main HTML Document

The first request in the list is the main HTML document. Click on it.

Look at the **Headers** tab inside that request. Find and write down:

**Request Headers:**
- What is the `Host` header value?
- What is the `User-Agent` header value?
- What HTTP method was used?

**Response Headers:**
- What is the `content-type` value?
- What is the `status` code?
- Is there a `strict-transport-security` header? What does it say?

### Step 4 — Look at the Timing

Click the **Timing** tab for the same request.

Write down:
- DNS Lookup time (in milliseconds)
- Initial Connection time
- Waiting (TTFB) time
- Content Download time
- Total time

### Step 5 — Count the Requests

Go back to the main Network tab view. Look at the bottom of the panel.

Write down:
- How many total requests were made to load the page?
- What is the total size of all resources downloaded?
- How long did the full page take to load?

---

## Activity 2: Observe the Steps in Order (10 minutes)

Now that you have seen a real request, map what you observed to the 7 steps.

Fill in this table based on what you found:

| Step | What You Observed |
|---|---|
| 1. URL Parsing | The browser connected to: |
| 2. DNS Lookup | DNS lookup took: |
| 3. TCP Connection | Initial connection took: |
| 4. TLS Handshake | Was HTTPS used? Yes / No |
| 5. HTTP Request | Method used: |
| 6. HTTP Response | Status code received: |
| 7. Browser Rendering | Total requests to render page: |

---

## Activity 3: Build a Documentation Page (10 minutes)

Create a file called `my-url-trace.html`.

Using only HTML, create a page that includes:
- An `<h1>` heading: "My URL Trace — github.com"
- A `<table>` with your findings from Activity 2
- A `<p>` paragraph explaining one thing that surprised you

---

## Discussion Questions

1. Why does loading one page require so many separate requests?
2. What is the difference between the DNS lookup time and the TTFB time?
3. Why does HTTPS require an extra step (TLS handshake) compared to HTTP?
4. What happens if the DNS lookup fails?

---

## Deliverable

Show your completed `my-url-trace.html` to the instructor.
