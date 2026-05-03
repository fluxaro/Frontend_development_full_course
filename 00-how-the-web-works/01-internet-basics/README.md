# 01 — Internet Basics

## What Is the Internet?

Think of the internet like a giant postal system. When you send a letter, you write an address on it, drop it in a mailbox, and it travels through sorting facilities and delivery trucks until it reaches the recipient. The internet works the same way — except instead of letters, we send tiny chunks of data called **packets**, and instead of postal roads, we use cables, fiber optics, and wireless signals.

The internet is simply a massive network of computers connected together, all agreeing to communicate using the same set of rules (called **protocols**).

---

## Why It Matters

Every website you visit, every video you stream, every message you send — all of it travels over the internet. Understanding how it works helps you:

- Debug network problems in your apps
- Write faster, more efficient code
- Understand why things like latency and bandwidth affect user experience
- Make better decisions about APIs, CDNs, and hosting

---

## Key Concepts

### Packets
Data is broken into small chunks called packets before being sent. Each packet travels independently and may take a different route. They're reassembled at the destination.

### Protocols
A protocol is a set of agreed-upon rules for communication. Think of it as a language both computers agree to speak. Examples: HTTP, TCP/IP, DNS.

### IP Address
Every device on the internet has a unique address called an IP address (e.g., `192.168.1.1`). It's like a home address for your computer.

### Bandwidth
How much data can travel through a connection at once — like the width of a pipe. More bandwidth = more data at once.

### Latency
The time it takes for data to travel from one point to another. Lower latency = faster response.

---

## A Simple HTTP Request (Concept)

When your browser visits a website, here's what happens at a high level:

```
You type: https://www.google.com

1. Browser asks DNS: "What's the IP for google.com?"
2. DNS replies: "It's 142.250.80.46"
3. Browser sends HTTP request to that IP:
   GET / HTTP/1.1
   Host: www.google.com

4. Google's server responds:
   HTTP/1.1 200 OK
   Content-Type: text/html
   ...the HTML of the page...

5. Browser renders the HTML into what you see
```

---

## What You'll Learn in This Lesson

- What the internet actually is
- How data travels as packets
- What protocols are and why they exist
- Key terms: IP, DNS, HTTP, bandwidth, latency

---

## Prerequisites

- None! This is the very beginning.

## Next Lesson

→ `02-what-happens-when-you-type-a-url`
