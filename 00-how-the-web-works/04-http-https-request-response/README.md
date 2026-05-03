# 04 — HTTP & HTTPS: Request/Response

## What Is HTTP?

**HTTP** (HyperText Transfer Protocol) is the foundation of data communication on the web. It defines how messages are formatted and transmitted between browsers (clients) and web servers.

Every time you visit a website, your browser sends an HTTP **request** and the server sends back an HTTP **response**.

---

## HTTP vs HTTPS

| Feature | HTTP | HTTPS |
|---------|------|-------|
| Stands for | HyperText Transfer Protocol | HTTP Secure |
| Encryption | ❌ None | ✅ TLS/SSL encrypted |
| Port | 80 | 443 |
| URL prefix | `http://` | `https://` |
| Data visible to others? | Yes (plain text) | No (encrypted) |
| Use for sensitive data? | Never | Always |

**Always use HTTPS** for anything involving passwords, payments, or personal data.

---

## HTTP Request Methods

| Method | Purpose | Example Use |
|--------|---------|-------------|
| **GET** | Retrieve data | Load a webpage, fetch a list of users |
| **POST** | Send data to create something | Submit a form, create a new user |
| **PUT** | Replace/update a resource | Update a user's entire profile |
| **PATCH** | Partially update a resource | Update just a user's email |
| **DELETE** | Remove a resource | Delete a post |
| **HEAD** | Like GET but no body | Check if a resource exists |
| **OPTIONS** | Ask what methods are allowed | CORS preflight requests |

---

## HTTP Status Codes

Status codes tell you what happened with your request.

### 2xx — Success
| Code | Meaning |
|------|---------|
| 200 | OK — request succeeded |
| 201 | Created — new resource created |
| 204 | No Content — success, no body returned |

### 3xx — Redirection
| Code | Meaning |
|------|---------|
| 301 | Moved Permanently — URL has changed forever |
| 302 | Found — temporary redirect |
| 304 | Not Modified — use your cached version |

### 4xx — Client Errors
| Code | Meaning |
|------|---------|
| 400 | Bad Request — malformed request |
| 401 | Unauthorized — need to log in |
| 403 | Forbidden — logged in but not allowed |
| 404 | Not Found — resource doesn't exist |
| 429 | Too Many Requests — rate limited |

### 5xx — Server Errors
| Code | Meaning |
|------|---------|
| 500 | Internal Server Error — something broke on the server |
| 502 | Bad Gateway — upstream server error |
| 503 | Service Unavailable — server is down/overloaded |

---

## HTTP Headers

Headers are key-value pairs that provide metadata about the request or response.

### Common Request Headers
```
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
Accept: text/html,application/json
Accept-Language: en-US,en;q=0.9
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9...
Content-Type: application/json
```

### Common Response Headers
```
Content-Type: text/html; charset=utf-8
Content-Length: 1234
Cache-Control: max-age=3600
Set-Cookie: session=abc123; HttpOnly; Secure
Access-Control-Allow-Origin: *
```

---

## The Request/Response Cycle

```
Browser                          Server
  │                                │
  │── GET /index.html HTTP/1.1 ──→ │
  │   Host: example.com            │
  │   Accept: text/html            │
  │                                │
  │ ←── HTTP/1.1 200 OK ──────────│
  │     Content-Type: text/html    │
  │     <html>...</html>           │
  │                                │
```

---

## Prerequisites

- Lesson 02: What Happens When You Type a URL
- Lesson 03: DNS Explained

## Next Lesson

→ `05-client-server-model`
