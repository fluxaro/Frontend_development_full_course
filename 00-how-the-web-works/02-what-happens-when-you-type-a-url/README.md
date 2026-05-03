# 02 — What Happens When You Type a URL?

## The Full Journey

Typing a URL and pressing Enter kicks off one of the most complex — yet fastest — sequences of events in computing. Let's break it down.

---

## The Restaurant Analogy

Think of visiting a website like ordering food at a restaurant:

| Restaurant | Web |
|-----------|-----|
| You (customer) | Your browser |
| Waiter | HTTP protocol |
| Kitchen | Web server |
| Menu item name | URL / domain name |
| Address book to find the restaurant | DNS |
| Food being prepared | Server processing request |
| Food arriving at your table | HTTP response |
| You eating the food | Browser rendering the page |

---

## The 7 Steps

### Step 1 — You Type the URL
You type `https://www.github.com` and press Enter. The browser parses the URL into parts:
- **Protocol:** `https`
- **Domain:** `www.github.com`
- **Path:** `/` (the homepage)

### Step 2 — DNS Lookup
The browser needs to find the IP address for `github.com`. It checks:
1. Its own cache (has it visited before?)
2. Your OS cache
3. Your router's cache
4. Your ISP's DNS server
5. Root DNS servers (if needed)

Result: `140.82.121.4` (GitHub's IP)

### Step 3 — TCP Connection
The browser opens a TCP connection to the server using a **3-way handshake**:
1. Browser → Server: "SYN" (I want to connect)
2. Server → Browser: "SYN-ACK" (OK, I'm ready)
3. Browser → Server: "ACK" (Great, let's go)

### Step 4 — TLS Handshake (HTTPS only)
For secure connections, the browser and server exchange encryption keys. This ensures all data is encrypted in transit. This is why HTTPS is important.

### Step 5 — HTTP Request
The browser sends an HTTP request:
```
GET / HTTP/1.1
Host: www.github.com
User-Agent: Mozilla/5.0 ...
Accept: text/html
```

### Step 6 — Server Response
The server processes the request and sends back:
```
HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
...
<!DOCTYPE html>
<html>...
```

### Step 7 — Browser Renders the Page
The browser receives the HTML and:
1. Parses HTML → builds the DOM
2. Parses CSS → builds the CSSOM
3. Combines them → Render Tree
4. Calculates layout
5. Paints pixels on screen

---

## Key Terms

| Term | Meaning |
|------|---------|
| URL | Uniform Resource Locator — the web address |
| DNS | Domain Name System — translates names to IPs |
| TCP | Transmission Control Protocol — reliable connection |
| TLS | Transport Layer Security — encryption |
| HTTP | HyperText Transfer Protocol — web communication |
| TTFB | Time to First Byte — how fast the server starts responding |
| Rendering | Browser turning HTML/CSS into visible pixels |

---

## Prerequisites

- Lesson 01: Internet Basics

## Next Lesson

→ `03-dns-explained`
