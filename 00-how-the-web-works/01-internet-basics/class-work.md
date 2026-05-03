# Class Work — Internet Basics

## What You Will Do

In this session you will explore how the internet works by using your browser's built-in developer tools. Then you will document what you find in a simple HTML page.

**Time:** 30–40 minutes

---

## Activity 1: Draw the Journey (10 minutes)

On paper, draw a diagram showing how data travels from your computer to `google.com` and back.

Your diagram must include these stops in order:
1. Your Computer
2. Your Router
3. Your ISP (Internet Service Provider)
4. DNS Server
5. Google's Web Server
6. Response traveling back to you

Label each arrow with what is happening at that step. For example: "sends HTTP request", "DNS lookup", "returns IP address", "sends HTML response".

Share your diagram with the person next to you and compare. Did you draw it the same way?

---

## Activity 2: Explore the Network Tab (20 minutes)

### Step 1 — Open Developer Tools

In Chrome or Firefox:
- Windows: press `F12`
- Mac: press `Cmd + Option + I`

Click the **Network** tab at the top.

### Step 2 — Visit a Website

Make sure the Network tab is open and recording (you should see a red circle or a recording indicator).

Type `https://example.com` in the address bar and press Enter.

You will see a list of requests appear in the Network tab.

### Step 3 — Investigate the First Request

Click on the first request in the list (it should be the HTML document itself).

Find and write down the following:

| What to Find | What You Found |
|---|---|
| Request URL | |
| Request Method (GET, POST, etc.) | |
| Status Code (200, 404, etc.) | |
| Content-Type in the response | |
| One request header name and value | |
| One response header name and value | |

### Step 4 — Check the Timing

Click on the same request, then click the **Timing** tab inside it.

Write down:
- What is the **Waiting (TTFB)** time? (Time to First Byte — how long before the server started responding)
- What is the total **Duration**?

### Step 5 — Test Different Status Codes

Visit these URLs and note the status code for each one:

| URL | Status Code | What It Means |
|---|---|---|
| `https://example.com` | | |
| `https://httpstat.us/404` | | |
| `https://httpstat.us/500` | | |
| `https://httpstat.us/301` | | |

---

## Activity 3: Document Your Findings (10 minutes)

Create a new file called `network-findings.html`.

Using only HTML (no CSS), create a page that includes:
- An `<h1>` heading: "What I Found in the Network Tab"
- A `<table>` with your findings from Activity 2, Step 3
- A short `<p>` paragraph describing what surprised you most

---

## Discussion Questions

Think about these and be ready to discuss with the class:

1. Why do you think data is broken into packets instead of sent all at once?
2. What would happen if there was no DNS — how would you visit websites?
3. What is the difference between a slow internet connection and a fast one in terms of latency vs bandwidth?
4. Why does a video call get choppy when your internet is slow?

---

## Deliverable

Show your hand-drawn diagram to the instructor and share one thing you discovered in the Network tab.
