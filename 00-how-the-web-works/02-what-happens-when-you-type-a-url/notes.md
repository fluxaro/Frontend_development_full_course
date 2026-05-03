# Notes — What Happens When You Type a URL?

## The 7 Steps (Quick Reference)

```
1. Type URL      →  Browser parses: protocol + domain + path
2. DNS Lookup    →  Domain name → IP address
3. TCP Connect   →  3-way handshake (SYN → SYN-ACK → ACK)
4. TLS Handshake →  Encryption keys exchanged (HTTPS only)
5. HTTP Request  →  GET / HTTP/1.1 sent to server
6. HTTP Response →  200 OK + HTML content returned
7. Render        →  HTML → DOM → CSSOM → Render Tree → Paint
```

---

## Key Terms

### URL (Uniform Resource Locator)
The full web address. Broken into parts:
```
https://www.example.com:443/path/to/page?query=value#section
  │         │           │       │            │          │
protocol  domain       port    path        query     fragment
```

### DNS (Domain Name System)
Translates human-readable domain names into IP addresses.
- `google.com` → `142.250.80.46`
- DNS lookup order: browser cache → OS cache → router → ISP DNS → root servers

### TCP (Transmission Control Protocol)
A reliable, connection-based protocol. Guarantees data arrives in order and without errors.

**3-Way Handshake:**
```
Client → Server:  SYN  (I want to connect)
Server → Client:  SYN-ACK  (OK, I'm ready)
Client → Server:  ACK  (Great, let's go!)
```

### TLS (Transport Layer Security)
Encrypts data between browser and server. Replaces the older SSL.
- Used in HTTPS (HTTP + TLS)
- Prevents eavesdropping and tampering
- You see the padlock icon when TLS is active

### HTTP Request
What the browser sends to the server:
```
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0
Accept: text/html
```

### HTTP Response
What the server sends back:
```
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 1234

<!DOCTYPE html>
<html>...
```

### TTFB (Time to First Byte)
The time from when the browser sends the request to when it receives the first byte of the response. A key performance metric — lower is better.

### Rendering
The process of turning HTML/CSS/JS into visible pixels:
1. Parse HTML → DOM tree
2. Parse CSS → CSSOM tree
3. Combine → Render tree
4. Layout (calculate positions)
5. Paint (draw pixels)

---

## Common Status Codes

| Code | Meaning |
|------|---------|
| 200 | OK — success |
| 301 | Moved Permanently — redirect |
| 304 | Not Modified — use cached version |
| 404 | Not Found |
| 500 | Internal Server Error |

---

## Timeline of a Typical Page Load

```
0ms      DNS lookup starts
~20ms    DNS resolved, TCP connection starts
~40ms    TCP connected, TLS handshake starts
~80ms    TLS done, HTTP request sent
~120ms   First byte received (TTFB)
~200ms   HTML fully downloaded
~300ms   CSS and JS downloaded
~400ms   Page rendered and visible
```
*(Times vary greatly based on network speed and server location)*

---

## Remember

The whole process — DNS lookup, TCP handshake, TLS, HTTP request, response, and rendering — typically happens in **under 1 second** on a fast connection. That's remarkable engineering!
