# Notes — Client-Server Model Cheat Sheet

## Key Terms

### Client
Any device or program that **requests** services from a server.
- Examples: browser, mobile app, Postman, curl, another server
- Initiates the connection
- Sends HTTP requests
- Receives and displays responses

### Server
A computer or program that **listens** for requests and **provides** responses.
- Examples: Apache, Nginx, Node.js, Django, Rails
- Waits for incoming connections
- Processes requests
- Sends back responses

### Request
A message from client to server asking for something.
- Contains: method, URL, headers, optional body

### Response
A message from server to client with the result.
- Contains: status code, headers, optional body

### Web Server
Serves static files (HTML, CSS, JS, images).
- Examples: Apache, Nginx, Caddy

### Application Server
Runs business logic, handles dynamic content.
- Examples: Node.js/Express, Python/Django, Ruby/Rails, Java/Spring

### Database Server
Stores and retrieves data.
- Examples: PostgreSQL, MySQL, MongoDB, Redis

---

## The Flow

```
Browser (Client)
    │
    │  1. User types URL / clicks button
    │  2. Browser creates HTTP request
    │
    ▼
Web/App Server
    │
    │  3. Server receives request
    │  4. Server processes (may query DB)
    │
    ▼
Database Server
    │
    │  5. DB returns data to server
    │
    ▲
Web/App Server
    │
    │  6. Server builds HTTP response
    │
    ▼
Browser (Client)
    │
    │  7. Browser receives response
    │  8. Browser renders the page
```

---

## Client-Side vs Server-Side

| | Client-Side | Server-Side |
|--|-------------|-------------|
| **Runs on** | User's browser | Server computer |
| **Languages** | HTML, CSS, JavaScript | Node.js, Python, PHP, Ruby, Java, Go |
| **User can see?** | Yes (View Source) | No |
| **DB access?** | No (via API only) | Yes (direct) |
| **Examples** | React, Vue, Angular | Express, Django, Laravel, Rails |
| **Rendering** | Browser renders | Server renders HTML |

---

## Types of Servers

| Type | Purpose | Examples |
|------|---------|---------|
| Web Server | Serve static files | Apache, Nginx |
| App Server | Business logic | Node.js, Django |
| Database Server | Store data | PostgreSQL, MongoDB |
| File Server | Store/serve files | AWS S3, FTP |
| Mail Server | Handle email | Postfix, SendGrid |
| Cache Server | Fast data storage | Redis, Memcached |
| CDN | Serve files globally | Cloudflare, AWS CloudFront |

---

## Common Ports

| Port | Service |
|------|---------|
| 80 | HTTP |
| 443 | HTTPS |
| 3000 | Node.js dev server |
| 5432 | PostgreSQL |
| 3306 | MySQL |
| 27017 | MongoDB |
| 6379 | Redis |

---

## Remember

```
Client asks → Server answers
Client doesn't know HOW the server works
Server doesn't know WHO the client is (stateless by default)
```

HTTP is **stateless** — each request is independent. Servers use cookies/sessions/tokens to remember users between requests.
