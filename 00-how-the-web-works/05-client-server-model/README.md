# 05 — The Client-Server Model

## What Is the Client-Server Model?

The client-server model is the fundamental architecture of the web. It describes how two types of computers communicate:

- **Client** — the computer that *requests* something
- **Server** — the computer that *provides* something

Every time you use the web, you're a client making requests to servers.

---

## The Restaurant Analogy

Think of a restaurant:

| Restaurant | Web |
|-----------|-----|
| Customer (you) | Client (browser) |
| Waiter | HTTP protocol |
| Kitchen | Web server |
| Menu | API / endpoints |
| Food order | HTTP request |
| Meal delivered | HTTP response |
| Restaurant building | Server hardware |
| Recipe book | Database |

The customer (client) doesn't cook the food — they just ask for it. The kitchen (server) does the work and sends the result back.

---

## What Is a Client?

A **client** is any device or program that requests services from a server.

Examples:
- Your web browser (Chrome, Firefox, Safari)
- A mobile app on your phone
- A desktop application
- Another server making API calls
- `curl` or Postman (developer tools)

The client:
1. Initiates the connection
2. Sends a request
3. Waits for a response
4. Processes and displays the response

---

## What Is a Server?

A **server** is a computer (or program) that listens for requests and sends back responses.

Types of servers:
- **Web Server** — serves HTML, CSS, JS files (Apache, Nginx)
- **Application Server** — runs business logic (Node.js, Django, Rails)
- **Database Server** — stores and retrieves data (PostgreSQL, MySQL, MongoDB)
- **File Server** — stores and serves files
- **Mail Server** — handles email

The server:
1. Listens on a port (e.g., port 80 or 443)
2. Receives a request
3. Processes it (may query a database)
4. Sends back a response

---

## How They Communicate

```
CLIENT                          SERVER
  │                               │
  │── HTTP Request ─────────────→ │
  │   GET /api/users              │
  │   Host: api.example.com       │
  │                               │  ← queries database
  │ ←── HTTP Response ───────────│
  │     200 OK                    │
  │     [{"id":1,"name":"Alice"}] │
  │                               │
```

---

## Client-Side vs Server-Side

| Aspect | Client-Side | Server-Side |
|--------|-------------|-------------|
| Runs on | User's browser | Server computer |
| Languages | HTML, CSS, JavaScript | Node.js, Python, PHP, Ruby, Java |
| User can see code? | Yes (View Source) | No |
| Access to database? | No (indirect via API) | Yes |
| Examples | React, Vue, vanilla JS | Express, Django, Rails |

---

## Prerequisites

- Lesson 04: HTTP & HTTPS

## Next Lesson

→ `06-browser-rendering-engine`
