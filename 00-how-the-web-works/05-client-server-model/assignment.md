# Assignment — Client-Server Chat UI

**Due:** Next class session  
**Estimated time:** 1.5–2 hours

---

## Your Task

Create an HTML page that simulates a **client-server conversation** as a chat-style UI. The page should show a back-and-forth "conversation" between a client (browser) and a server, demonstrating how HTTP requests and responses work.

---

## Requirements

### The page must show:

1. **A chat interface** with two sides:
   - Left side: Client (browser) messages
   - Right side: Server messages

2. **At least 4 exchanges** showing:
   - Client sends a GET request
   - Server responds with 200 OK + data
   - Client sends a POST request
   - Server responds with 201 Created
   - Client requests a page that doesn't exist
   - Server responds with 404 Not Found
   - (Optional) Client sends bad data, server responds 400 Bad Request

3. **Each message bubble** should show:
   - Who sent it (Client or Server)
   - The HTTP method or status code
   - A short description of what's happening

4. **Styled with embedded CSS** — make it look like a real chat app

---

## Example Conversation

```
CLIENT                              SERVER
──────────────────────────────────────────
GET /api/users                →
                              ←  200 OK
                                 [{"id":1,"name":"Alice"}]

POST /api/users               →
{"name": "Bob"}
                              ←  201 Created
                                 {"id":2,"name":"Bob"}

GET /api/users/999            →
                              ←  404 Not Found
                                 {"error":"User not found"}
```

---

## Starter Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Client-Server Chat</title>
  <style>
    body {
      font-family: sans-serif;
      background: #f0f4f8;
      padding: 40px 20px;
      max-width: 800px;
      margin: 0 auto;
    }

    .chat-container {
      background: white;
      border-radius: 16px;
      overflow: hidden;
      box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    }

    .chat-header {
      background: #1e293b;
      color: white;
      padding: 16px 20px;
      display: flex;
      justify-content: space-between;
    }

    .messages {
      padding: 20px;
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    .message {
      max-width: 70%;
      padding: 12px 16px;
      border-radius: 12px;
    }

    .client-msg {
      background: #dbeafe;
      border: 1px solid #93c5fd;
      align-self: flex-start;
    }

    .server-msg {
      background: #dcfce7;
      border: 1px solid #86efac;
      align-self: flex-end;
    }

    /* Add more styles... */
  </style>
</head>
<body>
  <h1>💬 Client-Server Conversation</h1>

  <div class="chat-container">
    <div class="chat-header">
      <span>💻 Client (Browser)</span>
      <span>🖥️ Server</span>
    </div>
    <div class="messages">

      <!-- Exchange 1: GET request -->
      <div class="message client-msg">
        <strong>GET /api/users</strong>
        <p>Requesting list of all users</p>
      </div>

      <div class="message server-msg">
        <strong>200 OK</strong>
        <p>Here are the users!</p>
      </div>

      <!-- Add more exchanges -->

    </div>
  </div>
</body>
</html>
```

---

## Bonus Challenges

- Add a "Send Request" button that adds a new message to the chat
- Animate messages appearing (CSS animation)
- Add timestamps to each message
- Show the full HTTP headers in a collapsible section
- Add a "typing..." indicator before the server responds

---

## Grading Criteria

| Criteria | Points |
|----------|--------|
| Chat UI has two sides (client/server) | 20 |
| At least 4 request/response exchanges | 30 |
| Each message shows method/status + description | 20 |
| Page is styled (looks like a chat app) | 20 |
| Messages are visually distinct (left/right) | 10 |
| **Bonus:** Interactive button, animations | +15 |

**Total: 100 points**

---

## Submission

Submit your `client-server-chat.html` file. Make sure all exchanges are visible when the page loads.
