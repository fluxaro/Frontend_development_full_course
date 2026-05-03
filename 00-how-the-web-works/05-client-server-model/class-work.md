# Class Work — The Client-Server Model

## Activity 1: Draw the Client-Server Model (15 minutes)

On paper or a whiteboard, draw a diagram showing:

1. A **client** (browser on a laptop)
2. A **server** (web server)
3. A **database** (connected to the server)
4. **Arrows** showing:
   - HTTP Request from client to server
   - Database query from server to database
   - Database response back to server
   - HTTP Response from server to client

**Label each arrow** with what's happening.

**Questions to answer in your diagram:**
- What does the client send?
- What does the server do with the request?
- Why does the client not talk directly to the database?

---

## Activity 2: Identify Clients and Servers (10 minutes)

For each item below, identify whether it's a **client**, a **server**, or **both**:

| Item | Client / Server / Both? |
|------|------------------------|
| Chrome browser | |
| Apache web server | |
| Your iPhone | |
| Netflix's streaming server | |
| Postman (API testing tool) | |
| A Node.js app that calls a payment API | |
| MySQL database | |
| A React app in the browser | |

---

## Activity 3: Build a Client-Server Diagram Page (25 minutes)

Create an HTML file called `my-client-server-diagram.html` that visually shows the client-server model.

### Requirements:
1. Show a **client** box (browser icon + label)
2. Show a **server** box (server icon + label)
3. Show a **database** box (database icon + label)
4. Show **arrows** between them with labels
5. Include a short description of what each component does

### Starter HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Client-Server Model</title>
  <style>
    body {
      font-family: sans-serif;
      background: #f0f4f8;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 40px 20px;
    }

    .diagram {
      display: flex;
      align-items: center;
      gap: 20px;
      margin: 40px 0;
    }

    .box {
      background: white;
      border: 2px solid #3b82f6;
      border-radius: 12px;
      padding: 20px;
      text-align: center;
      width: 140px;
    }

    .box .icon { font-size: 2.5rem; }
    .box .label { font-weight: bold; margin-top: 8px; }

    .arrow {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 4px;
      font-size: 0.75rem;
      color: #64748b;
    }

    .arrow-line {
      width: 60px;
      height: 2px;
      background: #94a3b8;
      position: relative;
    }
  </style>
</head>
<body>
  <h1>The Client-Server Model</h1>

  <div class="diagram">
    <div class="box">
      <div class="icon">💻</div>
      <div class="label">Client</div>
      <div style="font-size:0.75rem; color:#64748b; margin-top:4px;">Browser</div>
    </div>

    <div class="arrow">
      <span>→ Request</span>
      <div class="arrow-line"></div>
      <span>← Response</span>
    </div>

    <div class="box">
      <div class="icon">🖥️</div>
      <div class="label">Server</div>
      <div style="font-size:0.75rem; color:#64748b; margin-top:4px;">Web Server</div>
    </div>

    <!-- Add database box and arrow -->
  </div>

  <!-- Add descriptions below -->
</body>
</html>
```

---

## Discussion Questions

1. Can a computer be both a client and a server at the same time? Give an example.
2. Why is it important that clients can't directly access the database?
3. What happens if the server goes down? What does the client see?
4. What's the difference between a web server and an application server?

---

## Deliverable

Share your diagram with the class and explain the flow of a request from client to database and back.
